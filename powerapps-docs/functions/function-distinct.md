---
title: "Функция Distinct | Документация Майкрософт"
description: "Справочные сведения о функции Distinct в PowerApps, включая описание синтаксиса и примеры."
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
ms.openlocfilehash: b4e2a7c44696a57d01db5ac39da65ad782f0edac
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2018
---
# <a name="distinct-function-in-powerapps"></a>Функция Distinct в PowerApps
Эта функция вычисляет итоговые значения для [записей](../working-with-tables.md#records) [таблицы](../working-with-tables.md), удаляя дубликаты.

## <a name="description"></a>Описание
Функция **Distinct** вычисляет формулу для каждой записи таблицы. Функция **Distinct** возвращает таблицу с одним столбцом, содержащую результаты без повторяющихся значений.  

[!INCLUDE [record-scope](../includes/record-scope.md)]

## <a name="syntax"></a>Синтаксис
**Distinct**( *Таблица*, *Формула* )

* *Table* — обязательный аргумент.  Таблица для оценки.
* *Formula* — обязательный аргумент.  Формула, вычисляемая для каждой записи.

## <a name="example"></a>Пример
Если бы у вас была таблица **Employees**, содержащая столбец **Department**, то приведенная ниже функция вывела бы список уникальных названий отделов в этом столбце, независимо от того, сколько раз каждое название в нем указано.

**Distinct(Employees, Department)**

