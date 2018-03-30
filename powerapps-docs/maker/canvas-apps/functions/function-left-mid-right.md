---
title: Функции Left, Mid и Right | Документация Майкрософт
description: Справочные сведения, включая синтаксис и примеры, для функций Left, Mid и Right в PowerApps
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 2cf54b1225578b2bb2bdefa8c0bd02dc0c9c0283
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="left-mid-and-right-functions-in-powerapps"></a>Функции Left, Mid и Right в PowerApps
Извлекают левую, среднюю или правую часть текстовой строки.

## <a name="description"></a>Описание
Функции **Left**, **Mid** и **Right** возвращают часть строки.

* **Left** возвращает начальные символы строки.
* **Mid** возвращает средние символы строки.
* **Right** возвращает конечные символы строки.

При указании в качестве аргумента одной строки функция возвращает запрошенную часть этой строки. Если в качестве аргумента указана [таблица](../working-with-tables.md) из одного столбца со строками, функция возвращает таблицу из одного столбца с запрошенными частями соответствующих строк исходной таблицы. Если указана таблица с несколькими столбцами, ее можно преобразовать в таблицу из одного столбца, как указано в разделе [Работа с таблицами](../working-with-tables.md).

Если начальная позиция отрицательна или за пределами строки, **Mid** возвращает *пустое значение*.  Проверить длину строки можно с помощью функции **[Len](function-len.md)**. При запросе большего количества символов, чем есть в строке, функция вернет максимальное возможное количество символов.

## <a name="syntax"></a>Синтаксис
**Left**( *строка*, *количество_символов* )<br>**Mid**( *строка*, *начальная_позиция*, *количество_символов* )<br>**Right**( *строка*, *количество_символов* )

* *Строка* — обязательный аргумент. Строка, из которой нужно извлечь результат.
* *Начальная_позиция* — обязательный аргумент (только для функции **Mid**).  Начальная позиция в строке.  Первый символ строки находится в позиции 1.
* *Количество_символов* — обязательный аргумент.  Число возвращаемых символов.

**Left**( *таблица_с_одним_столбцом*, *количество_символов* )<br>**Mid**( *таблица_с_одним_столбцом*, *начальная_позиция*, *количество_символов* )<br>**Right**( *таблица_с_одним_столбцом*, *количество_символов* )

* *SingleColumnTable* — обязательный аргумент. Таблица с одним столбцом, из которой нужно извлечь результаты.
* *Начальная_позиция* — обязательный аргумент (только для функции **Mid**).  Начальная позиция в строке.  Первый символ строки находится в позиции 1.
* *Количество_символов* — обязательный аргумент.  Число возвращаемых символов.

## <a name="examples"></a>Примеры
### <a name="single-string"></a>Одна строка
Примеры в этом разделе используют в качестве [источника данных](../working-with-data-sources.md) элемент управления для ввода текста. Элемент управления называется **Author** и содержит строку "И. И. Иванов".

| Формула | Описание | Возвращаемый результат |
| --- | --- | --- |
| **Left ( Author.Text 5 )** |Извлекает до пяти символов от начала строки. |"И. И." |
| **Mid ( Author.Text, 7, 4 )** |Извлекает до четырех символов, начиная с седьмого знака в строке. |"Иван" |
| **Right (Author.Text 5)** |Извлекает до пяти знаков с конца строки. |"ванов" |

### <a name="single-column-table"></a>Для таблицы с одним столбцом
Каждый пример в этом разделе извлекает строки из **столбца** [Address](../working-with-tables.md#columns) источника данных с именем **People** и возвращает таблицу из одного столбца с результатами:

![](media/function-left-mid-right/people-table.png)

| Формула | Описание | Возвращаемый результат |
| --- | --- | --- |
| **Left( ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;), 8 )** |Извлекает первые восемь символов каждой строки. |<style> img { max-width: none } </style> ![](media/function-left-mid-right/people-table-left.png) |
| **Mid( ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;), 5, 7 )** |Извлекает средние семь символов каждой строки, начиная с пятого символа. |![](media/function-left-mid-right/people-table-mid.png) |
| **Right( ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;), 7 )** |Извлекает последние семь символов каждой строки. |![](media/function-left-mid-right/people-table-right.png) |

### <a name="step-by-step-example"></a>Пошаговый пример
1. Импортируйте или создайте [коллекцию](../working-with-data-sources.md#collections) с именем **Inventory**, затем покажите ее в коллекции, как это описано в первой процедуре раздела [Показ изображений и текстов в коллекции](../show-images-text-gallery-sort-filter.md).
2. Задайте в свойстве **[Text](../controls/properties-core.md)** нижней метки в коллекции следующую функцию:
   
    **Right(ThisItem.ProductName, 3)**
   
    Метка будет показывать три последних символа названия каждого продукта.
