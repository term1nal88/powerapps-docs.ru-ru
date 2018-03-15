---
title: "Создание приложения из списка SharePoint | Документация Майкрософт"
description: "Создание приложение с тремя экранами для управления элементами списка SharePoint для сайтов в локальных и облачных средах."
services: 
suite: powerapps
documentationcenter: na
author: skjerland
manager: kfile
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/21/2017
ms.author: sharik
ms.openlocfilehash: e5299b12e3034978b14c70193151440626267c5a
ms.sourcegitcommit: 91851aebdf650e99d15374478901b3762d2b4a4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2018
---
# <a name="generate-an-app-from-within-sharepoint-using-powerapps"></a>Создание приложения из списка SharePoint с использованием PowerApps

В PowerApps вы можете автоматически создать приложение, в котором пользователи смогут управлять элементами в настраиваемом списке SharePoint Online. Это приложение будет состоять из трех экранов, позволяющих пользователям:

* просматривать все записи в списке (**BrowseScreen1**);
* просматривать все поля для определенной записи (**DetailsScreen1**);
* создавать или изменять записи (**EditScreen1**).

Если создать приложение настраиваемого списка с помощью панели команд SharePoint Online, такое приложение будет доступно как представление этого списка. Вы также сможете запускать это приложение как в веб-браузере, так и на устройствах Windows Phone, iOS и Android.

> [!IMPORTANT]
> PowerApps не поддерживает все типы данных SharePoint. Дополнительные сведения см. в разделе с описанием [известных проблем](connections/connection-sharepoint-online.md#known-issues).

## <a name="generate-an-app"></a>Создание приложения
1. Откройте настраиваемый список в SharePoint Online, щелкните или нажмите **PowerApps** на панели команд, а затем выберите **Create an app** (Создать приложение).
   
    ![](./media/generate-app-from-sharepoint-list-interface/generate-new-app.png)
2. На появившейся панели введите название приложения, а затем щелкните или нажмите **Create** (Создать).
   
    ![](./media/generate-app-from-sharepoint-list-interface/enter-app-name.png)
   
    В веб-браузере откроется новая вкладка с приложением, созданным автоматически на основе вашего списка SharePoint.
   
    ![](./media/generate-app-from-sharepoint-list-interface/powerapp-studio-for-web.png)  
3. Щелкните или нажмите на вкладку со списком SharePoint и выберите **Open** (Открыть).
   
    > [!NOTE]
> Прежде чем приложение откроется, вам, возможно, потребуется обновить содержимое окна браузера (например, нажав клавишу F5).
   
    ![](./media/generate-app-from-sharepoint-list-interface/open-app-in-browser.png)
   
    Приложение откроется на отдельной вкладке браузера.
   
    ![](./media/generate-app-from-sharepoint-list-interface/open-app.png)

## <a name="manage-the-app"></a>Управление приложением
![](./media/generate-app-from-sharepoint-list-interface/command-bar.png)

* Если выбрать **Edit in PowerApps** (Изменить в PowerApps), приложение откроется на отдельной вкладке браузера и вы сможете внести изменения в его веб-версию в PowerApps Studio.
* Если выбрать **Make this view public** (Сделать это представление общедоступным), ваши сотрудники смогут просматривать приложение. По умолчанию создаваемые вами представления доступны только вам. Если вы хотите, чтобы другие пользователи могли вносить изменения в приложение, вам потребуется [предоставить им общий доступ](share-app.md) и разрешения **участника**.
* Если выбрать **Remove this view** (Удалить это представление), представление будет удалено из SharePoint, но приложение останется доступным в PowerApps, пока вы не [удалите его](delete-app.md).

## <a name="next-steps"></a>Дальнейшие действия
* Чтобы добавить или обновить элементы в списке, см. раздел "Управление списком с помощью приложения" статьи [Открытие приложения из списка SharePoint](open-app-embedded-in-sharepoint.md).
* Чтобы настроить экран обзора (который отображается по умолчанию), см. статью о [настройке макета](customize-layout-sharepoint.md).
* Чтобы настроить сведения или экраны редактирования, см. статью о [настройке формы](customize-forms-sharepoint.md).
* Чтобы удалить это приложение, удалите соответствующее представление из SharePoint, а затем [удалите приложение](delete-app.md) из PowerApps.

