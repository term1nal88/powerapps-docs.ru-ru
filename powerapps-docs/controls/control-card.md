---
title: "Справка по элементу управления \"Карточка\" | Документация Майкрософт"
description: "Сведения об элементе управления \"Карточка\" с описанием его свойств и примерами"
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
ms.date: 10/25/2016
ms.author: gregli
ms.openlocfilehash: e85b7ce4c51e693d566fb50b51be48f9ab3edadd
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2017
---
# <a name="card-control-in-powerapps"></a>Элемент управления "Карточка" в PowerApps
Позволяет отображать и редактировать одно поле в элементе управления **[Форма просмотра](control-form-detail.md)** или **[Форма редактирования](control-form-detail.md)**.

## <a name="description"></a>Описание
Элементы управления **[Форма просмотра](control-form-detail.md)**  и  **[Форма редактирования](control-form-detail.md)** выполняют функции контейнеров для отображения и просмотра записей. Каждый контейнер может содержать набор элементов управления **Карточка** для отображения отдельных полей или обновления этих полей. Каждая карточка имеет свойство **DataField**, которое указывает, для какого поля записи она применяется.  

Существуют стандартные карточки для разных типов данных и режимов работы.  Например, может быть карточка для редактирования числового поля с элементом управления **[Текстовый ввод](control-text-input.md)**, с которым очень удобно работать с помощью клавиатуры. Другая карточка может поддерживать редактирование числа с помощью элемента управления **[Ползунок](control-slider.md)**. Когда выбран элемент управления формой, вы можете легко выбрать карточку по нужному полю на панели справа.

Карточки сами содержат элементы управления. Элементы управления карточки предоставляют интерфейс для отображения и редактирования одного поля. Например, номер карточки может состоять из элемента управления **[Метка](control-text-box.md)**, который отображает имя поля, и другого элемента управления **[Текстовое поле](control-text-input.md)** для редактирования значения поля. Карточка может также иметь элемент управления **[Метка](control-text-box.md)**, в котором отображаются все возникающие ошибки при проверке, или **[Метка](control-text-box.md)** для отображения звездочки, которая указывает, что поле является обязательным.

Вы можете настраивать элементы управления для ранее определенной карточки, например изменяя их размер или положение, скрывая отображение или добавляя новые элементы управления и т. п. Также вы можете начать работу с пустой "пользовательской" карточки и самостоятельно добавить в нее все нужные элементы.

Стандартные карточки по умолчанию *заблокированы*. В заблокированной карточке можно изменить только некоторые свойства самой карточки или элементов управления. Кроме того, заблокированную карточку нельзя удалить. Вы можете отобразить состояние блокировки и разблокировать карточку на вкладке **Представление** в представлении **Дополнительно**. Если свойство заблокировано, то есть его нельзя изменять, рядом с его именем отображается значок блокировки. Разблокирование карточки предназначено для опытных пользователей. Используйте его с осторожностью, поскольку после разблокирования для карточки не будут автоматически создаваться формулы, и эту карточку невозможно заблокировать снова.

В контейнере формы существует запись **ThisItem**, которая содержит все поля записи.  Например, свойство карточки **[Default](properties-core.md)**  часто имеет значение **ThisItem**. *FieldName*.

Вы можете использовать ссылку на родительский элемент **Parent**, чтобы настроить элемент управления, использующий свойства карточки.  Например, элемент управления **Parent.Default** следует использовать для чтения начального состояния поля из источника данных. Если использовать элемент **Parent** вместо прямого доступа к данным, карточка будет лучше инкапсулирована, и вы сможете преобразовать ее в другое поле без нарушения внутренних формул.

В разделе [Understand data cards](../working-with-cards.md) (Общие сведения о карточках данных) вы найдете примеры настройки, разблокирования и создания карточек.

## <a name="key-properties"></a>Основные свойства
**DataField**. Имя поля в записи, которое позволяет просматривать и редактировать эта карточка.

* Укажите имя в формате единой статической строки, заключенной в двойные кавычки (например, **"Name"**). Не используйте формулы.
* Чтобы отменить привязку карточки, установите для ее свойства **DataField** *пустое* значение. Свойства **Valid** и **Update** игнорируются для несвязанных карточек.

**[Default](properties-core.md)**. Начальное значение элемента управления до его изменения пользователем.

