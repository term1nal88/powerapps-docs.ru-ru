---
title: Функция Distinct | Документация Майкрософт
description: Справочные сведения о функции Distinct в PowerApps, включая описание синтаксиса и примеры.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 8b482972b7e209c8cca98aae44389c133d5d4dcf
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2018
ms.locfileid: "39020338"
---
# <a name="distinct-function-in-powerapps"></a>Функция Distinct в PowerApps
Эта функция вычисляет итоговые значения для [записей](../working-with-tables.md#records) [таблицы](../working-with-tables.md), удаляя дубликаты.

## <a name="description"></a>Описание
Функция **Distinct** вычисляет формулу для каждой записи таблицы. Функция **Distinct** возвращает таблицу с одним столбцом, содержащую результаты без повторяющихся значений.  

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

## <a name="syntax"></a>Синтаксис
**Distinct**( *Таблица*, *Формула* )

* *Table* — обязательный аргумент.  Таблица для оценки.
* *Formula* — обязательный аргумент.  Формула, вычисляемая для каждой записи.

## <a name="example"></a>Пример
Если бы у вас была таблица **Employees**, содержащая столбец **Department**, то приведенная ниже функция вывела бы список уникальных названий отделов в этом столбце, независимо от того, сколько раз каждое название в нем указано.

**Distinct(Employees, Department)**

