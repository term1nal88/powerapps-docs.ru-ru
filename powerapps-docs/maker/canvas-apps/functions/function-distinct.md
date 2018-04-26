---
title: Функция Distinct | Документация Майкрософт
description: Справочные сведения о функции Distinct в PowerApps, включая описание синтаксиса и примеры.
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
ms.openlocfilehash: 101c28f2b4ac8135a9b4def9421f886f373105bf
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
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

