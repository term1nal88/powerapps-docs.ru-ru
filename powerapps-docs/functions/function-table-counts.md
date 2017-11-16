---
title: "Функции Count, CountA, CountIf и CountRows | Документация Майкрософт"
description: "Справочные сведения, включая синтаксис и пример, для функций Count, CountA, CounfIf и CountRows в PowerApps"
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
ms.openlocfilehash: b3473d0dcf1462648f39c3dbbdedd12d1cfce08c
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2017
---
# <a name="count-counta-countif-and-countrows-functions-in-powerapps"></a>Функции Count, CountA, CountIf и CountRows в PowerApps
Подсчитывает все [записи](../working-with-tables.md#records) в [таблице](../working-with-tables.md) или подсчитывает количество записей, удовлетворяющих условию.

## <a name="description"></a>Описание
Функция **Count** подсчитывает количество содержащих число записей в таблице из одного столбца.

Функция **CountA** подсчитывает количество *непустых* записей в таблице из одного столбца. При подсчете учитываются [пустые](function-isblank-isempty.md) текстовые строки ("").

Функция **CountIf** подсчитывает количество записей в таблице, которые возвращают значение **true** в результате вычисления логической формулы.  Формула может ссылаться на [столбцы](../working-with-tables.md#columns) таблицы.

Функция **CountRows** подсчитывает количество записей в таблице.

Каждая из этих функций возвращает число.

[!INCLUDE [delegation-no](../../includes/delegation-no.md)]

## <a name="syntax"></a>Синтаксис
**Count**( *таблица_из_одного_столбца* )<br>
**CountA**( *таблица_из_одного_столбца* )

* *SingleColumnTable* — обязательный аргумент.  Столбец записей для подсчета.  

**CountIf**( *таблица*, *логическая_формула* )

* *Table* — обязательный аргумент.  Таблица с записями для подсчета.
* *Логическая_формула* — обязательный аргумент.  Формула для вычисления для каждой записи таблицы.  Учитываются записи, возвращающие по этой формуле значение **true**.  Формула может ссылаться на столбцы таблицы.

**CountRows**( *таблица* )

* *Table* — обязательный аргумент.  Таблица с записями для подсчета.

## <a name="example"></a>Пример
1. Импортируйте или создайте [коллекцию](../working-with-data-sources.md#collections) с именем **Inventory**, как описано в первом шаге описания [показа текста и изображений в коллекции](../show-images-text-gallery-sort-filter.md).
2. Добавьте метку и установите в ее свойстве **[Text](../controls/properties-core.md)** формулу:
   
    **CountIf(Inventory, UnitsInStock < 30)**
   
    Метка показывает **2**, так как по двум продуктам (Ganymede и Callisto) на складе меньше 30 единиц.
3. Добавьте другую метку и установите в ее свойстве **[Text](../controls/properties-core.md)** формулу:
   
    **CountA(Inventory.UnitsInStock)**
   
    Метка показывает **5**, так как это количество непустых ячеек в столбце **UnitsInStock**.
4. Добавьте другую метку и установите в ее свойстве **[Text](../controls/properties-core.md)** формулу:
   
    **CountRows(Inventory)**
   
    Метка показывает **5**, так как коллекция содержит пять строк.

