---
title: Создание или изменение панелей мониторинга управляемых моделью приложений | MicrosoftDocs
ms.custom: ''
ms.date: 05/23/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.assetid: 641885d2-4a08-41b8-b914-d9a244e4d5b1
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-or-edit-model-driven-app-dashboards"></a>Создание или изменение панелей мониторинга управляемых моделью приложений

Существует два основных типа панелей мониторинга: системные панели мониторинга и пользовательские панели мониторинга. Пользователь приложения может создать панель мониторинга, видимую только ему в областях приложения, на доступ к которым у него есть привилегии. Системные панели мониторинга создаются и настраиваются администратором или настройщиком. После публикации они доступны всем пользователям приложения. Пользователь может сделать свою пользовательскую панель мониторинга панелью по умолчанию и переопределить системную панель мониторинга. В этом разделе рассматриваются системные панели мониторинга.  
  
<a name="BKMK_createdashboard"></a>   
## <a name="create-a-new-dashboard"></a>Создать новую панель мониторинга  
  
1.  На сайте [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) выберите **Управляемые моделью** (в левой нижней части панели навигации).

    ![Режим разработки, управляемый моделью](media/model-driven-switch.png)

    > [!IMPORTANT]
    > Если режим разработки **Управляемые моделью** недоступен, может потребоваться [создать среду](https://docs.microsoft.com/powerapps/administrator/create-environment).   
  
2. Разверните **Данные**, выберите **Сущности**, выберите сущность, на основании которой требуется создать панель мониторинга, например сущность **Организация**, и перейдите на вкладку **Панели мониторинга**. 

3. На панели инструментов выберите **Добавить панель мониторинга**, затем выберите макет с 2, 3 или 4 столбцами.  
  
4.  В диалоговом окне **Панель мониторинга: создание** введите имя для панели мониторинга.  
  
5.  Выберите одну из областей компонентов, затем выберите значок диаграммы или списка.  
  
     Панель мониторинга может содержать до 6 компонентов.  
  
6.  Например, чтобы добавить диаграмму, в диалоговом поле **Добавление компонента** выберите значения в полях **Тип записей**, **Представление** и **Диаграмма**, а затем нажмите **Добавить**, чтобы добавить диаграмму на панель мониторинга.  
  
7.  Закончив добавлять компоненты на панель мониторинга, выберите **Сохранить** и **Опубликовать**.  
  
<a name="BKMK_editdashboard"></a>   
## <a name="edit-an-existing-dashboard"></a>Изменение существующей панели мониторинга  
  
1. На сайте [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) выберите **Управляемые моделью** (в левой нижней части панели навигации).

    > [!IMPORTANT]
    > Если режим разработки **Управляемые моделью** недоступен, может потребоваться [создать среду](https://docs.microsoft.com/powerapps/administrator/create-environment).    
  
2. Разверните **Данные**, выберите **Сущности**, выберите сущность, на основании которой требуется создать панель мониторинга, например сущность **Организация**, и перейдите на вкладку **Панели мониторинга**.  

3. Откройте панель мониторинга, выберите одну из областей компонентов, затем на панели инструментов выберите **Изменить компонент**.  
  
4.  В диалоговом окне **Задать свойства** можно внести изменения в диаграмму или список, например изменить сущность, представление по умолчанию, добавить селектор диаграммы или сделать панель мониторинга доступной в мобильных приложениях. По завершении выберите **Задать**.  
  
     Для получения дополнительных сведений о свойствах компонентов панелей мониторинга см. раздел [Установка свойств диаграммы или списка, включенных на панель мониторинга](set-properties-chart-list-included-dashboard.md).  
  
4.  По завершении внесения изменений сохраните их, а затем опубликуйте.  
  
 Дополнительные задачи системных панелей мониторинга:  
  
    -   Удаление списка или диаграммы из панели мониторинга  
  
    -   Добавление диаграммы или списка на панель мониторинга  
  
    -   Назначение панели мониторинга по умолчанию  
  
    -   Использование ролей безопасности для отображения панелей мониторинга только для некоторых ролей.    
  
## <a name="next-steps"></a>Дальнейшие действия  
[Установка свойств диаграммы или списка, включенных на панель мониторинга](set-properties-chart-list-included-dashboard.md)
