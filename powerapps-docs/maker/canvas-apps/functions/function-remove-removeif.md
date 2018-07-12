---
title: Функции Remove и RemoveIf | Документация Майкрософт
description: Справочные сведения, включая описание синтаксиса и примеры, относительно функций Remove и RemoveIf в PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/21/2015
ms.author: gregli
ms.openlocfilehash: 1f4df70ce3274c4d83c39955df58ebc344038de3
ms.sourcegitcommit: 6d9fe9967841e381b108a7fb53c9057e295336ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38095857"
---
# <a name="remove-and-removeif-functions-in-powerapps"></a>Функции Remove и RemoveIf в PowerApps
Удаляют [записи](../working-with-tables.md#records) из [источника данных](../working-with-data-sources.md).

## <a name="description"></a>Описание
### <a name="remove-function"></a>Функция Remove
С помощью функции **Remove** можно удалить из источника данных определенную запись или набор записей.  

Для [коллекций](../working-with-data-sources.md#collections) должна совпадать вся запись. Удалить все копии записи можно с помощью аргумента **All**; в противном случае удаляется только одна копия.

### <a name="removeif-function"></a>Функция RemoveIf
С помощью функции **RemoveIf** можно удалить одну или несколько записей на основе определенного условия или набора условий. Каждое из этих условий может быть любой формулой, которая возвращает результат **true** (истина) или **false** (ложь), и может содержать ссылки на [столбцы](../working-with-tables.md#columns) источника данных (по имени). Каждое условие оценивается отдельно для каждой записи, и запись удаляется, если все условия возвращают значение **true**.

Функции **Remove** и **RemoveIf** возвращают измененный источник данных в виде [таблицы](../working-with-tables.md). Обе эти функции можно использовать только в [формулах поведения](../working-with-formulas-in-depth.md).

Кроме того, удалить все записи из источника данных можно с помощью функции **[Clear](function-clear-collect-clearcollect.md)**.

### <a name="delegation"></a>Делегирование
[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Синтаксис
**Remove**(*источник_данных*, *запись_1*[, *запись_2*, ... ] [, **All**])

* *источник_данных* — обязательный аргумент. Это источник данных, содержащий запись или записи, которые требуется удалить.
* *запись(_n)*  — обязательный аргумент. Запись или записи, которые требуется удалить.
* **All** — необязательный аргумент. В коллекции может существовать несколько копий одной записи.  С помощью аргумента **All** можно удалить их все.

**Remove**(*источник_данных*, *таблица*[, **All**])

* *источник_данных* — обязательный аргумент. Это источник данных, содержащий записи, которые требуется удалить.
* *таблица* — обязательный аргумент. Таблица с записями, которые требуется удалить.
* **All** — необязательный аргумент. В коллекции может существовать несколько копий одной записи.  С помощью аргумента **All** можно удалить их все.

**RemoveIf**(*источник_данных*, *условие*[, ... ])

* *источник_данных* — обязательный аргумент. Это источник данных, содержащий запись или записи, которые требуется удалить.
* *условие(_n)*  — обязательный аргумент. Формула, возвращающая значение **true** (истина) для записи или записей, которые требуется удалить.  В формуле можно использовать названия столбцов из *источника_данных*.  Если указано несколько *условий*, для удаления соответствующей записи все они должны возвращать значение **true**.

## <a name="examples"></a>Примеры
В этих примерах выполняется удаление записи или записей из источника данных под названием **IceCream**, начинающегося со значений из следующей таблицы:

![](media/function-remove-removeif/icecream.png)

| Формула | Описание | Возвращаемый результат |
| --- | --- | --- |
| **Remove(&nbsp;IceCream,<br>First(&nbsp;Filter(&nbsp;IceCream,&nbsp;Flavor="Chocolate"&nbsp;)&nbsp;))** |Удаляет из источника данных запись **Chocolate**. |<style> img { max-width: none } </style> ![](media/function-remove-removeif/icecream-no-chocolate.png)<br><br>Источник данных **IceCream** изменен. |
| **Remove(&nbsp;IceCream,<br>First(&nbsp;Filter(&nbsp;IceCream,&nbsp;Flavor="Chocolate"&nbsp;)&nbsp;) First(&nbsp;Filter(&nbsp;IceCream,&nbsp;Flavor="Strawberry"&nbsp;)&nbsp;))** |Удаляет из источника данных две записи. |![](media/function-remove-removeif/icecream-only-vanilla.png)<br><br>Источник данных **IceCream** изменен. |
| **RemoveIf(&nbsp;IceCream, Quantity&nbsp;>&nbsp;150)** |Удаляет записи со значением **Quantity** больше **150**. |![](media/function-remove-removeif/icecream-only-chocolate.png)<br><br>Источник данных **IceCream** изменен. |
| **RemoveIf(&nbsp;IceCream, Quantity&nbsp;>&nbsp;150, Left(&nbsp;Flavor,&nbsp;1&nbsp;) = "S")** |Удаляет записи со значением **Quantity** больше 150 и значением **Flavor**, начинающимся с буквы **S**. |![](media/function-remove-removeif/icecream-no-strawberry.png)<br><br><br>Источник данных **IceCream** изменен. |
| **RemoveIf(&nbsp;IceCream, true)** |Удаляет из источника данных все записи. |![](media/function-remove-removeif/icecream-empty.png)<br><br>Источник данных **IceCream** изменен. |

### <a name="step-by-step"></a>Шаг за шагом
1. Импортируйте или создайте коллекцию под названием **Inventory** и отобразите ее в коллекции, как описано в [этой статье](../show-images-text-gallery-sort-filter.md).
2. В коллекции задайте для свойства **[OnSelect](../controls/properties-core.md)** изображения следующее выражение:<br>**Remove(Inventory, ThisItem)**
3. Нажмите клавишу F5 и выберите изображение в коллекции.<br>Элемент будет удален из галереи и из коллекции.

