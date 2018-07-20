---
title: Функция Shuffle | Документация Майкрософт
description: Справочные сведения, включая синтаксис и пример, для функции Shuffle в PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 39307e9c7b3de7bfae151709827c409fcc7087ad
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2018
ms.locfileid: "39014243"
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

