---
title: "Справка по элементу управления \"Флажок\" | Документация Майкрософт"
description: "Сведения об элементе управления \"Флажок\" с описанием его свойств и примерами"
services: 
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 3784e90bbf6ed45d2b67b6211efaab279e37feca
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2017
---
# <a name="check-box-control-in-powerapps"></a>Элемент управления "Флажок" в PowerApps
Элемент управления, который пользователь может установить или снять, задавая значение **true** или **false** соответственно.

## <a name="description"></a>Описание
Пользователь может указывать логическое значение с помощью этого знакомого элемента управления, который уже не одно десятилетие используется в графических пользовательских интерфейсах.

## <a name="key-properties"></a>Основные свойства
**[Default](properties-core.md)** — начальное значение элемента управления до его изменения пользователем.

**[Text](properties-core.md)** — текст, отображаемый в элементе управления, или текст, который пользователь вводит в элемент управления.

**[Value](properties-core.md)** — значение элемента управления.

## <a name="additional-properties"></a>Дополнительные свойства
**[BorderColor](properties-color-border.md)** — цвет границы элемента управления.

**[BorderStyle](properties-color-border.md)** — стиль границы элемента управления: **Сплошная**, **Штриховая**, **Пунктирная** или **Отсутствует**.

**[BorderThickness](properties-color-border.md)** — толщина границы элемента управления.

**CheckboxBackgroundFill** — фоновый цвет поля вокруг значка флажка.

**CheckboxBorderColor** — цвет границы вокруг значка флажка.

**CheckboxSize** — ширина и высота поля вокруг значка флажка.

**CheckmarkFill** — цвет значка флажка.

**[Color](properties-color-border.md)** — цвет текста в элементе управления.

**[DisplayMode](properties-core.md)** — в зависимости от значения этого режима элемент управления разрешает пользователю вводить данные (**Изменение**), только отображает данные (**Просмотр**) или элемент вообще отключен (**Отключено**).

**[DisabledBorderColor](properties-color-border.md)** — цвет границы элемента управления, если для его свойства **[DisplayMode](properties-core.md)** установлено значение **Отключено**.

**[DisabledColor](properties-color-border.md)** — цвет текста в элементе управления, если для его свойства **[DisplayMode](properties-core.md)** установлено значение **Отключено**.

**[DisabledFill](properties-color-border.md)** — цвет фона элемента управления, если для его свойства **[DisplayMode](properties-core.md)** установлено значение **Отключено**.

**[Fill](properties-color-border.md)** — цвет фона элемента управления.

**[Font](properties-text.md)** — имя семейства шрифтов, используемых для отображения текста.

**[FontWeight](properties-text.md)** — толщина текста в элементе управления: **Жирный**, **Полужирный**, **Обычный** или **Очень тонкий**.

**[Height](properties-size-location.md)** — расстояние между верхним и нижним краем элемента управления.

**[HoverBorderColor](properties-color-border.md)** — цвет границы элемента управления при удерживании указателя мыши на нем.

**[HoverColor](properties-color-border.md)** — цвет текста в элементе управления при удерживании указателя мыши на нем.

**[HoverFill](properties-color-border.md)** — цвет фона элемента управления при удерживании указателя мыши на нем.

**[Italic](properties-text.md)** определяет, когда текст в элементе управления отображается курсивом.

**OnCheck** — поведение приложения, когда значение флажка или переключателя изменяется на **true**.

**[OnSelect](properties-core.md)** — поведение приложения, когда пользователь щелкает элемент управления или касается его.

**OnUncheck** — поведение приложения, когда значение флажка или переключателя изменяется на **false**.

**[PaddingBottom](properties-size-location.md)** — расстояние между текстом в элементе управления и нижним краем элемента управления.

**[PaddingLeft](properties-size-location.md)** — расстояние между текстом в элементе управления и левым краем элемента управления.

**[PaddingRight](properties-size-location.md)** — расстояние между текстом в элементе управления и правым краем элемента управления.

**[PaddingTop](properties-size-location.md)** — расстояние между текстом в элементе управления и верхним краем элемента управления.

**[PressedBorderColor](properties-color-border.md)** — цвет границы элемента управления при щелчке или касании.

**[PressedColor](properties-color-border.md)** — цвет текста в элементе управления при щелчке или касании.

**[PressedFill](properties-color-border.md)** — цвет фона элемента управления при щелчке или касании.

**[Reset](properties-core.md)** — определяет, возвращается ли элемент управления к значению по умолчанию.

**[Size](properties-text.md)** — размер шрифта текста, отображаемого в элементе управления.

**[Strikethrough](properties-text.md)** определяет, когда через текст, отображаемый в элементе управления, проходит линия.

**[Tooltip](properties-core.md)** — пояснительный текст, отображаемый при наведении указателя мыши на элемент управления.

**[Underline](properties-text.md)** определяет, когда под текстом, отображаемым в элементе управления, проходит линия.

**[VerticalAlign](properties-text.md)** — расположение текста в элементе управления относительно центра этого элемента управления по вертикали.

**[Visible](properties-core.md)** определяет, отображается ли элемент управления или он скрыт.

**[Width](properties-size-location.md)** — расстояние между левым и правым краем элемента управления.

**[X](properties-size-location.md)** — расстояние между левым краем элемента управления и левым краем его родительского контейнера (или экрана, если родительского контейнера нет).

**[Y](properties-size-location.md)** — расстояние между верхним краем элемента управления и верхним краем его родительского контейнера (или экрана, если родительского контейнера нет).

## <a name="related-functions"></a>Связанные функции
[**If**( *Condition*; *Result* )](../functions/function-if.md)

## <a name="example"></a>Пример
1. Добавьте элемент управления **Флажок**, назовите его **chkReserve** и укажите для свойства **[Text](properties-core.md)** значение **Зарезервировать**.
   
    Не знаете, как [добавить, назвать и настроить элемент управления](../add-configure-controls.md)?
2. Добавьте элемент управления **[Средство выбора даты](control-date-picker.md)** и укажите для свойства **[Visible](properties-core.md)** следующую формулу:
   <br>**If(chkReserve.Value = true, true)**
   
    Нужны дополнительные сведения о функции **[If](../functions/function-if.md)** или [других функциях](../formula-reference.md)?
3. Нажмите клавишу F5, выберите элемент **chkReserve** и укажите для свойства **[Value](properties-core.md)** значение **true**, затем еще раз выберите элемент **chkReserve** и укажите для свойства **[Value](properties-core.md)** значение **false**.
   
    Элемент управления **[Средство выбора даты](control-date-picker.md)** отображается, когда свойство **[Value](properties-core.md)** элемента **chkReserve** имеет значение **true**, но не отображается при значении **false**.
4. Нажмите клавишу ESC, чтобы вернуться в рабочую область по умолчанию.

