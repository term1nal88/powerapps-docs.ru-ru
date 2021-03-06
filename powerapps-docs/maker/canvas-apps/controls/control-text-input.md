---
title: Справка по элементу управления "Текстовое поле" | Документация Майкрософт
description: Сведения об элементе управления "Текстовое поле" с описанием его свойств и примерами
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a46635276f6598cf0591dc21ae5aeb855b6667c1
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42830554"
---
# <a name="text-input-control-in-powerapps"></a>Элемент управления "Текстовое поле" в PowerApps
Поле, в котором пользователь может вводить текст, числа и другие данные.

## <a name="description"></a>Описание
Пользователь может вводить данные в элементе управления "Текстовое поле". В зависимости от настройки приложения эти данные могут добавляться в источник, использоваться для вычисления временного значения или применяться иным способом.

## <a name="key-properties"></a>Основные свойства
**[Default](properties-core.md)**. Начальное значение элемента управления до его изменения пользователем.

**[Text](properties-core.md)**  — текст, отображаемый в элементе управления, или текст, который пользователь вводит в элемент управления.

## <a name="additional-properties"></a>Дополнительные свойства
**[AccessibleLabel](properties-accessibility.md)** — метка для средств чтения с экрана.

**[Align](properties-text.md)**  — расположение текста относительно центра элемента управления по горизонтали.

**[BorderColor](properties-color-border.md)**  — цвет границы элемента управления.

**[BorderStyle](properties-color-border.md)**  — стиль границы элемента управления: **Сплошная**, **Штриховая**, **Пунктирная** или **Отсутствует**.

**[BorderThickness](properties-color-border.md)**  — толщина границы элемента управления.

**Clear** — определяет, отображается ли в текстовом поле значок "X", с помощью которого пользователь может очистить содержимое элемента управления.

**[Color](properties-color-border.md)**  — цвет текста в элементе управления.

**DelayOutput** — при значении true вводимые пользователем данные регистрируются после задержки в половину секунды.  Можно задерживать ресурсоемкие операции, пока пользователь не завершит ввод текста (например, для фильтрации, если входные данные используются в других формулах).

**[DisplayMode](properties-core.md)** — в зависимости от значения этого режима элемент управления разрешает пользователю вводить данные (**Изменение**), только отображает данные (**Просмотр**) или элемент вообще отключен (**Отключено**).

**[DisabledBorderColor](properties-color-border.md)** — цвет границы элемента управления, если для его свойства **[DisplayMode](properties-core.md)** установлено значение **Отключено**.

**[DisabledColor](properties-color-border.md)** — цвет текста в элементе управления, если для его свойства **[DisplayMode](properties-core.md)** установлено значение **Отключено**.

**[DisabledFill](properties-color-border.md)** — цвет фона элемента управления, если для его свойства **[DisplayMode](properties-core.md)** установлено значение **Отключено**.

**[Fill](properties-color-border.md)**  — цвет фона элемента управления.

**[FocusedBorderColor](properties-color-border.md)** — цвет границы элемента управления при наведении фокуса.

**[FocusedBorderThickness](properties-color-border.md)** — толщина границы элемента управления при наведении фокуса.

**[Font](properties-text.md)**  — имя семейства шрифтов, используемых для отображения текста.

**[FontWeight](properties-text.md)**  — толщина текста в элементе управления: **Жирный**, **Полужирный**, **Обычный** или **Очень тонкий**.

**Format** — это значение определяет, может ли пользователь вводить только цифры или любой другой текст.

**[Height](properties-size-location.md)**  — расстояние между верхним и нижним краем элемента управления.

**HintText** — текст светло-серого цвета, отображаемый в пустом текстовом поле.

**[HoverBorderColor](properties-color-border.md)**  — цвет границы элемента управления при удерживании указателя мыши на нем.

**[HoverColor](properties-color-border.md)**  — цвет текста в элементе управления при удерживании указателя мыши на нем.

**[HoverFill](properties-color-border.md)**  — цвет фона элемента управления при удерживании указателя мыши на нем.

**[Italic](properties-text.md)** определяет, когда текст в элементе управления отображается курсивом.

**[LineHeight](properties-text.md)**  — расстояние, например, между строками текста или элементами списка.

**MaxLength** — количество символов, которые может ввести пользователь в элементе управления "Текстовое поле".

**Mode** — определяет режим **SingleLine** (Однострочный), **MultiLine** (Многострочный) или **Password** (Пароль).

**[OnChange](properties-core.md)**  — поведение приложения, когда пользователь изменяет значение элемента управления (например, перемещая ползунок).

**[OnSelect](properties-core.md)**  — поведение приложения, когда пользователь щелкает элемент управления или касается его.

**[PaddingBottom](properties-size-location.md)**  — расстояние между текстом в элементе управления и нижним краем элемента управления.

**[PaddingLeft](properties-size-location.md)**  — расстояние между текстом в элементе управления и левым краем элемента управления.

**[PaddingRight](properties-size-location.md)**  — расстояние между текстом в элементе управления и правым краем элемента управления.

**[PaddingTop](properties-size-location.md)**  — расстояние между текстом в элементе управления и верхним краем элемента управления.

**[PressedBorderColor](properties-color-border.md)**  — цвет границы элемента управления при щелчке или касании.

**[PressedColor](properties-color-border.md)**  — цвет текста в элементе управления при щелчке или касании.

