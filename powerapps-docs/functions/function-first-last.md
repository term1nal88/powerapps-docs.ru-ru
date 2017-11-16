---
title: "Функции First, FirstN, Last и LastN | Документация Майкрософт"
description: "Справочные сведения о функциях First, FirstN, Last и LastN в PowerApps, включая описание синтаксиса и примеры."
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
ms.openlocfilehash: 0a056aa20532ffe6e2e8ae502e67b5b27d134839
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2017
---
# <a name="first-firstn-last-and-lastn-functions-in-powerapps"></a>Функции First, FirstN, Last и LastN в PowerApps
Возвращает первый или последний набор [записей](../working-with-tables.md#records) таблицы.

## <a name="description"></a>Описание
Функция **First** возвращает первую запись [таблицы](../working-with-tables.md).

Функция **FirstN** возвращает первый набор записей таблицы; второй аргумент задает количество возвращаемых записей.

Функция **Last** возвращает последнюю запись таблицы.

Функция **LastN** возвращает последний набор записей таблицы; второй аргумент задает количество возвращаемых записей.

Функции **First** и **Last** возвращают одну запись.  Функции **FirstN** и **LastN** возвращают таблицу, даже если указать только одну запись.

[!INCLUDE [delegation-no](../../includes/delegation-no.md)]

## <a name="syntax"></a>Синтаксис
**First**( *Таблица* )<br>**Last**( *Таблица* )

* *Таблица* — обязательный аргумент. Таблица, с которой выполняются операции.

**FirstN**( *Таблица* [, *Число_записей* ] )<br>**LastN**( *Таблица* [, *Число_записей* ] )

* *Table* — обязательный аргумент. Таблица, с которой выполняются операции.
* *Число_записей* — необязательный аргумент.  Количество возвращаемых записей. Если не указать этот аргумент, то функция возвратит одну запись.

## <a name="examples"></a>Примеры
Эта формула возвращает первую запись из таблицы с именем **Employees**:<br>
**First(Employees)**

Эта формула возвращает последние 15 записей из таблицы с именем **Employees**:<br>
**LastN(Employees, 15)**

