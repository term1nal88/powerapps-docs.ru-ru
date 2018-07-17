---
title: Общие сведения о подключении к Excel | Документация Майкрософт
description: Отображение и обновление данных в Excel при сохранении книги в учетной записи облачного хранилища и последующем подключении к данным из вашего приложения.
author: lancedMicrosoft
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 10/02/2016
ms.author: lanced
ms.openlocfilehash: e6ab6d7e5c7cdf6c166660c1e905f3d62531c3ed
ms.sourcegitcommit: 76ffec3b4d9c18a01f19c583435541ae165a8234
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37864245"
---
# <a name="connect-to-excel-from-powerapps"></a>Подключение к Excel из PowerApps
![Excel](./media/connection-excel/excelicon.png)

Excel — это *вид* подключения. Для отображения данных Excel в вашем приложении сделайте следующее:

1. [Отформатируйте данные Excel в виде таблицы](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-E81AA349-B006-4F8A-9806-5AF9DF0AC664).
2. Поместите файл Excel в учетную запись облачного хранилища, например Box, Dropbox, Google Диск, OneDrive или OneDrive для бизнеса.
3. [Подключитесь к учетной записи облачного хранилища](../add-manage-connections.md), а затем добавьте таблицу Excel в качестве источника данных.
4. Для отображения этой информации в вашем приложении можно выполнить [автоматическое создание приложения](../get-started-create-from-data.md) или добавить и настроить, например, управление **коллекцией**.

> [!NOTE]
> После подключения к таблице Excel из PowerApps эта служба создаст новый столбец с именем **\_PowerAppsId_** и уникальным идентификатором для каждой строки таблицы Excel.

В разделе с [общими сведениями о подключении к облачному хранилищу](cloud-storage-blob-connections.md) показано, как добавить подключение, добавить таблицу Excel в качестве источника данных и использовать данные Excel в приложении.

Сведения о подключении к данным других типов см. в [списке подключений для PowerApps](../connections-list.md).

### <a name="known-limitations"></a>Известные ограничения
[Просмотрите эти ограничения](cloud-storage-blob-connections.md#sharing-excel-tables) для совместного использовании данных Excel в организации.

