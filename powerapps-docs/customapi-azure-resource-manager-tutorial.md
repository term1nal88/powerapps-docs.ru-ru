---
title: "Использование Azure Active Directory с настраиваемым соединителем | Документация Майкрософт"
description: "Сведения о создании настраиваемого соединителя для Azure Resource Manager с проверкой подлинности Azure Active Directory."
services: 
suite: powerapps
documentationcenter: 
author: mgblythe
manager: anneta
editor: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/03/2017
ms.author: mblythe
ms.openlocfilehash: c62a927ae6a7e7b6cf6b101d84e3ba1fe15cccc5
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2017
---
# <a name="use-azure-active-directory-with-a-custom-connector-in-powerapps"></a>Использование Azure Active Directory с настраиваемым соединителем в PowerApps
Azure Resource Manager (ARM) позволяет управлять такими компонентами решения в Azure, как базы данных, виртуальные машины и веб-приложения. В этом руководстве показано, как включить проверку подлинности в Azure Active Directory, зарегистрировать один из API ARM в качестве настраиваемого соединителя, а затем подключиться к нему в PowerApps. Это позволит управлять ресурсами Azure непосредственно из приложения. Дополнительные сведения о ARM см. в [этой статье](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview).

## <a name="prerequisites"></a>Технические условия
* [Подписка Azure](https://azure.microsoft.com/free/).
* [Учетная запись PowerApps.](https://powerapps.microsoft.com)
* [Пример файла OpenAPI](http://pwrappssamples.blob.core.windows.net/samples/AzureResourceManager.json), используемый в этом руководстве.

## <a name="enable-authentication-in-azure-active-directory"></a>Включение проверки подлинности в Azure Active Directory
Сначала необходимо создать приложение Azure Active Directory (AAD), которое будет выполнять проверку подлинности при вызове конечной точки API ARM.

1. Войдите на [портал Azure](https://portal.azure.com).  Если вы используете несколько клиентов Azure Active Directory, убедитесь, что вы вошли в правильный каталог. Для этого проверьте свое имя пользователя в правом верхнем углу.
   
    ![Имя пользователя](./media/customapi-azure-resource-manager-tutorial/current-user.png)
2. В меню слева выберите пункт **Дополнительные службы**.  В текстовом поле **Фильтр** введите **Azure Active Directory**, а затем нажмите кнопку **Azure Active Directory**.
   
    ![Azure Active Directory](./media/customapi-azure-resource-manager-tutorial/azureaad.png)
   
    Откроется колонка Azure Active Directory.   
3. В меню колонки Azure Active Directory выберите пункт **Регистрация приложений**.
   
    ![Регистрация приложений](./media/customapi-azure-resource-manager-tutorial/azureapplication.png)
4. В списке зарегистрированных приложений нажмите кнопку **Добавить**.
   
    ![Кнопка "Добавить"](./media/customapi-azure-resource-manager-tutorial/add-app-btn.png)   
5. Введите имя приложения, оставьте тип **Веб-приложение или API**, а в поле **URL-адрес входа** введите `https://login.windows.net`.  Нажмите кнопку **Создать**.  
   
    ![Форма нового приложения](./media/customapi-azure-resource-manager-tutorial/newapplication.png)
6. Выберите новое приложение в списке.
   
    ![Новое приложение в списке](./media/customapi-azure-resource-manager-tutorial/newapplication2.png)
   
    Откроется колонка зарегистрированных приложений.  Запишите **идентификатор приложения**.  Он понадобится позже.
7. Колонка параметров тоже должна быть открыта.  Если колонка не открыта, нажмите кнопку **Параметры**.
   
    ![Кнопка "Параметры"](./media/customapi-azure-resource-manager-tutorial/settings-btn.png)
8. В колонке "Параметры" щелкните **URL-адреса ответа**. В списке URL-адресов добавьте `https://msmanaged-na.consent.azure-apim.net/redirect` и нажмите кнопку **Сохранить**.
   
    ![URL-адреса ответа](./media/customapi-azure-resource-manager-tutorial/reply-urls.png)
9. В колонке "Параметры" щелкните **Необходимые разрешения**.  В колонке "Необходимые разрешения" нажмите кнопку **Добавить**.
   
    ![Необходимые разрешения](./media/customapi-azure-resource-manager-tutorial/permissions.png)
   
    Откроется колонка "Добавить доступ через API".
10. Щелкните **Выбрать API**. В открывшейся колонке выберите вариант для API управления службами Azure и нажмите кнопку **Выбрать**.
    
    ![Выбор API](./media/customapi-azure-resource-manager-tutorial/permissions2.png)
11. Щелкните **Выбрать разрешения**.  В разделе *Делегированные разрешения* щелкните **Доступ к управлению службами Azure для пользователей организации** и нажмите кнопку **Выбрать**.
    
    ![Делегированные разрешения](./media/customapi-azure-resource-manager-tutorial/permissions3.png)
12. В колонке "Добавить доступ через API" нажмите кнопку **Готово**.
13. В колонке "Параметры" щелкните **Ключи**.  В колонке "Ключи" введите описание для ключа, выберите срок действия, затем нажмите кнопку **Сохранить**.  Отобразится новый ключ.  Запишите значение ключа, так как позднее оно нам понадобится.  Теперь можно закрыть портал Azure.
    
    ![Создание ключа](./media/customapi-azure-resource-manager-tutorial/configurekeys.png)

## <a name="add-the-connection-in-powerapps"></a>Добавление подключения к PowerApps
Теперь, когда приложение AAD настроено, добавим настраиваемый соединитель.

1. На сайте [powerapps.com](https://web.powerapps.com) в меню слева выберите **Подключения**. Выберите многоточие **...**, а затем — **Manage custom connectors** (Управление настраиваемыми соединителями) в верхнем правом углу.
   
     **Совет.** Если вам не удается найти область управления настраиваемыми соединителями в браузере мобильного устройства, вы можете перейти к ней из меню в верхнем левом углу.
   
    ![Создание настраиваемого соединителя](./media/customapi-azure-resource-manager-tutorial/managecustomapi.png)  
2. Выберите **Create custom connector** (Создание настраиваемого соединителя).
   
    ![Свойства настраиваемого соединителя](./media/customapi-azure-resource-manager-tutorial/newcustomapi.png)
3. Введите имя подключения, а затем отправьте пример [файла ARM OpenAPI](http://pwrappssamples.blob.core.windows.net/samples/AzureResourceManager.json).  Щелкните **Продолжить**.  
   
    ![Подключение к новой конечной точке API](./media/customapi-azure-resource-manager-tutorial/createcustom.png)
4. Так как файл OpenAPI использует наше приложение AAD для проверки подлинности, на следующем экране необходимо предоставить некоторые сведения о приложении PowerApps.  В поле **Идентификатор клиента** введите **идентификатор приложения** AAD, записанный ранее.  В качестве секрета клиента используйте **ключ**.  И наконец, в поле **URL-адрес ресурса** введите `https://management.core.windows.net/`.
   
    **Важно.** Обязательно вставьте URL-адрес ресурса в точности, как указано выше, в том числе косую черту в конце.
   
    ![Параметры OAuth](./media/customapi-azure-resource-manager-tutorial/oauthsettings.png)
5. Настраиваемый соединитель зарегистрирован. Теперь его можно использовать в PowerApps или Microsoft Flow.
   
    ![Добавленный настраиваемый соединитель](./media/customapi-azure-resource-manager-tutorial/createdcustomapi.png)
   
    **Примечание.** Пример OpenAPI не определяет полный набор операций ARM. Сейчас он содержит только операцию [вывода списка всех подписок](https://msdn.microsoft.com/library/azure/dn790531.aspx).  Вы можете изменить этот файл OpenAPI или создать другой, используя [интерактивный редактор OpenAPI](http://editor.swagger.io/). Этот процесс можно использовать для доступа к любой API RESTful, который прошел проверку подлинности с помощью AAD.

## <a name="next-steps"></a>Дальнейшие действия
Подробные сведения о создании приложения см. в статье [Generate an app from Excel data](get-started-create-from-data.md) (Создание приложения на основе данных Excel).

Подробные сведения об использовании последовательности см. в статье, посвященной [запуску последовательности в приложении](using-logic-flows.md).

Чтобы задать вопросы или оставить комментарии о настраиваемых соединителях, [присоединитесь к нашему сообществу](https://aka.ms/powerapps-community).

