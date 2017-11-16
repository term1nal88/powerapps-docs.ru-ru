---
title: "Функция Shuffle | Документация Майкрософт"
description: "Справочные сведения, включая синтаксис и пример, для функции Shuffle в PowerApps"
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
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 672caee3b683bb0222b15a65cdad4edce78c4fe4
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2017
---
# <a name="shuffle-function-in-powerapps"></a>Функция Shuffle в PowerApps
Случайным образом изменяет порядок [записей](../working-with-tables.md#records) в [таблице](../working-with-tables.md).

## <a name="description"></a>Описание
Функция **Shuffle** изменяет порядок записей в таблице (перемешивает таблицу).

Функция **Shuffle** возвращает таблицу, в которой столько же [столбцов](../working-with-tables.md#columns) и строк, сколько в таблице-аргументе.

## <a name="syntax"></a>Синтаксис
**Shuffle**( *таблица* )

* *Table* — обязательный аргумент.  Таблица для перемешивания.

## <a name="example"></a>Пример
Если вы храните информацию об игральных картах в [коллекции](../working-with-data-sources.md#collections) с именем **Deck**, то эта формула вернет копию коллекции, которая будет перемешана случайным образом.

**Shuffle(Deck)**

