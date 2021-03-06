---
title: Справка по элементу управления "Коллекция" | Документация Майкрософт
description: Сведения об элементе управления "Коллекция" с описанием его свойств и примерами
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/25/2017
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 710bc4a11e4de9921e0efa077cb0e18f58f09cb5
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42831511"
---
# <a name="gallery-control-in-powerapps"></a>Элемент управления "Коллекция" в PowerApps
Элемент управления, содержащий другие элементы управления и отображающий набор данных.

## <a name="description"></a>Описание
Элемент управления **Коллекция** отображает несколько записей из источника данных, и каждая запись может содержать данные нескольких типов. Например, элемент управления **Коллекция** может отображать несколько контактов, включая имя, адрес и номер телефона для каждого из них. Каждое поле данных отображается в отдельном элементе управления в составе элемента управления **Коллекция**, и вы можете настраивать эти элементы управления в шаблоне. Шаблон отображается в качестве первого элемента коллекции с левого края элемента управления **Коллекция** в горизонтальной (альбомной) ориентации и вверху элемента управления **Коллекция** в вертикальной (книжной) ориентации. Все внесенные в шаблон изменения отражаются во всем элементе управления **Коллекция**.

Доступны готовые шаблоны коллекции для отображения изображений, текста и коллекции с элементами переменной высоты.

## <a name="key-properties"></a>Основные свойства
**[Default](properties-core.md)**  — элемент или запись из источника данных, выбираемые в коллекции при запуске приложения.

**[Items](properties-core.md)** — источник данных, отображаемых в элементе управления, такой как коллекция, список или диаграмма.

**Selected** — выбранный элемент.

## <a name="additional-properties"></a>Дополнительные свойства
**[AccessibleLabel](properties-accessibility.md)** — метка для средств чтения с экрана. Должна описывать список элементов.

**AllItems** — все элементы в коллекции, включая дополнительные значения элементов управления, которые являются частью шаблона коллекции.

**[BorderColor](properties-color-border.md)**  — цвет границы элемента управления.

**[BorderStyle](properties-color-border.md)**  — стиль границы элемента управления: **Сплошная**, **Штриховая**, **Пунктирная** или **Отсутствует**.

**[BorderThickness](properties-color-border.md)**  — толщина границы элемента управления.

**[DisplayMode](properties-core.md)** — в зависимости от значения этого режима элемент управления разрешает пользователю вводить данные (**Изменение**), только отображает данные (**Просмотр**) или элемент вообще отключен (**Отключено**).

**[Fill](properties-color-border.md)**  — цвет фона элемента управления.

**[Height](properties-size-location.md)**  — расстояние между верхним и нижним краем элемента управления.

**Layout** — направление прокрутки коллекции или передвижения ползунка пользователем: сверху вниз (**Vertical**) или слева направо (**Horizontal**).

**NavigationStep** — определяет шаг прокрутки коллекции, если ее свойству **ShowNavigation** присвоено значение **true** и пользователь выбрал стрелку навигации на любом конце этой коллекции.

**ShowNavigation** — определяет появление стрелки на каждом конце коллекции, с помощью которой пользователь сможет прокручивать элементы.

**ShowScrollbar** — определяет появление полосы прокрутки при наведении пользователем указателя на коллекцию.

**Snap** — при прокрутке пользователем коллекции определяет ее автоматическую привязку, которая позволяет отображать следующий элемент целиком.

**TemplateFill** — цвет фона коллекции.

**TemplatePadding** — расстояние между элементами в коллекции.

**TemplateSize** — высота шаблона коллекции в вертикальной (книжной) ориентации или его ширина в горизонтальной (альбомной) ориентации.

**Transition** — визуальный эффект (**Pop**, **Push** или **None**) при наведении пользователем указателя на элемент коллекции.

**[Visible](properties-core.md)** определяет, отображается ли элемент управления или он скрыт.

**[Width](properties-size-location.md)**  — расстояние между левым и правым краем элемента управления.

**WrapCount** — количество отображаемых элементов в строке (горизонтальный макет) или столбце (вертикальный макет).

**[X](properties-size-location.md)**  — расстояние между левым краем элемента управления и левым краем его родительского контейнера (или экрана, если родительского контейнера нет).

**[Y](properties-size-location.md)**  — расстояние между верхним краем элемента управления и верхним краем его родительского контейнера (или экрана, если родительского контейнера нет).

## <a name="related-functions"></a>Связанные функции
[**Filter**(*источник*, *формула*)](../functions/function-filter-lookup.md)

## <a name="examples"></a>Примеры
### <a name="show-and-filter-data"></a>Отображение и фильтрация данных
* [Отображение текста](control-text-box.md#show-data-in-a-gallery)
* [Отображение изображений](control-image.md#show-a-set-of-images-from-a-data-source)
* [Фильтрация данных с помощью выбора элемента списка](control-drop-down.md#example)
* [Фильтрация данных с помощью ползунка](control-slider.md#example)

### <a name="get-data-from-the-user"></a>Получение данных от пользователя
* [Получение текста](control-text-input.md#collect-data)
* [Получение изображений](control-add-picture.md#add-images-to-an-image-gallery-control)
* [Получение фотографий](control-camera.md#example)
* [Получение звуков](control-microphone.md#example)
* [Получение рисунков](control-pen-input.md#create-a-set-of-images)


## <a name="accessibility-guidelines"></a>Руководство по настройке специальных возможностей
### <a name="color-contrast"></a>Контрастность
Так как при щелчке в любом месте элемента коллекции должен происходить его выбор, следует установить достаточную контрастность между следующими элементами:
* элементом **[BorderColor](properties-color-border.md)** и цветом за пределами коллекции (если есть граница);
* элементом **[Fill](properties-color-border.md)** и цветом за пределами коллекции (если нет границы).

### <a name="screen-reader-support"></a>Поддержка средства чтения с экрана
* Должен присутствовать элемент **[AccessibleLabel](properties-accessibility.md)**.

    > [!NOTE]
  > Средства чтения с экрана проинформируют об изменениях в коллекции. **AccessibleLabel** также упоминается. Так обеспечивается контекст оповещения. Это еще важнее при наличии нескольких коллекций на экране.

### <a name="keyboard-support"></a>Поддержка клавиатуры
* Установите для параметра **ShowScrollbar** значение **true**. На большинстве устройств с сенсорным экраном полоса прокрутки не отображается, пока не начнется прокрутка.
* Так как при щелчке в любом месте элемента коллекции должен происходить его выбор, поэтому для клавиатуры также должны быть предусмотрены аналогичные действия. Например, при добавлении **[кнопки](control-button.md)**, для свойства **OnSelect** задано значение **Select(Parent)** 

    > [!NOTE]
  > Элементы управления вне коллекции не учитываются в порядке навигации с клавиатуры внутри коллекции. Значения **[TabIndex](properties-accessibility.md)** элементов управления внутри коллекции находятся в области. Дополнительные сведения см. в разделе [свойства специальных возможностей](properties-accessibility.md).
