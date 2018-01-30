---
title: "Функции Concat и Concatenate | Документация Майкрософт"
description: "Справочные сведения о функциях Concat и Concatenate в PowerApps, включая описание синтаксиса и примеры."
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
ms.date: 08/28/2017
ms.author: gregli
ms.openlocfilehash: 2277d7f9252f8ce4df7552b6eb5f7bf4ac94ff63
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2018
---
# <a name="concat-and-concatenate-functions-in-powerapps"></a>Функции Concat и Concatenate в PowerApps
Объединяют отдельные строки текста и строки в [таблицах](../working-with-tables.md).

## <a name="description"></a>Описание
Функция **Concat** объединяет результат формулы, примененной ко всем [записям](../working-with-tables.md#records) таблицы, в результате чего получается одна строка. Используйте эту функцию для объединения строк таблицы, как функция **[Sum](function-aggregates.md)** делает с числами.

[!INCLUDE [record-scope](../includes/record-scope.md)]

Используйте функцию **[Split](function-split.md)**, чтобы разбить строку на таблицу с подстроками.

Функция **Concatenate** объединяет сочетание отдельных строк и таблицу из одного столбца со строками. При использовании с отдельными строками эта функция действует как [оператор](operators.md) **&**. Формулу, которая включает в себя функцию **[ShowColumns](function-table-shaping.md)**, можно использовать для создания из таблицы с несколькими столбцами таблицы с одним столбцом.

## <a name="syntax"></a>Синтаксис
**Concat**( *Table*, *Formula* )

* *Table* — обязательный аргумент.  Таблица, для которой выполняется операция.
* *Formula* — обязательный аргумент.  Формула, которую необходимо применить к записям таблицы.

**Concatenate**( *Строка1* [, *Строка2*, ...] )

* *Строка* — обязательные аргументы.  Сочетание отдельных строк или таблица из одного столбца со строками.

## <a name="examples"></a>Примеры
#### <a name="concat"></a>Concat
1. Добавьте элемент управления **[Кнопка](../controls/control-button.md)** и задайте следующую формулу в качестве значения свойства **[OnSelect](../controls/properties-core.md)**:
   
    **Collect(Products, {String:"Violin", Wind:"Trombone", Percussion:"Bongos"}, {String:"Cello", Wind:"Trumpet", Percussion:"Tambourine"})**
2. Нажмите клавишу F5, а затем нажмите клавишу Esc, чтобы вернуться в рабочую область конструирования.
3. Добавьте элемент управления **[Метка](../controls/control-text-box.md)** и задайте в качестве значения свойства **[Text](../controls/properties-core.md)** следующую формулу:
   
    **Concat(Products, String & " ")**
   
    Метка отобразит **Violin Cello**.

#### <a name="concatenate"></a>Concatenate
1. Добавьте элемент управления **[Текстовое поле](../controls/control-text-input.md)** и назовите его **AuthorName**.
2. Добавьте элемент управления **[Метка](../controls/control-text-box.md)** и задайте в качестве значения свойства **[Text](../controls/properties-core.md)** следующую формулу:<br>
   **Concatenate("By ", AuthorName.Text)**
3. Введите свое имя вместо **AuthorName**.
   
    Метка отобразит ваше имя после **By**.

Если у вас была таблица **Employees**, содержавшая столбцы **FirstName** и **LastName**, то данная формула объединит данные из всех строк этих столбцов.
<br>**Concatenate(Employees.FirstName, " ", Employees.LastName)**

