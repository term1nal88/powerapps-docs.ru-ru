---
title: "Функция Len | Документация Майкрософт"
description: "Справочные сведения, включая описание синтаксиса и примеры, относительно функции Len в PowerApps"
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
ms.openlocfilehash: 06f8e7a80adc7a2175f2da7ab98fb1966d8cf015
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2017
---
# <a name="len-function-in-powerapps"></a>Функция Len в PowerApps
Возвращает длину текстовой строки.

## <a name="description"></a>Описание
Если в качестве аргумента указать одну строку, функция вернет длину в виде числа.  Если указать [таблицу](../working-with-tables.md) из одного столбца, содержащую строки, функция вернет таблицу из одного столбца с длинами каждой из строк. Таблицу с несколькими столбцами можно преобразовать в таблицу с одним столбцом, как описано в статье об [использовании таблиц](../working-with-tables.md).

Если указать [пустую](function-isblank-isempty.md) строку, функция **Len** вернет 0.

## <a name="syntax"></a>Синтаксис
**Len**(*строка*)

* *строка* — обязательный аргумент. Строка, длину которой требуется определить.

**Len**(*таблица_из_одного_столбца*)

* *SingleColumnTable* — обязательный аргумент. Таблица из одного столбца со строками, длины которых нужно определить.

## <a name="examples"></a>Примеры
### <a name="single-string"></a>Одна строка
Во всех примерах этого раздела в качестве [источника данных](../working-with-data-sources.md) используется элемент управления для ввода текста под названием **Author** (Автор), содержащий строку "E. И. Иванов".

| Формула | Описание | Возвращаемый результат |
| --- | --- | --- |
| **Len(Author.Text)** |Определяет длину строки в поле **Author**. |14 |
| **Len( "" )** |Определяет длину пустой строки. |0 |

### <a name="single-column-table"></a>Для таблицы с одним столбцом
В первом примере этого раздела используется источник данных под названием **People** (Люди), содержащий указанные ниже значения.

![](media/function-len/people-table.png)

| Формула | Описание | Возвращаемый результат |
| --- | --- | --- |
| **Len(ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;))** |В [столбце](../working-with-tables.md#columns) **Address** (Адрес) таблицы **People** (Люди):<br><ul><li>Определяет длину каждой строки.</li><li>Возвращает таблицу из одного столбца, содержащего длины каждой из строк.</li> |<style> img { max-width: none } </style> ![](media/function-len/people-table-len.png) |
| **Len(["Hello", "to the", "World", ""])** |В столбце **[Value](function-value.md)** (Значение) встроенной таблицы:<br><ul><li>Определяет длину каждой строки.</li><li>Возвращает таблицу из одного столбца, содержащего длины каждой из строк.</li> |![](media/function-len/people-table-len-inline.png) |

