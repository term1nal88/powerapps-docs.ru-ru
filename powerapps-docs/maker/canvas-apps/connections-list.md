---
title: Общие сведения о соединителях | Документация Майкрософт
description: Обзор всех доступных подключений, которые можно использовать для создания приложений
services: ''
suite: powerapps
documentationcenter: ''
author: archnair
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.workload: na
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 08/28/2017
ms.author: archanan
ms.openlocfilehash: aff9e09ea92376c19067fbbc99dc1a9d8ccb0f99
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="overview-of-connectors-for-powerapps"></a>Общие сведения о соединителях для PowerApps
Большинство приложений основываются на данных, в том числе и те, которые создаются в PowerApps. Эти данные хранятся в *источниках данных*. Вы переносите их в приложение при создании *подключения*. Для подключения используется определенный *соединитель*, который обеспечивает обмен данными с источником данных. В PowerApps есть соединители для многих популярных служб и локальных источников данных, включая SharePoint, SQL Server, Office 365, Salesforce, Twitter и другие. Чтобы начать добавлять данные в приложение, ознакомьтесь со статьей [Добавление подключения к данным в PowerApps](add-data-connection.md).

В таблице ниже содержатся ссылки на статьи с дополнительными сведениями о самых популярных соединителях. Полный список соединителей см. в разделе [Все соединители](#all-connectors).

| &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; |
| --- | --- | --- | --- | --- |
| ![Common Data Service](./media/connections-list/cdm.png) |[**Common Data Service**](../common-data-service/data-platform-intro.md) |&nbsp; |![Outlook в Office 365](./media/connections-list/office365.png) |[**Outlook в Office 365**](connections/connection-office365-outlook.md) |
| ![SharePoint](./media/connections-list/sharepoint.png) |[**SharePoint**](connections/connection-sharepoint-online.md) |&nbsp; |![Excel](./media/connections-list/excel.png) |[**Excel**](connections/connection-excel.md) |
| ![SQL Server](./media/connections-list/sql.png) |[**SQL Server**](connections/connection-azure-sqldatabase.md) |&nbsp; |![OneDrive для бизнеса](./media/connections-list/onedrive.png) |[**OneDrive для бизнеса**](connections/cloud-storage-blob-connections.md) |
| ![Dynamics 365.](./media/connections-list/dynamics-365.png) |[**Dynamics 365**](connections/connection-dynamics-crmonline.md) |&nbsp; |![OneDrive](./media/connections-list/onedrive.png) |[**OneDrive**](connections/cloud-storage-blob-connections.md) |
| ![Пользователи Office 365](./media/connections-list/office365.png) |[**Пользователи Office 365**](connections/connection-office365-users.md) |&nbsp; |![Dropbox](./media/connections-list/dropbox.png) |[**Dropbox**](connections/cloud-storage-blob-connections.md) |

## <a name="types-of-connectors"></a>Типы соединителей
Существует два типа соединителей для PowerApps: *стандартные соединители* (перечисленные выше) и *настраиваемые соединители*. Если вы подключаетесь к источнику данных, поддерживаемый службой PowerApps при использовании стандартного соединителя, используйте такой соединитель. Чтобы подключиться к другому источнику, например созданной вами службе, см. инструкции по [регистрации и использованию настраиваемых соединителей](../canvas-apps/register-custom-api.md).

Поведение стандартных соединителей отличается в зависимости от типа источника данных, к которому они подключаются, и как этот источник данных возвращает данные:

* Некоторые соединители работают с табличными источниками данных, включая SharePoint, SQL Server и Excel. Если используются такие источники, данные возвращаются в PowerApps в виде таблицы. PowerApps использует собственные функции для работы с данными, такие как [Patch()](functions/function-patch.md), [Collect()](functions/function-clear-collect-clearcollect.md), [Update()](functions/function-update-updateif.md) и т. д. Табличные данные также удобно использовать в формах и коллекциях, где поле таблицы отображается как поле в коллекции или форме. Дополнительные сведения см. в следующих статьях:

    [Общие сведения об источниках данных в PowerApps](working-with-data-sources.md)

    [Создание приложения на основе данных Excel](get-started-create-from-data.md)

    [Создание приложения с нуля](get-started-create-from-blank.md)

    > [!NOTE]
> Чтобы подключиться к данным в Excel, необходимо разместить книгу в службе облачного хранения, например OneDrive. Дополнительные сведения см. в статье о [подключении к облачным хранилищам из PowerApps](connections/cloud-storage-blob-connections.md).

* Другие соединители работают с источниками данных на основе функций, включая Twitter, Facebook и Office 365 Outlook. Если используются такие источники, данные возвращаются в PowerApps при вызове определенных функций в соответствующей службе. Например, при работе с соединителем Twitter вызывается метод `Twitter.MyFollowers()` для получения списка подписчиков. Вы также можете использовать эти данные в форме или коллекции, но это немного сложнее, чем работа с табличными данными. Дополнительные сведения см. в инструкциях по [подключению к Twitter из PowerApps](connections/connection-twitter.md).

## <a name="all-connectors"></a>Все соединители
В следующей таблице перечислены все соединители. Дополнительные сведения о каждом соединителе см. в [справочнике по соединителям Майкрософт](https://docs.microsoft.com/connectors/). Для соединителей уровня "Премиум" требуется план 1 или 2 службы PowerApps. Дополнительные сведения см. на странице [планов PowerApps](https://powerapps.microsoft.com/pricing/).

| &nbsp; | &nbsp; |
| --- | --- |
| 10to8-Appointment Scheduling<br>Act!<br>Adobe Creative Cloud ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Adobe Sign<br>Amazon Redshift ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Apache Impala ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>appFigures<br>Утверждения<br>Asana<br>AWeber ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Azure AD<br>Azure Application Insights<br>Автоматизация Azure<br>Хранилище BLOB-объектов Azure<br>Azure Cosmos DB<br>Azure Data Lake<br>Сетка событий Azure<br>Публикации в службе "Сетка событий Azure"<br>Хранилище файлов Azure<br>Azure Log Analytics<br>Сборщик данных Azure Log Analytics<br>Azure Queues<br>Azure Resource Manager<br>Хранилище таблиц Azure<br>Basecamp 2<br>Basecamp 3<br>Benchmark Email ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Bing Maps<br>API Bing для поиска<br>Bitbucket ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Bitly<br>Bizzy (H3 Solutions, Inc.)<br>Blogger<br>Box<br>bttn<br>Buffer<br>Calendly ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Campfire<br>Capsule CRM ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Chatter ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Cognito Forms<br>Common Data Service ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>API компьютерного зрения<br>Преобразование содержимого<br>Content Moderator<br>DB2 ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Disqus<br>DocFusion365 — SP ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>DocuSign ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Dropbox<br>Dynamics 365.<br>Dynamics 365 for Financials<br>Dynamics for Operations<br>Dynamics NAV<br>Easy Redmine ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Elastic Forms<br>Концентраторы событий<br>Eventbrite ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Excel<br>API-интерфейс для распознавания лиц<br>Facebook<br>Файловая система<br>Flic<br>FlowForma ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>FreshBooks ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Freshdesk<br>Freshservice ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>FTP<br>GitHub<br>Gmail<br>Календарь Google<br>Контакты Google<br>Google Drive<br>Таблицы Google<br>Google Tasks<br>GoToMeeting ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>GoToTraining ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>GoToWebinar ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Harvest ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>HelloSign ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>HipChat<br>HTTP с Azure AD ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Informix; ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Infusionsoft ![Соединитель уровня "Премиум"](./media/connections-list/premium.png) |Inoreader<br>Insightly<br>Instagram<br>Instapaper<br>Intercom<br>JIRA ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>JotForm ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>LeanKit ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>LinkedIn<br>LiveChat ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>LUIS<br>Почта<br>MailChimp ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Mandrill ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Средняя<br>Microsoft Forms<br>Microsoft StaffHub<br>Microsoft Teams<br>Microsoft Translator<br>MSN Weather<br>Muhimbi PDF<br>MySQL ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Nexmo ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Уведомления<br>Bookings в Office 365<br>Группы Office 365<br>Outlook в Office 365<br>Пользователи Office 365<br>Office 365 Видео<br>OneDrive<br>OneDrive для бизнеса<br>OneNote (Business)<br>База данных Oracle ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Outlook Customer Manager<br>Задачи Outlook<br>Outlook.com<br>PagerDuty<br>Parserr<br>Paylocity ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Pinterest<br>Pipedrive ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Проверка данных Pitney Bowes ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Pivotal Tracker<br>Планировщик<br>Plivo ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>PostgreSQL ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Power BI<br>Уведомление PowerApps ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Project Online<br>Redmine<br>RSS-канал<br>Salesforce ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>SendGrid<br>Служебная шина<br>SFTP<br>SharePoint<br>Skype для бизнеса<br>Slack<br>SmartSheet<br>SMTP<br>SparkPost<br>SQL Server<br>Stripe ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>SurveyMonkey ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Teamwork Projects ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Teradata ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Анализ текста<br>Todoist<br>Toodledo<br>Trello<br>Twilio<br>Twitter<br>TypeForm<br>UserVoice ![Соединитель уровня "Премиум"](./media/connections-list/premium.png)<br>Индексатор видео<br>Vimeo<br>Visual Studio Team Services<br>WebMerge<br>WordPress<br>Wunderlist<br>Yammer<br>YouTube<br>Zendesk ![Соединитель уровня "Премиум"](./media/connections-list/premium.png) |

Если у вас есть вопросы по конкретному соединителю, задайте их на [форуме PowerApps](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1). Если у вас есть предложения по новым соединителям или рекомендации по улучшению, поделитесь ими на странице [PowerApps Ideas](https://powerusers.microsoft.com/t5/PowerApps-Ideas/idb-p/PowerAppsIdeas).