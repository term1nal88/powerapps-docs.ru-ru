---
title: "Функция Revert | Документация Майкрософт"
description: "Справочные сведения, включая описание синтаксиса и пример, относительно функции Revert в PowerApps"
services: 
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/21/2015
ms.author: gregli
ms.openlocfilehash: e61566077ccdf9f3b2913ec0293868c1863c26fa
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2018
---
# <a name="revert-function-in-powerapps"></a>Функция Revert в PowerApps
Обновляет содержимое и удаляет ошибки для [записей](../working-with-tables.md#records) в [источнике данных](../working-with-data-sources.md).

## <a name="description"></a>Описание
Функция **Revert** обновляет весь источник данных или одну запись в нем. Вы сможете увидеть изменения, внесенные другими пользователями.

Для записей, для которых выполняется функция **Revert**, также удаляются все ошибки в [таблице](../working-with-tables.md), возвращенные функцией **[Errors](function-errors.md)**.

Если функция **[Errors](function-errors.md)** сообщает о конфликте после выполнения функции **[Patch](function-patch.md)** или другой операции с данными, выполните для записи функцию **Revert**, чтобы повторно применить изменение к конфликтующей версии.

Функция **Revert** не возвращает никакого значения. Ее можно использовать только в [формуле поведения](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Синтаксис
**Revert**(*источник_данных*[, *запись*])

* *источник_данных* — обязательный аргумент. Это источник данных, который требуется восстановить.
* *запись* — необязательный аргумент.  Запись, которую требуется восстановить.  Если запись не указана, выполняется восстановление всего источника.

## <a name="example"></a>Пример
В этом примере восстанавливается источник данных под названием **IceCream**, который начинается со значений из следующей таблицы:

![](media/function-revert/icecream.png)

Пользователь на другом устройстве изменяет значение свойства **Quantity** записи **Strawberry** на **400**.  Примерно в тот же момент вы меняете значение того же свойства в той же записи на **500**, не зная о параллельном изменении.

Чтобы обновить запись, вы используете функцию **[Patch](function-patch.md)**:<br>
**Patch( IceCream, First( Filter( IceCream, Flavor = "Strawberry" ) ), { Quantity: 500 } )**

В таблице **[Errors](function-errors.md)** вы обнаруживаете ошибку:

| Запись | [Столбец](../working-with-tables.md#columns) | Сообщение | Ошибка |
| --- | --- | --- | --- |
| **{ID: 1, Flavor: "Strawberry", Quantity: 300}** |*пустое значение* |**"Запись, которую вы пытаетесь изменить, была изменена другим пользователем.  Восстановите ее и повторите попытку".** |**ErrorKind.Conflict** |

Для записи в столбце **Ошибка** вы можете воспользоваться кнопкой **Reload** (Перезагрузить), у которой для свойства **[OnSelect](../controls/properties-core.md)** установлена следующая формула:<br>
**Revert( IceCream, First( Filter( IceCream, Flavor = "Strawberry" ) ) )**

После нажатия кнопки **Reload** таблица **[ошибок](function-errors.md)** [очищается](function-isblank-isempty.md), а для свойства **Strawberry** загружается новое значение:

![](media/function-revert/icecream-after.png)

Вы применяете это изменение, перезаписывая предыдущее, и операция выполняется успешно, так как конфликт устранен.

![](media/function-revert/icecream-success.png)

