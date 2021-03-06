---
title: Справка по элементу управления "Добавить изображение" | Документация Майкрософт
description: Сведения об элементе управления "Добавить изображение" с описанием его свойств и примерами
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1cc2b7c1752abe4f12e76c30f59978fc753f4ac5
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42835658"
---
# <a name="add-picture-control-in-powerapps"></a>Элемент управления "Добавить изображение" в PowerApps
Делает снимок или загружает изображения с локального устройства.

## <a name="description"></a>Описание
С помощью этого элемента управления пользователи могут делать снимки или передавать файлы изображений со своих устройств, а также обновлять источник данных с применением этого содержимого. На мобильном устройстве пользователя откроется диалоговое окно выбора устройства, в котором можно выбрать один из вариантов: сделать снимок или выбирать уже имеющийся.

Этот элемент управления является групповым и состоит из двух элементов — **изображение** и **кнопки добавления мультимедиа**. Элемент управления **Изображение** отображает переданное изображение или заполнитель, если изображение не передавалось. **Кнопка добавления мультимедиа** выдает запрос по передаче изображения.

Свойства **изображения** см. в разделе с [рекомендациями по элементу управления "Изображение"](control-image.md).

## <a name="add-media-button-properties"></a>Свойства кнопки добавления мультимедиа
**[AccessibleLabel](properties-accessibility.md)** — метка для средств чтения с экрана. Должен описывать цель добавления изображения.

**[Align](properties-text.md)**  — расположение текста относительно центра элемента управления по горизонтали.

**[BorderColor](properties-color-border.md)**  — цвет границы элемента управления.

**[BorderStyle](properties-color-border.md)**  — стиль границы элемента управления: **Сплошная**, **Штриховая**, **Пунктирная** или **Отсутствует**.

**[BorderThickness](properties-color-border.md)**  — толщина границы элемента управления.

**ChangePictureText** — текст, появляющийся на кнопке после передачи изображения.

**[Color](properties-color-border.md)**  — цвет текста в элементе управления.

**[DisabledBorderColor](properties-color-border.md)** — цвет границы элемента управления, если для его свойства **[DisplayMode](properties-core.md)** установлено значение **Отключено**.

**[DisabledColor](properties-color-border.md)** — цвет текста в элементе управления, если для его свойства **[DisplayMode](properties-core.md)** установлено значение **Отключено**.

**[DisabledFill](properties-color-border.md)** — цвет фона элемента управления, если для его свойства **[DisplayMode](properties-core.md)** установлено значение **Отключено**.

**[DisplayMode](properties-core.md)** — в зависимости от значения этого режима элемент управления разрешает пользователю вводить данные (**Изменение**), только отображает данные (**Просмотр**) или элемент вообще отключен (**Отключено**).

**Error** — при наличии проблемы с передачей изображения это свойство будет содержать соответствующую строку ошибки.

**[Fill](properties-color-border.md)**  — цвет фона элемента управления.

**[FocusedBorderColor](properties-color-border.md)** — цвет границы элемента управления при наведении фокуса.

**[FocusedBorderThickness](properties-color-border.md)** — толщина границы элемента управления при наведении фокуса.

**[Font](properties-text.md)**  — имя семейства шрифтов, используемых для отображения текста.

**[FontWeight](properties-text.md)**  — толщина текста в элементе управления: **Жирный**, **Полужирный**, **Обычный** или **Очень тонкий**.

**[Height](properties-size-location.md)**  — расстояние между верхним и нижним краем элемента управления.

**[HoverBorderColor](properties-color-border.md)**  — цвет границы элемента управления при удерживании указателя мыши на нем.

**[HoverColor](properties-color-border.md)**  — цвет текста в элементе управления при удерживании указателя мыши на нем.

**[HoverFill](properties-color-border.md)**  — цвет фона элемента управления при удерживании указателя мыши на нем.

**[Italic](properties-text.md)** определяет, когда текст в элементе управления отображается курсивом.

**Media** — идентификатор клипа, воспроизводимого элементом управления "Звук" или "Видео".

**[OnChange](properties-core.md)**  — поведение приложения, когда пользователь изменяет значение элемента управления (например, перемещая ползунок).

**[OnSelect](properties-core.md)**  — поведение приложения, когда пользователь щелкает элемент управления или касается его.

**[Padding](properties-size-location.md)**  — расстояние между текстом кнопки "Импорт" или "Экспорт" и границами кнопки.

**[PressedBorderColor](properties-color-border.md)**  — цвет границы элемента управления при щелчке или касании.

**[PressedColor](properties-color-border.md)**  — цвет текста в элементе управления при щелчке или касании.

**[PressedFill](properties-color-border.md)**  — цвет фона элемента управления при щелчке или касании.

**[Reset](properties-core.md)**  — определяет, возвращается ли элемент управления к значению по умолчанию.

**[Size](properties-text.md)**  — размер шрифта текста, отображаемого в элементе управления.

