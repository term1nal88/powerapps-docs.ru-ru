---
title: "Справка по элементу управления \"HTML-текст\" | Документация Майкрософт"
description: "Сведения об элементе управления \"HTML-текст\" с описанием его свойств и примерами"
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
ms.openlocfilehash: bb652f3ba6decad7cb6f93007eaec6340f230ca1
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2018
---
# <a name="html-text-control-in-powerapps"></a>Элемент управления "HTML-текст" в PowerApps
Поле, в котором отображается текст, а HTML-теги преобразуются в форматирование.

## <a name="description"></a>Описание
Элемент управления **HTML-текст** не только отображает обычный текст и числа, но и преобразует HTML-теги, например неразрывные пробелы.

## <a name="key-properties"></a>Основные свойства
**[Color](properties-color-border.md)** — цвет текста в элементе управления.

**[Font](properties-text.md)** — имя семейства шрифтов, используемых для отображения текста.

**HTMLText** — текст, который отображается в элементе управления "HTML-текст" и может содержать HTML-теги.

## <a name="additional-properties"></a>Дополнительные свойства
**[BorderColor](properties-color-border.md)** — цвет границы элемента управления.

**[BorderStyle](properties-color-border.md)** — стиль границы элемента управления: **Сплошная**, **Штриховая**, **Пунктирная** или **Отсутствует**.

**[BorderThickness](properties-color-border.md)** — толщина границы элемента управления.

**[DisplayMode](properties-core.md)** — в зависимости от значения этого режима элемент управления разрешает пользователю вводить данные (**Изменение**), только отображает данные (**Просмотр**) или элемент вообще отключен (**Отключено**).

**[DisabledBorderColor](properties-color-border.md)** — цвет границы элемента управления, если для его свойства **[DisplayMode](properties-core.md)** установлено значение **Отключено**.

**[DisabledFill](properties-color-border.md)** — цвет фона элемента управления, если для его свойства **[DisplayMode](properties-core.md)** установлено значение **Отключено**.

**[Fill](properties-color-border.md)** — цвет фона элемента управления.

**[Height](properties-size-location.md)** — расстояние между верхним и нижним краем элемента управления.

**[HoverBorderColor](properties-color-border.md)** — цвет границы элемента управления при удерживании указателя мыши на нем.

**[OnSelect](properties-core.md)** — поведение приложения, когда пользователь щелкает элемент управления или касается его.

**[PaddingBottom](properties-size-location.md)** — расстояние между текстом в элементе управления и нижним краем элемента управления.

**[PaddingLeft](properties-size-location.md)** — расстояние между текстом в элементе управления и левым краем элемента управления.

**[PaddingRight](properties-size-location.md)** — расстояние между текстом в элементе управления и правым краем элемента управления.

**[PaddingTop](properties-size-location.md)** — расстояние между текстом в элементе управления и верхним краем элемента управления.

**[Size](properties-text.md)** — размер шрифта текста, отображаемого в элементе управления.

**[Tooltip](properties-core.md)** — пояснительный текст, отображаемый при наведении указателя мыши на элемент управления.

**[Visible](properties-core.md)** определяет, отображается ли элемент управления или он скрыт.

**[Width](properties-size-location.md)** — расстояние между левым и правым краем элемента управления.

**[X](properties-size-location.md)** — расстояние между левым краем элемента управления и левым краем его родительского контейнера (или экрана, если родительского контейнера нет).

**[Y](properties-size-location.md)** — расстояние между верхним краем элемента управления и верхним краем его родительского контейнера (или экрана, если родительского контейнера нет).

## <a name="related-functions"></a>Связанные функции
[**Find**(*текст_для_поиска*, *в_тексте*)](../functions/function-find.md)

## <a name="example"></a>Пример
1. Добавьте элемент управления **[Метка](control-text-box.md)**, назовите его **Source** и укажите в качестве значения свойства **[Text](properties-core.md)** следующую строку:

\<p> Мы достигли необычайно \&nbsp; \&quot; глубокого \&quot; уровня глобализации и локализации. \<p>

Не знаете, как [добавить, назвать и настроить элемент управления](../add-configure-controls.md)?

1. Добавьте элемент управления **HTML-текст** и укажите для свойства **HTMLText** следующее значение:<br>
   **Source.Text**
   
     В элементе управления **HTML-текст** отображается тот же текст, что и в элементе управления **[Метка](control-text-box.md)**, но теги преобразуются в соответствующие символы.

