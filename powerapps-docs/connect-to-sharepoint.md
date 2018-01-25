---
title: "Создание подключения к SharePoint из PowerApps | Документация Майкрософт"
description: "На сайте powerapps.com создайте подключение к SharePoint, чтобы использовать его для автоматического создания приложения или сборки приложения с нуля."
services: 
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/03/2016
ms.author: sharik
ms.openlocfilehash: e9023c75dab32b59fb86e1fea4a2a89dd0e4454f
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2018
---
# <a name="create-a-connection-to-sharepoint-from-powerapps"></a>Создание подключения к SharePoint из PowerApps
Создайте подключение к SharePoint Online или локальному сайту SharePoint, чтобы использовать его для автоматического создания приложения или сборки приложения с нуля.

Если вы еще не работали с PowerApps, см. статью [Знакомство с PowerApps](getting-started.md).

На момент написания этой статьи служба PowerApps поддерживает пользовательские списки, но не поддерживает библиотеки. Кроме того, данные можно отображать в столбцах некоторых типов, например **Choice** (Выбор) и **Picture** (Изображение), но обновить эти данные невозможно. Дополнительные сведения см. в разделе с описанием [известных проблем](connections/connection-sharepoint-online.md#known-issues).

## <a name="specify-a-sharepoint-connection"></a>Настройка подключения SharePoint
1. Если вы еще не сделали это, [зарегистрируйтесь для использования PowerApps](signup-for-powerapps.md).

2. Войдите в [powerapps.com](https://web.powerapps.com), используя те же учетные данные, которые вы ввели при регистрации.

3. На панели навигации слева выберите раскрывающийся список **Manage** (Управление), а затем — пункт **Connections** (Подключения).

    ![Пункт "Создать" в меню "Файл"](./media/connect-to-sharepoint/manage-connections.png)

4. В правом верхнем углу экрана нажмите кнопку **New connection** (Создать подключение).

    ![Кнопка создания подключения](./media/connect-to-sharepoint/new-connection.png)

5. В списке подключений выберите **SharePoint**.

    ![Добавление подключения SharePoint](./media/connect-to-sharepoint/add-sp-portal.png)

6. Выполните действия, описанные в любой из следующих процедур:

   * [Подключение к сайту SharePoint Online](connect-to-sharepoint.md#connect-to-a-sharepoint-online-site).
   * [Подключение к локальному сайту SharePoint](connect-to-sharepoint.md#connect-to-an-on-premises-sharepoint-site).

## <a name="connect-to-a-sharepoint-online-site"></a>Подключение к сайту SharePoint Online
1. Выберите **Connect directly (cloud services)** (Подключиться напрямую (облачные службы)), и нажмите кнопку **Add connection** (Добавить подключение).

    ![Выбор SharePoint Online](./media/connect-to-sharepoint/choose-online.png)

2. Перейдите к разделу [Дальнейшие действия](connect-to-sharepoint.md#next-steps) в конце этой статьи.

## <a name="connect-to-an-on-premises-sharepoint-site"></a>Подключение к локальному сайту SharePoint
1. Выберите **Connect using on-premises data gateway** (Подключение с помощью локального шлюза данных).

    ![Выбор локального сайта SharePoint](./media/connect-to-sharepoint/choose-onprem.png)

    > [!NOTE]
> Пользователь может создавать и использовать шлюзы и локальные подключения только в своей [среде по умолчанию](working-with-environments.md).

2. Укажите имя пользователя и пароль.

    Если учетные данные содержат имя домена, укажите его в формате *домен\псевдоним*.

    ![Ввод учетных данных](./media/connect-to-sharepoint/specify-credentials.png)

3. Если у вас нет локального шлюза данных, [установите его](gateway-reference.md), а затем щелкните значок, чтобы обновить список шлюзов.

    ![Установка шлюза](./media/connect-to-sharepoint/install-gateway.png)

4. В поле **Choose a gateway** (Выбор шлюза) выберите шлюз, который вы хотите использовать, и нажмите кнопку **Add connection** (Добавить подключение).

    ![Выбор шлюза](./media/connect-to-sharepoint/choose-gateway.png)

## <a name="next-steps"></a>Дальнейшие действия
* [Автоматическое создание приложения](app-from-sharepoint.md) на основе указанного списка. По умолчанию приложение будет включать три экрана: для просмотра записей, для отображения сведений об отдельной записи, а также для создания или обновления записи.
* [Создание приложения с нуля](get-started-create-from-blank.md). Эта статья написана для Excel, но инструкции в ней применимы и к SharePoint.
