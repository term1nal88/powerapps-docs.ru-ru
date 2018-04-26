---
title: Общие сведения о подключении к Excel | Документация Майкрософт
description: Отображение и обновление данных в Excel при сохранении книги в учетной записи облачного хранилища и последующем подключении к данным из вашего приложения.
documentationcenter: ''
author: lancedMicrosoft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/02/2016
ms.author: lanced
ms.openlocfilehash: e8bdc3f7bbfa7fdd55e9a5273c084d0aa870cf6d
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="connect-to-excel-from-powerapps"></a>Подключение к Excel из PowerApps
![Excel](./media/connection-excel/excelicon.png)

Excel — это *вид* подключения. Для отображения данных Excel в вашем приложении сделайте следующее:

1. [Отформатируйте данные Excel в виде таблицы](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-E81AA349-B006-4F8A-9806-5AF9DF0AC664).
2. Поместите файл Excel в учетную запись облачного хранилища, например Box, Dropbox, Google Диск, OneDrive или OneDrive для бизнеса.
3. [Подключитесь к учетной записи облачного хранилища](../add-manage-connections.md), а затем добавьте таблицу Excel в качестве источника данных.
4. Для отображения этой информации в вашем приложении можно выполнить [автоматическое создание приложения](../get-started-create-from-data.md) или добавить и настроить, например, управление **коллекцией**.

> [!NOTE]
> После подключения к таблице Excel из PowerApps эта служба создаст новый столбец с именем **\_* PowerAppsId_*** и уникальным идентификатором для каждой строки таблицы Excel.

В разделе с [общими сведениями о подключении к облачному хранилищу](cloud-storage-blob-connections.md) показано, как добавить подключение, добавить таблицу Excel в качестве источника данных и использовать данные Excel в приложении.

Сведения о подключении к данным других типов см. в [списке подключений для PowerApps](../connections-list.md).

### <a name="known-limitations"></a>Известные ограничения
[Просмотрите эти ограничения](cloud-storage-blob-connections.md#sharing-excel-tables) для совместного использовании данных Excel в организации.

