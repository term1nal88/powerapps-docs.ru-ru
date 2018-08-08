---
title: Создание приложения на основе холста из списка SharePoint | Документы Майкрософт
description: Создание приложения на основе холста с тремя экранами для управления элементами списка SharePoint из локальных и облачных сайтов.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: 9230c96c1b1c5e07ea5129f73a8edd95772aad84
ms.sourcegitcommit: e3f5a2bef64085d02aec82e62ff94ae8a4d01d24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39471427"
---
# <a name="generate-a-canvas-app-from-within-sharepoint-by-using-powerapps"></a>Создание приложения на основе холста из списка SharePoint с использованием PowerApps

В PowerApps вы можете автоматически создать приложение на основе холста, в котором пользователи смогут управлять элементами настраиваемого списка SharePoint Online. Это приложение будет состоять из трех экранов, позволяющих пользователям:

* просматривать все записи в списке (**BrowseScreen1**);
* просматривать все поля для определенной записи (**DetailsScreen1**);
* создавать или изменять записи (**EditScreen1**).

Если создать приложение настраиваемого списка с помощью панели команд SharePoint Online, такое приложение будет доступно как представление этого списка. Помимо веб-браузера, это приложение можно запускать на устройствах iOS и Android.

> [!IMPORTANT]
> PowerApps не поддерживает все типы данных SharePoint. Дополнительные сведения см. в разделе с описанием [известных проблем](connections/connection-sharepoint-online.md#known-issues).

## <a name="generate-an-app"></a>Создание приложения
1. Откройте настраиваемый список в SharePoint Online, щелкните или нажмите **PowerApps** на панели команд, а затем выберите **Create an app** (Создать приложение).

    ![Создание приложения](./media/generate-app-from-sharepoint-list-interface/generate-new-app.png)

2. На появившейся панели введите название приложения, а затем щелкните или нажмите **Create** (Создать).

    ![Присвоение имени приложению](./media/generate-app-from-sharepoint-list-interface/app-name.png)

    В веб-браузере откроется новая вкладка с приложением, созданным автоматически на основе вашего списка SharePoint. Приложение откроется в PowerApps Studio, где его можно настроить.

    ![Приложение по умолчанию](./media/generate-app-from-sharepoint-list-interface/default-app.png)  
3. Щелкните или нажмите на вкладку со списком SharePoint и выберите **Open** (Открыть).

> [!NOTE]
> Прежде чем приложение откроется, вам, возможно, потребуется обновить содержимое окна браузера (например, нажав клавишу F5).

Приложение откроется на отдельной вкладке браузера.

## <a name="manage-the-app"></a>Управление приложением
![Панель команд](./media/generate-app-from-sharepoint-list-interface/command-bar.png)

* Если выбрать **Edit in PowerApps** (Изменить в PowerApps), приложение откроется на отдельной вкладке браузера, где вы сможете изменить его в PowerApps Studio.

* Если выбрать **Make this view public** (Сделать это представление общедоступным), ваши сотрудники смогут просматривать приложение. По умолчанию создаваемые вами представления доступны только вам. Если вы хотите, чтобы другие пользователи могли вносить изменения в приложение, вам потребуется [предоставить им общий доступ](share-app.md) и разрешения **Можно изменять**.

* Если выбрать **Remove this view** (Удалить это представление), представление будет удалено из SharePoint, но приложение останется доступным в PowerApps, пока вы не [удалите его](delete-app.md).

## <a name="next-steps"></a>Дальнейшие действия
* Настройте [коллекцию](customize-layout-sharepoint.md), [формы](customize-forms-sharepoint.md) и [карточки](customize-card.md) по умолчанию.