**[Strikethrough](properties-text.md)** определяет, когда через текст, отображаемый в элементе управления, проходит линия.

**[TabIndex](properties-accessibility.md)** — порядок навигации с помощью клавиатуры относительно других элементов управления.

**[Text](properties-core.md)** — текст, появляющийся на кнопке, если изображение не было передано.

**[Tooltip](properties-core.md)** — пояснительный текст, отображаемый при наведении указателя мыши на элемент управления.

**[Underline](properties-text.md)** определяет, когда под текстом, отображаемым в элементе управления, проходит линия.

**[VerticalAlign](properties-text.md)**  — расположение текста в элементе управления относительно центра этого элемента управления по вертикали.

**[Visible](properties-core.md)** определяет, отображается ли элемент управления или он скрыт.

**[Width](properties-size-location.md)**  — расстояние между левым и правым краем элемента управления.

**[X](properties-size-location.md)**  — расстояние между левым краем элемента управления и левым краем его родительского контейнера (или экрана, если родительского контейнера нет).

**[Y](properties-size-location.md)**  — расстояние между верхним краем элемента управления и верхним краем его родительского контейнера (или экрана, если родительского контейнера нет).

## <a name="related-functions"></a>Связанные функции
[**Patch**( *DataSource*; *BaseRecord*; *ChangeRecord* )](../functions/function-patch.md)

## <a name="examples"></a>Примеры
### <a name="add-images-to-an-image-gallery-control"></a>Добавление изображений в коллекцию
1. Добавьте элемент управления **Добавить изображение** и щелкните его три раза.
   
    Не знаете, как [добавить, назвать и настроить элемент управления](../add-configure-controls.md)?
2. В диалоговом окне **Открыть** выберите файл изображения и нажмите **Открыть**.
3. Добавьте элемент управления **[Кнопка](control-button.md)**, переместите его под элемент управления **Добавить изображение** и укажите для свойства **[OnSelect](properties-core.md)** элемента **[Кнопка](control-button.md)** следующую формулу:<br>
   **Collect(MyPix, AddMediaButton1.Media)**
   
    Нужны дополнительные сведения о функции **[Collect](../functions/function-clear-collect-clearcollect.md)** или [других функциях](../formula-reference.md)?
4. Добавьте элемент управления **Коллекция изображений** и укажите для его свойства **[Items](properties-core.md)** значение **MyPix**.
5. Нажмите клавишу F5 и выберите элемент управления **[Кнопка](control-button.md)**.
   
    Изображение из элемента управления **Добавить изображение** появляется в элементе управления **Коллекция изображений**. Если пропорции вашего изображения отличаются от элемента управления **[Image](control-image.md)** в элементе управления **Коллекция изображений**, укажите для свойства **[ImagePosition](properties-visual.md)** элемента управления **[Image](control-image.md)** значение **Fit**.
6. Нажмите элемент управления **Добавить изображение**, выберите другой файл изображения, нажмите **Открыть**, а затем нажмите добавленный вами элемент управления **[Кнопка](control-button.md)**.
   
    В элементе управления **Коллекция изображений** появляется второе изображение.
7. (Необязательно) Повторите предыдущее действие один и несколько раз, а затем нажмите клавишу ESC, чтобы вернуться в рабочую область по умолчанию.

Для сохранения изображений на локальном устройстве используйте функцию **[SaveData](../functions/function-savedata-loaddata.md)**, а для обновления источника данных — функцию **[Patch](../functions/function-patch.md)**.


## <a name="accessibility-guidelines"></a>Руководство по настройке специальных возможностей
Применяются те же рекомендации, что и для **[кнопки](control-button.md)** и **[изображения](control-image.md)**. Кроме того, рассмотрим следующее.

### <a name="color-contrast"></a>Контрастность
* Текст и фон **кнопки добавления мультимедиа** должны быть достаточно контрастными. Так как в переданном изображении могут присутствовать разные цвета, используйте непрозрачную **[заливку](properties-color-border.md)** для **кнопки добавления мультимедиа**, чтобы гарантировать достаточную контрастность.

### <a name="screen-reader-support"></a>Поддержка средства чтения с экрана
* **Кнопка добавления мультимедиа** должна быть снабжена элементами **Text** и **ChangePictureText**, которые позволяют вывести запрос о добавлении или изменении изображения для пользователя.

### <a name="keyboard-support"></a>Поддержка клавиатуры
* Для элемента **[TabIndex](properties-accessibility.md)** **кнопки добавления мультимедиа** должно быть задано значение ноль или больше, чтобы пользователи могли использовать навигацию с помощью клавиатуры.
* Для **кнопки добавления мультимедиа** должны быть предусмотрены явно различимые индикаторы фокуса. Для этого используйте элементы **[FocusedBorderColor](properties-color-border.md)** и **[FocusedBorderThickness](properties-color-border.md)**.
 
