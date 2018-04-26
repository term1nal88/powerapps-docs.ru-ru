---
title: Функция Shuffle | Документация Майкрософт
description: Справочные сведения, включая синтаксис и пример, для функции Shuffle в PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 6d981c410b22dd9db52cdf077a00e6eaae83be75
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="shuffle-function-in-powerapps"></a>Функция Shuffle в PowerApps
Случайным образом изменяет порядок [записей](../working-with-tables.md#records) в [таблице](../working-with-tables.md).

## <a name="description"></a>Описание
Функция **Shuffle** изменяет порядок записей в таблице (перемешивает таблицу).

Функция **Shuffle** возвращает таблицу, в которой столько же [столбцов](../working-with-tables.md#columns) и строк, сколько в таблице-аргументе.

## <a name="syntax"></a>Синтаксис
**Shuffle**( *таблица* )

* *Table* — обязательный аргумент.  Таблица для перемешивания.

## <a name="example"></a>Пример
Если вы храните информацию об игральных картах в [коллекции](../working-with-data-sources.md#collections) с именем **Deck**, то эта формула вернет копию коллекции, которая будет перемешана случайным образом.

**Shuffle(Deck)**

