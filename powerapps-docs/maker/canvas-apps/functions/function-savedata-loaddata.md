---
title: Функции SaveData и LoadData | Документация Майкрософт
description: Справочные сведения, включая описание синтаксиса, относительно функций SaveData и LoadData в PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5aa9992b9371724c77bcc1d2baf439bb2d7b9dab
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42864334"
---
# <a name="savedata-and-loaddata-functions-in-powerapps"></a>Функции SaveData и LoadData в PowerApps
Сохраняют и загружают [коллекцию](../working-with-data-sources.md#collections).

## <a name="description"></a>Описание
Функция **SaveData** сохраняет коллекцию под определенным именем для дальнейшего использования.  

Функция **LoadData** загружает коллекцию с определенным именем, сохраненную ранее с помощью функции **SaveData**. С помощью этой функции нельзя загрузить коллекцию из другого источника.  

Функция **LoadData** не создает новую коллекцию, она лишь заполняет данными существующую. Сначала необходимо создать коллекцию с правильными [столбцами](../working-with-tables.md#columns) с помощью функции **[Collect](function-clear-collect-clearcollect.md)**.

Хранилище данных зашифровано и располагается в закрытой папке на локальном устройстве, изолированной от других пользователей и приложений.  

## <a name="syntax"></a>Синтаксис
**SaveData**(*коллекция*, *имя*)<br>**LoadData**( *коллекция*, *имя* [, *IgnoreNonexistentFile* ])

* *коллекция* — обязательный аргумент.  Коллекция, которую требуется сохранить или загрузить.
* *имя* — обязательный аргумент.  Название хранилища. Для сохранения и загрузки одного набора данных необходимо использовать одинаковое имя. Пространство имен не используется совместно с другими приложениями и пользователями.
* *IgnoreNonexistentFile* — необязательный параметр. Логическое значение (**true**/**false**), указывающее, что делать функции **LoadData**, если ей не удается найти соответствующий файл: отображать или пропускать ошибки. Если указать значение **false**, ошибки будут отображаться. Если указать значение **true**, ошибки будут игнорироваться, что полезно для сценариев в автономном режиме работы. Функция **SaveData** может создать файл, если устройство находится в автономном режиме (то есть, если состояние **Connection.Connected** имеет значение **false**).

## <a name="examples"></a>Примеры

| Формула | Описание | Возвращаемый результат |
| --- | --- | --- |
| **If(Connection.Connected, ClearCollect(LocalTweets, Twitter.SearchTweet("PowerApps", {maxResults: 100})),LoadData(LocalTweets, "Tweets", true))** |Если устройство подключено, загрузите коллекцию LocalTweets из службы Twitter. В противном случае — загрузите коллекцию из кэша локальных файлов. |Содержимое отображается независимо от того, в каком режиме находится устройство: оперативном или автономном. |
| **SaveData(LocalTweets, "Tweets")** |Сохраняет коллекцию LocalTweets в кэше локальных файлов на устройстве. |Данные сохраняются локально, поэтому функция **LoadData** может загрузить их в коллекцию. |

