---
title: Общие сведения о соединителях | Документация Майкрософт
description: Обзор всех доступных подключений, которые можно использовать для создания приложений
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/28/2017
ms.author: lanced
ms.openlocfilehash: 15da6ed2ce6b44c17645ac11d1b049b95e157703
ms.sourcegitcommit: 47be38a23c96ba7478fd777065f5db41181af40b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2018
ms.locfileid: "39164755"
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
Полный список наших соединителей см. в [справочнике по соединителям Майкрософт](https://docs.microsoft.com/connectors/). Для соединителей уровня "Премиум" требуется план 1 или 2 службы PowerApps. Дополнительные сведения см. на странице [планов PowerApps](https://powerapps.microsoft.com/pricing/).


Если у вас есть вопросы по конкретному соединителю, задайте их на [форуме PowerApps](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1). Если у вас есть предложения по новым соединителям или рекомендации по улучшению, поделитесь ими на странице [PowerApps Ideas](https://powerusers.microsoft.com/t5/PowerApps-Ideas/idb-p/PowerAppsIdeas).
