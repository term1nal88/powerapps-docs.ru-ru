---
title: Справка по элементу управления "Таймер" | Документация Майкрософт
description: Сведения об элементе управления "Таймер" с описанием его свойств и примерами
services: ''
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 008c992ad3452c1844064335a51593c222fb1ac1
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="timer-control-in-powerapps"></a>Элемент управления "Таймер" в PowerApps
Элемент управления, определяющий поведение приложения по истечении заданного количества времени.

## <a name="description"></a>Описание
Например, таймеры могут определять, как долго отображается элемент управления или как изменяются его свойства по истечении заданного количества времени.

Обратите внимание, что необходимо перейти в режим предварительного просмотра приложения, чтобы запустить таймер в конструкторе.  Так пользователь сможет настроить таймер в конструкторе без ограничения по времени.

## <a name="key-properties"></a>Основные свойства
**Duration** — продолжительность работы таймера в миллисекундах.  Максимальное значение отсутствует.

**OnTimerEnd** — поведение приложения по окончании работы таймера.

**Repeat** — определяет, будет ли таймер автоматически перезапускаться по окончании работы.

## <a name="additional-properties"></a>Дополнительные свойства
**[Align](properties-text.md)** — расположение текста относительно центра элемента управления по горизонтали.

**AutoPause** — определяет, приостанавливается ли автоматически звуковой или видеоклип при переходе пользователя на другой экран.

**AutoStart** — определяет, запускается ли автоматически элемент управления "Звук" или "Видео" для воспроизведения клипа при переходе пользователя на экран с таким элементом управления.

**[BorderColor](properties-color-border.md)** — цвет границы элемента управления.

**[BorderStyle](properties-color-border.md)** — стиль границы элемента управления: **Сплошная**, **Штриховая**, **Пунктирная** или **Отсутствует**.

**[BorderThickness](properties-color-border.md)** — толщина границы элемента управления.

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

**[OnSelect](properties-core.md)** — поведение приложения, когда пользователь щелкает элемент управления или касается его.

**OnTimerStart** — поведение приложения при запуске таймера.

**[PressedBorderColor](properties-color-border.md)** — цвет границы элемента управления при щелчке или касании.

**[PressedColor](properties-color-border.md)** — цвет текста в элементе управления при щелчке или касании.

**[PressedFill](properties-color-border.md)** — цвет фона элемента управления при щелчке или касании.

**[Reset](properties-core.md)** — определяет, возвращается ли элемент управления к значению по умолчанию.

**[Size](properties-text.md)** — размер шрифта текста, отображаемого в элементе управления.

**Start** — определяет, воспроизводится ли звуковой или видеоклип.

**[Strikethrough](properties-text.md)** определяет, когда через текст, отображаемый в элементе управления, проходит линия.

**[Text](properties-core.md)** — текст, отображаемый в элементе управления, или текст, который пользователь вводит в элемент управления.

**[Tooltip](properties-core.md)** — пояснительный текст, отображаемый при наведении указателя мыши на элемент управления.

**[Underline](properties-text.md)** определяет, когда под текстом, отображаемым в элементе управления, проходит линия.

**[Visible](properties-core.md)** определяет, отображается ли элемент управления или он скрыт.

**[Width](properties-size-location.md)** — расстояние между левым и правым краем элемента управления.

**[X](properties-size-location.md)** — расстояние между левым краем элемента управления и левым краем его родительского контейнера (или экрана, если родительского контейнера нет).

**[Y](properties-size-location.md)** — расстояние между верхним краем элемента управления и верхним краем его родительского контейнера (или экрана, если родительского контейнера нет).

## <a name="related-functions"></a>Связанные функции
[**Refresh**(*источник_данных*)](../functions/function-refresh.md)

## <a name="examples"></a>Примеры
### <a name="show-a-countdown"></a>Отображение обратного отсчета
1. Добавьте таймер и назовите его **Countdown**.

    Не знаете, как [добавить, назвать и настроить элемент управления](../add-configure-controls.md)?
2. Укажите для свойства **Duration** значение **10000**, а для свойств **Repeat** и **Autostart** — значение **true**.
3. (Необязательно) Сделайте таймер удобным для чтения, указав следующие значения для перечисленных свойств: **[Height](properties-size-location.md)** — **160**, **[Width](properties-size-location.md)** — **600** и **[Size](properties-text.md)** — **60**.
4. Добавьте метку и установите в ее свойстве **[Text](properties-core.md)** формулу:
   <br>**"Осталось секунд: " & RoundUp(10-Countdown.Value/1000, 0)**

    Нужны дополнительные сведения о функции **[RoundUp](../functions/function-round.md)** или [других функциях](../formula-reference.md)?

    В метке отображается количество секунд, оставшихся до перезапуска таймера.
5. (Необязательно) Укажите для свойства **[Visible](properties-core.md)** таймера значение **false**.

### <a name="animate-a-control"></a>Анимация элемента управления
1. Добавьте таймер и назовите его **FadeIn**.

    Не знаете, как [добавить, назвать и настроить элемент управления](../add-configure-controls.md)?
2. Укажите для свойства **Duration** значение **5000**, а для свойств **Repeat** и **Autostart** — значение **true**.
3. (Необязательно) Сделайте таймер удобным для чтения, указав следующие значения для перечисленных свойств: **[Height](properties-size-location.md)** — **160**, **[Width](properties-size-location.md)** — **600** и **[Size](properties-text.md)** — **60**.
4. Добавьте метку и задайте для свойства **[Text](properties-core.md)** отображение слова **Приветствуем!**, а для свойства **[Color](properties-color-border.md)** — следующую формулу:
   <br>**ColorFade(Color.BlueViolet, FadeIn.Value/5000)**

    Нужны дополнительные сведения о функции **[ColorFade](../functions/function-colors.md)** или [других функциях](../formula-reference.md)?

    Текст в метке выцветает до белого, затем возвращается к полной насыщенности, и этот процесс повторяется.
5. (Необязательно) Укажите для свойства **[Visible](properties-core.md)** таймера значение **false**.