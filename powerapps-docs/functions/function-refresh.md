---
title: "Функция Refresh | Документация Майкрософт"
description: "Справочные сведения, включая описание синтаксиса и пример, для функции Refresh в PowerApps"
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
ms.openlocfilehash: 57c591e134eafeae422289ad47afc8952ff67110
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2017
---
# <a name="refresh-function-in-powerapps"></a>Функция Refresh в PowerApps
Обновляет [записи](../working-with-tables.md#records) [источника данных](../working-with-data-sources.md).

## <a name="description"></a>Описание
Функция **Refresh** получает свежую копию источника данных.  Вы сможете увидеть изменения, внесенные другими пользователями.

Функция **Refresh** не возвращает никакого значения, и ее можно использовать только в [формулах управления поведением](../working-with-formulas-in-depth.md#behavior-formulas).

## <a name="syntax"></a>Синтаксис
****Refresh*(* источник_данных )

* *источник_данных* — обязательный аргумент. Это источник данных, который требуется обновить.

## <a name="example"></a>Пример
В этом примере обновляется источник данных под названием **IceCream**, который начинается с таких значений:

![](media/function-refresh/icecream.png)

Пользователь на другом устройстве изменяет значение **Quantity** в записи **Strawberry** на **400**.  Вы не увидите этого изменения, пока не будет выполнена следующая формула:

**Refresh(IceCream)**

После ее выполнения в коллекциях, связанных с источником данных **IceCream**, появится обновленное значение **Strawberry**:

![](media/function-refresh/icecream-after.png)