* Для каждого элемента управления в карточке присвойте этому свойству значение **Parent.Default**, чтобы они использовали значения по умолчанию для соответствующего источника данных. Например, если для свойства ползунка **[Default](properties-core.md)** установить значение **Parent.Default**, пользователь будет начинать работу со стандартного значения для этого ползунка.

**DisplayMode** — возможные значения: **Изменение, Просмотр** или **Отключено**. В зависимости от значения этого режима элемент управления в карточке разрешает пользователю вводить данные (**Изменение**), только отображает данные (**Просмотр**) или элемент вообще отключен (**Отключено**).  

* Этот режим позволяет использовать одну карточку в формах редактирования и просмотра одновременно. Для этого нужно настроить это свойство, привязанное к поведению формы по умолчанию.
* В режиме **Просмотр** дочерние элементы управления, такие как **[Ввод текста](control-text-input.md)**, **[Раскрывающийся список](control-drop-down.md)**, **[Выбор даты](control-date-picker.md)**, отображают только текст, а не интерактивные элементы или элементы оформления.

**Отображаемое имя.** Понятное имя для поля в источнике данных.

* Функция **[DataSourceInfo](../functions/function-datasourceinfo.md)** предоставляет эти метаданные из источника данных.
* Для элементов управления в карточке следует использовать **Parent.DisplayName**, чтобы использовать имя поля.

**Error.** Понятное пользователю сообщение об ошибке, которое будет отображаться для этого поля при сбое проверки.

* Это свойство задается при вызове **SubmitForm**.  
* Сообщение описывает проблемы проверки, используя метаданные источника данных и свойство **Required** карточки.

**Required.** Обязательно ли указывать значение для карточки при редактировании поля источника данных.

* Функция **[DataSourceInfo](../functions/function-datasourceinfo.md)** предоставляет нужные метаданные из источника данных.
* Для элементов управления в карточке следует использовать **Parent.Required**, чтобы определить, является ли поле этой карточки обязательным.

**Update.** Значение, которое будет записано в источник данных для этого поля.

* Используйте формулу этого свойства для извлечения значений из элементов управления, используемых в карточке для редактирования и записи значения в источник данных. Например, установите для свойства **Update** значение **Slider.Value**, чтобы записать в источник данных значение, установленное на ползунке в текущей карточке.

**[Width](properties-size-location.md)** — расстояние между левым и правым краем элемента управления.

**[WidthFit](properties-size-location.md)** — позволяет включить автоматическое изменение размера элемента управления по горизонтали для заполнения пустого пространства в контейнере, например в элементе управления **[Форма изменения](control-form-detail.md)**. Если для нескольких карт этому свойству присвоено значение **true**, то пространство распределяется между ними. Дополнительные сведения о формах данных см. в статье [Общие сведения о макете формы данных в Microsoft PowerApps](../working-with-form-layout.md).

## <a name="additional-properties"></a>Дополнительные свойства
**[BorderColor](properties-color-border.md)** — цвет границы элемента управления.

**[BorderStyle](properties-color-border.md)** — стиль границы элемента управления: **Сплошная**, **Штриховая**, **Пунктирная** или **Отсутствует**.

**[BorderThickness](properties-color-border.md)** — толщина границы элемента управления.

**[Fill](properties-color-border.md)** — цвет фона элемента управления.

**[Height](properties-size-location.md)** — расстояние между верхним и нижним краем элемента управления.

**Valid** —содержит ли **Карточка** или **[Форма редактирования](control-form-detail.md)** допустимые значения, готовые к отправке в источник данных.

**[Visible](properties-core.md)** определяет, отображается ли элемент управления или он скрыт.

**[X](properties-size-location.md)** — расстояние между левым краем элемента управления и левым краем его родительского контейнера (или экрана, если родительского контейнера нет). Для элемента управления **[Карточка](control-card.md)** в контейнере с несколькими столбцами данное свойство определяет столбец, в котором отображается карточка.

**[Y](properties-size-location.md)** — расстояние между верхним краем элемента управления и верхним краем его родительского контейнера (или экрана, если родительского контейнера нет). Для элемента управления **[Карточка](control-card.md)** в контейнере с несколькими строками данное свойство определяет строку, в которой отображается карточка.

## <a name="examples"></a>Примеры
С примерами можно ознакомиться в разделах [Общие сведения о карточках данных](../working-with-cards.md) и [Общие сведения о макете формы данных в Microsoft PowerApps](../working-with-form-layout.md).
