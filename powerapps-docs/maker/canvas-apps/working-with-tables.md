---
title: Общие сведения о таблицах в приложениях на основе холста | Документы Майкрософт
description: Справочные сведения о работе с таблицами, столбцами и записями в приложениях на основе холста в PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/26/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 38745810321807e69d5eba8e1f2c281dafa73ae5
ms.sourcegitcommit: 5db6e3ac3a622de313a1102417397e126c3f92f2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2018
ms.locfileid: "45640453"
---
# <a name="understand-canvas-app-tables-and-records-in-powerapps"></a>Общие сведения о таблицах и записях в приложениях на основе холста в PowerApps

PowerApps позволяет вам создать приложение на основе холста, обращающееся к сведениям в Microsoft Excel, SharePoint, SQL Server и ряде других источников, хранящих данные в виде записей и таблиц. Чтобы работать с данными такого типа максимально эффективно, ознакомьтесь с основными понятиями, которые лежат в основе этих структур.

* Запись содержит одну или несколько категорий сведений о человеке, месте или предмете. Например, запись может содержать имя, адрес электронной почты и номер телефона для одного клиента. В других средствах записи называются "строками" или "элементами".
* В таблице хранится одна или несколько записей, содержащих одинаковые категории сведений. Например, таблица может содержать имена, адреса электронной почты и номера телефона 50 клиентов.

