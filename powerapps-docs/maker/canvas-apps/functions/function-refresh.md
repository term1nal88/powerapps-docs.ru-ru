---
title: Функция Refresh | Документация Майкрософт
description: Справочные сведения, включая описание синтаксиса и пример, для функции Refresh в PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/21/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 2999665e5882245b594468b6babe67be575c5c1e
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42843604"
---
# <a name="refresh-function-in-powerapps"></a>Функция Refresh в PowerApps
Обновляет [записи](../working-with-tables.md#records) [источника данных](../working-with-data-sources.md).

## <a name="description"></a>Описание
Функция **Refresh** получает свежую копию источника данных.  Вы сможете увидеть изменения, внесенные другими пользователями.

Функция **Refresh** не возвращает никакого значения, и ее можно использовать только в [формулах управления поведением](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Синтаксис
**Refresh**( *источник_данных* )

* *источник_данных* — обязательный аргумент. Это источник данных, который требуется обновить.

## <a name="example"></a>Пример
В этом примере обновляется источник данных под названием **IceCream**, который начинается с таких значений:

![](media/function-refresh/icecream.png)

Пользователь на другом устройстве изменяет значение **Quantity** в записи **Strawberry** на **400**.  Вы не увидите этого изменения, пока не будет выполнена следующая формула:

**Refresh(IceCream)**

После ее выполнения в коллекциях, связанных с источником данных **IceCream**, появится обновленное значение **Strawberry**:

![](media/function-refresh/icecream-after.png)