**[PressedFill](properties-color-border.md)**  — цвет фона элемента управления при щелчке или касании.

**[RadiusBottomLeft](properties-size-location.md)**  — градус скругления нижнего левого угла элемента управления.

**[RadiusBottomRight](properties-size-location.md)**  — градус скругления нижнего правого угла элемента управления.

**[RadiusTopLeft](properties-size-location.md)**  — градус, до которого округляется верхний левый угол элемента управления.

**[RadiusTopRight](properties-size-location.md)**  — градус скругления верхнего правого угла элемента управления.

**[Reset](properties-core.md)**  — определяет, возвращается ли элемент управления к значению по умолчанию.

**[Size](properties-text.md)**  — размер шрифта текста, отображаемого в элементе управления.

**[Strikethrough](properties-text.md)** определяет, когда через текст, отображаемый в элементе управления, проходит линия.

**[TabIndex](properties-accessibility.md)** — порядок навигации с помощью клавиатуры относительно других элементов управления.

**[Tooltip](properties-core.md)** — пояснительный текст, отображаемый при наведении указателя мыши на элемент управления.

**[Underline](properties-text.md)** определяет, когда под текстом, отображаемым в элементе управления, проходит линия.

**[Visible](properties-core.md)** определяет, отображается ли элемент управления или он скрыт.

**[Width](properties-size-location.md)**  — расстояние между левым и правым краем элемента управления.

**[X](properties-size-location.md)**  — расстояние между левым краем элемента управления и левым краем его родительского контейнера (или экрана, если родительского контейнера нет).

**[Y](properties-size-location.md)**  — расстояние между верхним краем элемента управления и верхним краем его родительского контейнера (или экрана, если родительского контейнера нет).

## <a name="related-functions"></a>Связанные функции
[**DateTimeValue**(*строка*)](../functions/function-datevalue-timevalue.md)

## <a name="examples"></a>Примеры
### <a name="collect-data"></a>Сбор данных
1. Добавьте два элемента управления "Текстовое поле" и назовите их **inputFirst** и **inputLast**.
   
    Не знаете, как [добавить, назвать и настроить элемент управления](../add-configure-controls.md)?
2. Добавьте кнопку, укажите для ее свойства **[Text](properties-core.md)** значение **Добавить**, а для свойства **[OnSelect](properties-core.md)** следующую формулу:<br>
   **Collect(Names, {FirstName:inputFirst.Text, LastName:inputLast.Text})**
   
    Нужны дополнительные сведения о функции **[Collect](../functions/function-clear-collect-clearcollect.md)** или [других функциях](../formula-reference.md)?
3. Добавьте коллекцию текстов в портретной (вертикальной) ориентации, укажите для свойства **[Items](properties-core.md)** значение **Names**, а для свойства **[Text](properties-core.md)** элемента **Subtitle1** значение **ThisItem.FirstName**.
4. (Необязательно.) В коллекции шаблонов удалите нижнюю метку с именем **Body1** и укажите для свойства **[TemplateSize](control-gallery.md)** коллекции значение **80**.
5. Нажмите клавишу F5, введите строку текста в элементах **inputFirst** и **inputLast**, затем нажмите кнопку **Добавить**.
6. (Необязательно) Добавьте другие имена в коллекцию, а затем нажмите клавишу ESC, чтобы вернуться в рабочую область по умолчанию.

### <a name="prompt-for-a-password"></a>Запрос пароля

1. Добавьте элемент управления "Текстовое поле", назовите его **inputPassword** и укажите для свойства **Mode** значение **Password**.

1. Добавьте метку и установите в ее свойстве **[Text](properties-core.md)** формулу:<br>
   **If(inputPassword.Text = "P@ssw0rd", "Доступ предоставлен", "Доступ запрещен")**

    Нуждаетесь в дополнительных сведениях о функции **[If](../functions/function-if.md)** или [других функциях](../formula-reference.md)?

1. Нажмите клавишу F5 и введите **P@ssw0rd** в элементе **inputPassword**.

    Когда вы закончите вводить пароль, в метке вместо значения **Доступ запрещен** будет отображаться значение **Доступ предоставлен**.

1. Нажмите клавишу ESC, чтобы вернуться в рабочую область по умолчанию.

1. (Необязательно) Добавьте стрелку, настройте ее для перехода на другой экран и отображайте только после того, как пользователь введет пароль.

1. (Необязательно) Добавьте кнопку, настройте ее свойство **[Text](properties-core.md)** для отображения значения **Войти**, добавьте таймер и отключайте элемент управления "Текстовое поле" на определенное время, если пользователь вводит неправильный пароль и нажимает кнопку **Войти**.


## <a name="accessibility-guidelines"></a>Руководство по настройке специальных возможностей
### <a name="color-contrast"></a>Контрастность
* Применяются [стандартные требования по цветовому контрасту](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Поддержка средства чтения с экрана
* Должен присутствовать элемент **[AccessibleLabel](properties-accessibility.md)**.

### <a name="keyboard-support"></a>Поддержка клавиатуры
* Значение элемента **[TabIndex](properties-accessibility.md)** должно быть равно нулю или больше нуля, чтобы пользователи могли использовать навигацию с помощью клавиатуры.
* Индикаторы фокуса должны быть хорошо видны. Для этого используются элементы **[FocusedBorderColor](properties-color-border.md)** и **[FocusedBorderThickness](properties-color-border.md)**.
 
