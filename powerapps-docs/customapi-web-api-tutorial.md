---
title: "Создание настраиваемого соединителя для веб-API | Документация Майкрософт"
description: "Сведения о создании веб-API ASP.NET с проверкой подлинности Azure Active Directory в PowerApps."
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
ms.date: 10/26/2016
ms.author: mblythe
ms.openlocfilehash: 4fc9fb1d183ec910d37383be6629aaa67cf3723d
ms.sourcegitcommit: 68eee592c351688e5d0bd458f33a70be507fa53f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2018
---
# <a name="build-a-custom-connector-for-a-web-api-in-powerapps"></a>Создание настраиваемого соединителя для веб-API в PowerApps
В этом руководстве показано, как приступить к созданию веб-API ASP.NET, разместить его в веб-приложениях Azure, а также как включить проверку подлинности Azure Active Directory, а затем зарегистрировать веб-API ASP.NET в службе PowerApps. После регистрации API вы можете подключиться к нему и вызвать его из приложения.

## <a name="prerequisites"></a>Технические условия
* [Подписка Azure](https://azure.microsoft.com/en-us/free/).
* [Учетная запись PowerApps](https://powerapps.microsoft.com).
* [Visual Studio](https://www.visualstudio.com/vs/) 2013 или более поздней версии.

## <a name="create-an-aspnet-web-api-and-deploy-it-to-azure"></a>Создание веб-API ASP.NET и его развертывание в Azure
1. Чтобы создать веб-приложение ASP.NET на языке C#, в Visual Studio щелкните **Файл** > **Новый проект**.
   
    ![Новое веб-приложение](./media/customapi-web-api-tutorial/newwebapp.png)
2. Выберите шаблон **веб-API**.  Установите флажок **Разместить в облаке**.  Нажмите кнопку **Изменить способ проверки подлинности**.
   
    ![Шаблон нового веб-проекта](./media/customapi-web-api-tutorial/new-web-api.png)
3. Установите флажок **Без проверки подлинности** и нажмите кнопку **ОК**.
   
    ![Флажок "Без проверки подлинности"](./media/customapi-web-api-tutorial/noauth.png)
4. В диалоговом окне **Новый проект ASP.NET** нажмите кнопку **ОК**.  После этого откроется диалоговое окно "Настройка веб-приложения Microsoft Azure".
   
    ![Диалоговое окно "Настройка веб-приложения Microsoft Azure"](./media/customapi-web-api-tutorial/azure-publishing.png)]
   
    Выберите учетную запись, введите **имя веб-приложения** (или оставьте значение по умолчанию) и выберите **подписку** Azure.  Выберите или создайте **план службы приложений** (коллекция веб-приложений в подписке).  Выберите или создайте **группу ресурсов** (группа ресурсов Azure в подписке).  Выберите регион для развертывания веб-приложения.  При необходимости выберите или создайте **сервер базы данных Azure**.  И наконец, нажмите кнопку **ОК**.
5. Создайте веб-API.
   
    > [!NOTE]
> Если у вас еще нет кода для веб-API, ознакомьтесь с руководством по [началу работы с веб-API 2 ASP.NET (C#)](http://www.asp.net/web-api/overview/getting-started-with-aspnet-web-api/tutorial-your-first-web-api).
6. Чтобы подключить веб-API к PowerApps, вам потребуется файл [OpenAPI](http://swagger.io/), в котором описаны операции этого интерфейса.  Вы можете сами написать этот файл в [интерактивном редакторе](http://editor.swagger.io/), но в рамках этого руководства мы будем использовать средство с открытым кодом под названием [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle/blob/master/README.md).  Установите пакет NuGet Swashbuckle в проекте Visual Studio. Для этого щелкните **Инструменты** > **Диспетчер пакетов NuGet** > **Консоль диспетчера пакетов**, а затем в окне консоли введите команду `Install-Package Swashbuckle`.
   
    ![Команда Install-Package Swashbuckle](./media/customapi-web-api-tutorial/swashbuckle-console.png)
   
    > [!TIP]
> Когда вы запустите приложение веб-API после установки Swashbuckle, в расположении с URL-адресом `http://<your root URL>/swagger/docs/v1` будет создан файл OpenAPI.  Созданный пользовательский интерфейс также доступен по адресу `http://<your root URL>/swagger`.
7. Когда веб-API будет готов, опубликуйте его в Azure. Чтобы опубликовать его из Visual Studio, щелкните веб-проект правой кнопкой мыши в обозревателе решений, а затем выберите **Опубликовать...** и следуйте указаниям в диалоговом окне публикации.
8. Получите JSON-файл OpenAPI, перейдя по адресу `https://<azure-webapp-url>/swagger/docs/v1`.  Сохраните содержимое в формате JSON.  В зависимости от браузера может потребоваться скопировать и вставить текст в пустой текстовый файл.   
   
    > [!IMPORTANT]
> Документ OpenAPI с повторяющимися идентификаторами операций недопустимый. При использовании шаблона C# идентификатор операции `Values_Get` повторяется дважды. Это можно исправить, изменив один экземпляр на `Value_Get` и повторно опубликовав документ. Вы также можете скачать пример файла OpenAPI из [этого руководства](http://pwrappssamples.blob.core.windows.net/samples/webAPI.json). Перед его использованием нужно удалить комментарии (которые начинаются с `//`).

## <a name="set-up-azure-active-directory-authentication"></a>Настройка проверки подлинности Azure Active Directory
Теперь вы создадите два приложения Azure Active Directory (AAD) в Azure.  Пример см. в руководстве по [Azure Resource Manager](customapi-azure-resource-manager-tutorial.md#enable-authentication-in-azure-active-directory).

> [!IMPORTANT]
> Оба приложения должны находиться в одном каталоге.

### <a name="first-aad-application-securing-the-web-api"></a>Обеспечение безопасности веб-API с помощью первого приложения AAD
Первое приложение AAD используется для защиты веб-API. Назовите его **webAPI**.  Следуйте инструкциям в упомянутом выше руководстве (только в разделе "Включение проверки подлинности в Azure Active Directory") и укажите следующие значения:

* URL-адрес входа: `https://login.windows.net`.
* URL-адрес ответа: `https://<your-root-url>/.auth/login/aad/callback`.
* Клиентский ключ не нужен.
* Делегировать разрешения не нужно.

> [!IMPORTANT]
> Запишите идентификатор приложения.  Он понадобится вам позже.

### <a name="second-aad-application-securing-the-custom-connector-and-delegated-access"></a>Защита настраиваемого соединителя и получение делегированного доступа с помощью второго приложения AAD
Второе приложение AAD используется для защиты настраиваемого соединителя при регистрации и получении делегированного доступа к веб-API, защищенного первым приложением. Назовите это приложение **webAPI-customAPI**.

* URL-адрес входа: `https://login.windows.net`.
* URL-адрес ответа: `https://msmanaged-na.consent.azure-apim.net/redirect`.
* Добавьте разрешения, чтобы делегировать доступ к веб-API.
* Идентификатор этого приложения также понадобится вам позже. Запишите его.
* Создайте клиентский ключ и сохраните его в безопасном месте. Этот ключ понадобится вам позже.

## <a name="add-authentication-to-your-azure-web-app"></a>Добавление проверки подлинности для веб-приложения Azure

1. Войдите на [портал Azure](https://portal.azure.com) и найдите веб-приложение, развернутое во время работы с первым разделом.

2. Щелкните **Параметры**, а затем выберите **Аутентификация или авторизация**.

3. Включите **проверку подлинности службы приложений**, а затем выберите **Azure Active Directory**.  В следующей колонке выберите **Экспресс**.  

4. Щелкните **Выбрать существующее приложение AD** и выберите приложение AAD **webAPI**, созданное ранее.

Теперь AAD можно использовать для проверки подлинности веб-приложения.

## <a name="add-the-custom-connector-to-powerapps"></a>Добавление настраиваемого соединителя в PowerApps
1. Добавьте в файл OpenAPI объект `securityDefintions` и проверку подлинности AAD, используемую для веб-приложения. Раздел файла OpenAPI со свойством **host** должен выглядеть следующим образом:

    ```javascript
    // File header should be above here...

    "host": "<your-root-url>",
    "schemes": [
        "https"         //Make sure this is https!
    ],
    "securityDefinitions": {
        "AAD": {
            "type": "oauth2",
            "flow": "implicit",
            "authorizationUrl": "https://login.windows.net/common/oauth2/authorize",
            "scopes": {}
        }
    },

    // The rest of the OpenAPI document follows...
    ```

2. Перейдите в службу [PowerApps](https://web.powerapps.com) и добавьте настраиваемый соединитель, как описано в статье [Регистрация настраиваемых интерфейсов API в PowerApps](register-custom-api.md).

3. После отправки файла OpenAPI мастер автоматически обнаружит, что для веб-API используется проверка подлинности AAD.

4. Настройте проверку подлинности AAD для настраиваемого соединителя.  
   
   * **Идентификатор клиента**: *идентификатор клиента для webAPI-CustomAPI*.
   * **Секрет**: *клиентский ключ для webAPI-CustomAPI*.
   * **URL-адрес входа**: `https://login.windows.net`.
   * **URI ресурса**: *идентификатор клиента для webAPI*.
5. Щелкните **Создать** и создайте подключение к настраиваемому соединителю.

## <a name="next-steps"></a>Следующие шаги
Ознакомьтесь с руководством [Создание настраиваемого API с помощью Azure Resource Manager в PowerApps](customapi-azure-resource-manager-tutorial.md).

