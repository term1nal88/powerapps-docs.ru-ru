---
title: Функции First, FirstN, Last и LastN | Документация Майкрософт
description: Справочные сведения о функциях First, FirstN, Last и LastN в PowerApps, включая описание синтаксиса и примеры.
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
ms.openlocfilehash: 947a6c369c41b1ff67c611fa734f927227dde991
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="first-firstn-last-and-lastn-functions-in-powerapps"></a>Функции First, FirstN, Last и LastN в PowerApps
Возвращает первый или последний набор [записей](../working-with-tables.md#records) таблицы.

## <a name="description"></a>Описание
Функция **First** возвращает первую запись [таблицы](../working-with-tables.md).

Функция **FirstN** возвращает первый набор записей таблицы; второй аргумент задает количество возвращаемых записей.

Функция **Last** возвращает последнюю запись таблицы.

Функция **LastN** возвращает последний набор записей таблицы; второй аргумент задает количество возвращаемых записей.

Функции **First** и **Last** возвращают одну запись.  Функции **FirstN** и **LastN** возвращают таблицу, даже если указать только одну запись.

[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Синтаксис
**First**( *Таблица* )<br>**Last**( *Таблица* )

* *Таблица* — обязательный аргумент. Таблица, для которой выполняется операция.

**FirstN**( *Таблица* [, *Число_записей* ] )<br>**LastN**( *Таблица* [, *Число_записей* ] )

* *Table* — обязательный аргумент. Таблица, для которой выполняется операция.
* *Число_записей* — необязательный аргумент.  Количество возвращаемых записей. Если не указать этот аргумент, то функция возвратит одну запись.

## <a name="examples"></a>Примеры
Эта формула возвращает первую запись из таблицы с именем **Employees**:<br>
**First(Employees)**

Эта формула возвращает последние 15 записей из таблицы с именем **Employees**:<br>
**LastN(Employees, 15)**