Для создания и обновления записей и таблиц, а также управления ими в приложении используются [формулы](working-with-formulas.md). Зачастую данные при этом считываются из внешнего [источника данных](working-with-data-sources.md), представляющего собой расширенную таблицу, и записываются в такой источник. Кроме того, можно создать одну или несколько внутренних таблиц, которые называются [коллекциями](working-with-data-sources.md#collections).

Вы можете создавать различные формулы, которые принимают имя таблицы в качестве аргумента так же, как формула в Excel принимает одну или несколько ссылок на ячейки. Некоторые формулы в PowerApps возвращают таблицу, в которой отражаются значения других заданных аргументов. Например, можно создать формулу:

* чтобы обновлять записи в таблице, указав эту таблицу в качестве одного из нескольких аргументов функции **[Patch](functions/function-patch.md)**;
* чтобы добавлять, удалять и переименовывать столбцы в таблице, указав ее в качестве аргумента функции **[AddColumns](functions/function-table-shaping.md)**, **[DropColumns](functions/function-table-shaping.md)** или **[RenameColumns](functions/function-table-shaping.md)**. Ни одна из этих функций не изменяет исходную таблицу. Вместо этого функция возвращает другую таблицу на основе других заданных аргументов.

## <a name="elements-of-a-table"></a>Элементы таблицы
![](media/working-with-tables/elements-of-a-table.png)

### <a name="records"></a>Записи
Каждая запись содержит по меньшей мере одну категорию сведений о человеке, месте или предмете. В предыдущем примере показана запись для каждого товара (**Chocolate**, **Bread** и **Water**) и столбец для каждой категории сведений (**Price**, **Quantity on Hand** и **Quantity on Order**).

Чтобы сослаться в формуле на саму запись вне контекста таблицы, воспользуйтесь фигурными скобками. Например, запись **{ Name: "Strawberries", Price: 7,99 }** не связана с таблицей. Обратите внимание, что имена полей (**Name** и **Price** в этом примере) не заключаются в двойные кавычки.

### <a name="fields"></a>Поля
Поле — это отдельная часть сведений в записи. Такого рода поля можно представить себе как значение в столбце определенной записи.

Как и в случае с элементом управления, для ссылки на поле записи используется **.** ([оператор](functions/operators.md) записи).  Например, **First(Products).Name** возвращает поле **Name** для первой записи в таблице **Products**.

Поле может содержать другую запись или таблицу, как показано в примере для функции **[GroupBy](functions/function-groupby.md)**. Количество уровней вложенных записей и таблиц не ограничено.

### <a name="columns"></a>Столбцы
Столбец состоит из одинаковых полей одной или нескольких записей в таблице. В приведенном выше примере у каждого товара есть поле цены, и эта цена находится в одном и том же столбце для всех продуктов.  Приведенная выше таблица состоит из четырех столбцов, имена которых показаны в первой строке:

* **Name** (Наименование)
* **Price** (Цена)
* **Quantity on Hand** (Количество в наличии)
* **Quantity on Order** (Количество в заказе)

Имя столбца соответствует содержащимся в нем полям.

Все значения в столбце принадлежат к одинаковому типу данных. В приведенном выше примере столбец Quantity on Hand всегда содержит число и не может содержать строку, например "12 единиц", для одной из записей.  Значение любого поля может быть также пустым (*blank*).  

В других средствах столбцы могут называться "полями".

> [!NOTE]
> Для источников данных SharePoint и Excel, содержащих имена столбцов с пробелами, PowerApps заменит эти пробелы кодом **"\_x0020\_"**. Например, столбец **Имя столбца** из SharePoint или Excel будет отображаться как **Имя_x0020_столбца** в PowerApps при отображении в структуре данных или использовании в формуле.

### <a name="table"></a>Таблицы
Таблица состоит из одной или нескольких записей, каждая из которых имеет несколько полей с согласованными именами во всех записях.

У всех таблиц, хранящихся в источнике данных или коллекции, есть имя, которое используется для ссылки на таблицу и передачи ее функциям, принимающим таблицы в качестве аргументов.  Таблицы также могут быть результатом функции или формулы.

Как показано в следующем примере, таблицу в формуле можно представить с помощью функции **[Table](functions/function-table.md)** с набором записей, которые записываются в фигурных скобках:

**Table( { Value: "Strawberry" }, { Value: "Vanilla" } )**

Используя квадратные скобки, можно также определить таблицу с одним столбцом.  Эквивалентный способ представления приведенной выше записи:

**[ "Strawberry", "Vanilla" ]**

## <a name="table-formulas"></a>Формулы для таблиц
В Excel и PowerApps формулы для обработки чисел и строк текста используются аналогичным образом.

* Если в Excel ввести значение, например **42**, в ячейке **A1** и формулу, например **A1+2**, в другой ячейке, в ней отобразится значение **44**.
* Если в PowerApps задать для свойства **[Default](controls/properties-core.md)** элемента управления **Slider1** значение **42**, а для свойства **[Text](controls/properties-core.md)** метки — значение **Slider1.Value + 2**, также отобразится значение **44**.

В обоих случаях вычисленное значение изменяется автоматически при изменении значений аргументов (например, числа в ячейке **A1** или значения **Slider1**).

Аналогично можно использовать формулы для доступа к данным в таблицах и записях, а также управления ими. В некоторых формулах имена таблиц можно использовать в качестве аргументов. Например, **Min(Catalog, Price)** можно использовать для отображения минимального значения столбца **Price** таблицы **Catalog**. Другие формулы возвращают в качестве значения целые таблицы, например **RenameColumns(Catalog, "Price", "Cost")**, которая возвращает все записи из таблицы **Catalog**, но изменяет имя столбца **Price** на **Cost**.

Так же как в случае с числами, формулы, включающие в себя таблицы и записи, автоматически пересчитываются при изменении базовой таблицы или записи. Если стоимость товара в таблице **Catalog** станет меньше предыдущего минимального значения, возвращаемое значение формулы **[Min](functions/function-aggregates.md)** автоматически изменится соответствующим образом.

Давайте рассмотрим несколько простых примеров.

1. Создайте пустое приложение для телефона и добавьте вертикальный элемент управления **[Коллекция](controls/control-gallery.md)**, который содержит другие элементы управления.

    По умолчанию на экране отображается заполнитель из таблицы **CustomGallerySample**. В качестве значения свойства **[Items](controls/properties-core.md)** элемента управления **[Коллекция](controls/control-gallery.md)** на этом экране автоматически устанавливается эта таблица.

    ![](media/working-with-tables/gallery-items.png)

    > [!NOTE]
    > Для большей наглядности на иллюстрациях мы изменили относительное расположение некоторых элементов управления и увеличили их размер.

2. Вместо того чтобы задавать в качестве значения свойства **[Items](controls/properties-core.md)** имя таблицы, присвойте ему формулу, которая включает в себя имя таблицы в качестве аргумента, как показано в этом примере:<br>
    **Sort(CustomGallerySample, SampleHeading, Descending)**

    Эта формула содержит функцию **[Sort](functions/function-sort.md)**, которая принимает имя таблицы в качестве первого аргумента и имя ее столбца в качестве второго. Функция также поддерживает необязательный третий аргумент, который указывает, что данные необходимо отсортировать в порядке убывания.

    ![](media/working-with-tables/gallery-items-sort.png)

3. Задайте в качестве значения свойства **[Items](controls/properties-core.md)** формулу, которая принимает в качестве аргумента формулу с предыдущего этапа и возвращает таблицу, как в следующем примере:<br>
   **FirstN(Sort(CustomGallerySample, SampleHeading, Descending), 2)**

    В этой формуле для отображения определенного числа записей в таблице используется функция **[FirstN](functions/function-first-last.md)**. Функция **[Sort](functions/function-sort.md)** используется в качестве первого аргумента **[FirstN](functions/function-first-last.md)**, и число (в данном случае **2**) — в качестве второго (он указывает, сколько записей следует отображать).
   
    Вся формула возвращает таблицу, содержащую первые две записи таблицы **CustomGallerySample**, отсортированные по столбцу **SampleHeading** в порядке убывания.
   
    ![](media/working-with-tables/gallery-items-sort-firstn.png)

### <a name="table-functions-and-control-properties"></a>Функции для таблиц и свойства элементов управления
Многие функции в PowerApps принимают имя таблицы в качестве аргумента, создают вторую таблицу с теми же данными, обрабатывают новую таблицу на основе других аргументов, а затем возвращают результат. Эти функции не изменяют исходную таблицу, даже если она является источником данных.

* **[Sort](functions/function-sort.md)**, **[Filter](functions/function-filter-lookup.md)**  — сортирует и фильтрует записи.
* **[FirstN](functions/function-first-last.md)**, **[LastN](functions/function-first-last.md)**  — возвращает первые или последние N записей таблицы.
* **[Abs](functions/function-numericals.md)**, **[Sqrt](functions/function-numericals.md)**, **[Round](functions/function-round.md)**, **[RoundUp](functions/function-round.md)**, **[RoundDown](functions/function-round.md)**  — выполняет с каждой записью таблицы из одного столбца арифметические операции, результатом которых является таблица с одним столбцом.
* **[Left](functions/function-left-mid-right.md)**, **[Mid](functions/function-left-mid-right.md)**, **[Right](functions/function-left-mid-right.md)**, **[Replace](functions/function-replace-substitute.md)**, **[Substitute](functions/function-replace-substitute.md)**, **[Trim](functions/function-trim.md)**, **[Lower](functions/function-lower-upper-proper.md)**, **[Upper](functions/function-lower-upper-proper.md)**, **[Proper](functions/function-lower-upper-proper.md)**  — обрабатывает строки каждой записи таблицы из одного столбца, создавая в результате таблицу строк с одним столбцом.
* **[Len](functions/function-len.md)**  — возвращает таблицу из одного столбца, содержащего длины каждой из строк, для столбца строк.
* **[Concatenate](functions/function-concatenate.md)**  — объединяет несколько столбцов строк, создавая в результате таблицу строк из одного столбца.
* **[AddColumns](functions/function-table-shaping.md)**, **[DropColumns](functions/function-table-shaping.md)**, **[RenameColumns](functions/function-table-shaping.md)**, **[ShowColumns](functions/function-table-shaping.md)**  — обрабатывает столбец таблицы, в результате чего создается новая таблица с различными столбцами.
* **[Distinct](functions/function-distinct.md)**  — удаляет дубликаты записей.
* **[Shuffle](functions/function-shuffle.md)**  — переставляет записи в произвольном порядке.
* **[HashTags](functions/function-hashtags.md)**  — ищет хэш-теги в строке.
* **[Errors](functions/function-errors.md)**  — предоставляет сведения об ошибке при работе с источником данных.

Функцию, которой требуется один столбец в качестве аргумента, можно выполнить для таблицы, содержащей несколько столбцов. Чтобы извлечь один столбец из таблицы с несколькими столбцами, используйте функцию **[ShowColumns](functions/function-table-shaping.md)** в качестве аргумента функции, которую необходимо применить, как показано в следующем примере:<br>**Lower( ShowColumns( Products, "Name" ) )**

Эта формула создает таблицу из одного столбца, содержащую все данные из столбца **Name** таблицы **Products**, однако преобразует все прописные буквы в строчные. Указав таблицу в качестве аргумента функции **[AddColumns](functions/function-table-shaping.md)**, **[RenameColumns](functions/function-table-shaping.md)** или **[DropColumns](functions/function-table-shaping.md)**, можно полностью переформировать таблицы желаемым образом.

Если указать в качестве аргумента для одной из этих функций источник данных, функция изменит записи этого источника и в общем случае возвратит новое значение источника данных в виде таблицы.

* **[Collect](functions/function-clear-collect-clearcollect.md)**, **[Clear](functions/function-clear-collect-clearcollect.md)**, **[ClearCollect](functions/function-clear-collect-clearcollect.md)**  — создает и добавляет записи в коллекцию, а также удаляет их из нее.
* **[Update](functions/function-update-updateif.md)**, **[UpdateIf](functions/function-update-updateif.md)**  — обновляет записи, которые соответствуют одному или нескольким заданным условиям.
* **[Remove](functions/function-remove-removeif.md)**, **[RemoveIf](functions/function-remove-removeif.md)**  — удаляет записи, которые соответствуют одному или нескольким заданным условиям.

Этим свойствам присваиваются значения, которые являются таблицами:

* **Items** — применяется для коллекций и списков. Таблица, которая отображается в коллекции.
* **SelectedItems** — применяется для списков. Таблица элементов, которые выбрал пользователь.

## <a name="record-formulas"></a>Запись формул
Вы можете также создать формулу, которая вычисляет данные для отдельной записи, принимает отдельную запись в качестве аргумента и предоставляет отдельную запись как возвращаемое значение. Возвращаясь к приведенному выше примеру коллекции, воспользуемся свойством **Gallery1.Selected** для отображения сведений из записи, которую выбрал в ней пользователь.

1. Добавьте кнопку и задайте следующую формулу в качестве значения свойства **[OnSelect](controls/properties-core.md)**:<br>
    **Collect( SelectedRecord, Gallery1.Selected )**

2. Удерживая нажатой клавишу ALT, нажмите на эту кнопку.

3. В меню **Файл** выберите **Коллекции**.

    ![](media/working-with-tables/selected-collection.png)

Эта формула возвращает запись, которая включает в себя данные не только из записи, выбранной в данный момент в коллекции, но и каждого элемента управления в этой коллекции. Допустим, что запись содержит столбец **SampleText**, который соответствует столбцу **SampleText** в исходной таблице, и столбец **Subtitle1**, представляющий метку, в которой отображаются данные из этого столбца. Выберите значок таблицы в столбце **Subtitle1** для детализации данных.

> [!NOTE]
> Столбец **Subtitle1** может называться **Subtitle2** или подобным образом, если вы добавили другие элементы помимо описанных в этом разделе.

Теперь при наличии выбранной записи можно извлечь из нее отдельные поля с помощью оператора **.** .

1. Добавьте элемент управления **[Label](controls/control-text-box.md)** и переместите его под коллекцию и кнопку.

1. Задайте для свойства **[Text](controls/properties-core.md)** метки следующее выражение:<br>
    **"Selected: " & Gallery1.Selected.SampleHeading**
   
    ![](media/working-with-tables/gallery-selected.png)

Таким образом вы получили свойство **Selected**, которое представляет собой запись, и извлекли из него свойство **SampleHeading**.

Запись можно также использовать как контейнер общего назначения для соответствующих именованных значений.

* При построении формулы, в которой используются функции **[UpdateContext](functions/function-updatecontext.md)** и **[Navigate](functions/function-navigate.md)**, для сбора [переменных контекста](working-with-variables.md#create-a-context-variable), которые необходимо обновить, используется запись.
* Для сбора изменений, внесенных пользователем в форму, воспользуйтесь свойством **[Updates](controls/control-form-detail.md)** элемента управления **[Форма редактирования](controls/control-form-detail.md)**.
* Чтобы обновить источник данных и при этом объединить записи, воспользуйтесь функцией **[Patch](functions/function-patch.md)**.

В этих случаях запись никогда не была частью таблицы.

### <a name="record-functions-and-control-properties"></a>Функции для записей и свойства элементов управления
Функции, возвращающие записи:

* **[FirstN](functions/function-first-last.md)**, **[LastN](functions/function-first-last.md)**  — возвращает одну или несколько первых или последних записей таблицы.
* **[Lookup](functions/function-filter-lookup.md)**  — возвращает первую запись таблицы, которая соответствует одному или нескольким условиям.
* **[Patch](functions/function-patch.md)**  — обновляет источник данных или выполняет слияние записей.
* **[Defaults](functions/function-defaults.md)**  — возвращает значения по умолчанию для источника данных.

Свойства, возвращающие записи:

* **Selected** — применяется для коллекций и списков. Возвращает выбранную в данный момент запись.
* **Updates** — применяется для коллекций.  Объединяет все изменения, вносимые пользователем в форме ввода данных.
* **[Update](functions/function-update-updateif.md)**  — применяется для элементов управления вводом, например элементов управления текстовым вводом и ползунков. Задает отдельные свойства, собираемые в коллекции.

## <a name="record-scope"></a>Область действия записи
Некоторые функции при выполнении вычисляют формулы для всех записей таблицы по отдельности.  Результат формулы используется различными способами:  

* **Filter**, **Lookup** — формула определяет, нужно ли включать запись в выходные данные.
* **Sort** — формула предоставляет значение для сортировки записей.
* **Concat** — формула определяет строки, которые следует объединять.
* **ForAll** — формула может возвращать любое значение, которое потенциально имеет побочный эффект.
* **DISTINCT** — формула возвращает значение, используемое для выявления повторяющихся записей.  
* **AddColumns** — формула предоставляет значение добавленного поля.
* **Average**, **Max**, **Min**, **Sum**, **StdevP**, **VarP** — формула предоставляет значение для выполнения статистического вычисления.

Внутри этих формул можно ссылаться на поля обрабатываемой записи.  Каждая из этих функций создает "область записи", в которой вычисляется формула. При этом поля записи предоставляются как идентификаторы верхнего уровня.  Кроме того, можно использовать ссылки на свойства элементов управления и другие значения из приложения.

Возьмем, например, таблицу **Products**.

![](media/working-with-tables/requested.png)

Чтобы определить, требуется ли какого-либо из этих продуктов больше, чем есть в наличии, воспользуйтесь формулой:

**Filter( Products, 'Quantity Requested' > 'Quantity Available' )**

Первый аргумент функции **Filter** — это таблица записей, которые необходимо обработать, а второй — это формула.  Функция **Filter** создает для вычисления этой формулы область записи, в которой доступны поля каждой записи. В данном случае это **Product**, **Quantity Requested** и **Quantity Available**.  От результата сравнения зависит, нужно ли включать каждую запись в результат функции.

![](media/working-with-tables/needed.png)

Просуммировав значения в этом примере, можно рассчитать, сколько единиц каждого товара следует заказать.

**AddColumns( Filter( Products, 'Quantity Requested' > 'Quantity Available' ), "Quantity To Order", 'Quantity Requested' - 'Quantity Available' )**

Здесь мы добавляем к результату вычисляемый столбец.  У функции **AddColumns** есть своя область записи, которая используется для вычисления разницы между запрашиваемым и доступным количеством.

![](media/working-with-tables/toorder.png)

Наконец, мы можем сократить результирующую таблицу только до необходимых столбцов.

**ShowColumns( AddColumns( Filter( Products, 'Quantity Requested' > 'Quantity Available' ), "Quantity To Order", 'Quantity Requested' - 'Quantity Available' ), "Product", "Quantity To Order" )**

![](media/working-with-tables/toorderonly.png)

Обратите внимание, что в приведенном выше примере в одних местах мы использовали двойные кавычки (""), а в других — одинарные (').  Одинарные кавычки необходимы при ссылке на значение объекта, например поля или таблицы, если его имя содержит пробел.  Двойные кавычки используются, когда нужно не сослаться на значение объекта, а просто его объявить, что особенно важно в ситуациях, когда объект еще не существует, как в случае с **AddColumns**.  

### <a name="disambiguation"></a>Устранение неоднозначности
Имена полей, добавленные с использованием области записи, переопределяют такие же имена из любого места в приложении.  В этом случае с помощью [оператора устранения неоднозначности **@**](functions/operators.md) можно по-прежнему получать доступ к значениям за пределами области записи.

* Для доступа к значениям из вложенных областей записей используйте оператор **@**, указав имя нужной таблицы в формате:<br>_Таблица_**[@**_FieldName_**]**
* Чтобы получить доступ к глобальным значениям, таким как источники данных, коллекции и переменные контекста, используйте шаблон **[@**_ObjectName_**]** (без обозначения таблицы).

Если таблица, над которой выполняется операция, представляет собой выражение, например **Filter(** _Table_**,** ... **)**, оператор устранения неоднозначности использовать нельзя.  Не используя оператор устранения неоднозначности, получить доступ к полям этого табличного выражения можно только в наиболее глубоко вложенной области записи.

Представьте, например, что есть коллекция **X**.

![](media/working-with-tables/X.png)

Ее можно создать с помощью функции **ClearCollect( X, \[1, 2\] )**.

Есть также другая коллекция **Y**.

![](media/working-with-tables/Y.png)

Эту коллекцию можно создать с помощью функции **ClearCollect( Y, ["A", "B"] )**.

Кроме того, определите переменную контекста с именем **Value** с помощью следующей формулы: **UpdateContext( {Value: "!"} )**.

Давайте теперь соберем все это вместе.  В этом контексте следующая формула:

* **Ungroup( ForAll( X, ForAll( Y, Y[@Value] & Text( X[@Value] ) & [@Value] ) ), "Value" )**

дает такую таблицу:

![](media/working-with-tables/XY.png)

Что в этом случае происходит?  Внешняя функция **ForAll** определяет область записи для **X**, обеспечивая доступ к полю **Value** всех записей по мере их обработки.  Для доступа к нему можно просто воспользоваться словом **Value** или выражением **X[@Value]**.

Наиболее глубоко вложенная функция **ForAll** определяет другую область записи для **Y**.  Поскольку в этой таблице также определено поле **Value**, значение **Value** в данном случае будет ссылаться на поле в записи коллекции **Y** и больше не будет ссылаться на поле из **X**.  Чтобы получить здесь доступ к полю **Value** из коллекции **X**, необходимо использовать более длинную версию с оператором устранения неоднозначности.

Поскольку **Y** является самой глубоко вложенной областью записи, для доступа к полям в этой таблице устранение неоднозначности не требуется, что позволяет использовать эту формулу с тем же результатом:

* **Ungroup( ForAll( X, ForAll( Y, Value & Text( X[@Value] ) & [@Value] ) ), "Value" )**

Все области записей **ForAll** переопределяют глобальную область.  На определенную нами переменную контекста **Value** нельзя ссылаться по имени без оператора устранения неоднозначности.   Для доступа к этому значению следует использовать **[@Value]**.

**Ungroup** преобразует результат в плоскую структуру, поскольку вложенные функции **ForAll** приведут к созданию вложенной результирующей таблицы.

## <a name="inline-syntax"></a>Встроенный синтаксис
### <a name="records"></a>Записи
Для обозначения записей используются фигурные скобки, содержащие значения именованных полей.  Например, первую запись в таблице, приведенной в начале данного раздела, можно выразить с помощью следующей формулы:

**{ Name: "Chocolate", Price: 3,95, 'Quantity on Hand': 12, 'Quantity on Order': 10 }**

Вы можете также встраивать одни формулы в другие, как показано в этом примере:

**{ Name: First(Products).Name, Price: First(Products).Price * 1,095 }**

Чтобы вложить записи, можно воспользоваться вложенными фигурными скобками, как показано в следующем примере:

**{ 'Quantity': { 'OnHand': ThisItem.QuantOnHand, 'OnOrder': ThisItem.QuantOnOrder } }**

Заключите имя каждого столбца, содержащего специальный символ, например пробел или двоеточие, в одинарные кавычки.  Чтобы использовать одинарные кавычки в имени столбца, укажите их дважды.

Обратите внимание, что значение в столбце **Price** не содержит символ валюты, например знак рубля. Форматирование будет применено при отображении значения.  

### <a name="tables"></a>Таблицы
Таблицу можно создать с помощью функции **[Table](functions/function-table.md)** и набора записей. Таблицу, приведенную в начале данного раздела, можно представить с помощью следующей формулы:

**Table( { Name: "Chocolate", Price: 3.95, 'Quantity on Hand': 12, 'Quantity on Order': 10 },<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{ Name: "Bread", Price: 4.95, 'Quantity on Hand': 34, 'Quantity on Order': 0 },<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{ Name: "Water", Price: 4.95, 'Quantity on Hand': 10, 'Quantity on Order': 0 } )**

Таблицы можно также вкладывать друг в друга:

**Table( { Name: "Chocolate",<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'Quantity History': Table( { Quarter: "Q1", OnHand: 10, OnOrder: 10 },<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{ Quarter: "Q2", OnHand: 18, OnOrder: 0 } ) } )**

### <a name="value-tables"></a>Таблицы Value
Вы можете создать таблицы с одним столбцом, указав значения в квадратных скобках. Результирующая таблица будет содержать один столбец с именем **Value**.

Например, выражение **[ 1, 2, 3, 4 ]** эквивалентно **Table( { Value: 1 }, { Value: 2 }, { Value: 3 }, { Value: 4 } )** и возвращает такую таблицу:

![](media/working-with-tables/inline-table.png)

