---
title: Цвета высокой контрастности | Документация Майкрософт
description: Рекомендации по повышению контрастности цветов в PowerApps
author: tahoon
manager: kvivek
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/23/2018
ms.author: tahoon
ms.openlocfilehash: 289026f18d341381d64423e76effb1abf586557c
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2018
ms.locfileid: "39014818"
---
# <a name="accessible-colors-in-powerapps"></a>Цвета высокой контрастности в PowerApps
Используемые в приложении цвета должны восприниматься пользователями с цветовой слепотой и (или) слабым зрением. Все темы PowerApps по умолчанию имеют высокий уровень контрастности. Если вы решите изменить цвета в приложении, соблюдайте эти рекомендации, чтобы обеспечить восприятие цветов. В Интернете можно найти ряд инструментов для выявления проблем с контрастностью цветов.

## <a name="minimum-contrast-for-text"></a>Минимальная контрастность текста
* Контрастность между текстом и фоном должна составлять не менее 4.5:1.
* Для крупного текста следует соблюдать контрастность не менее 3:1.
* К выключенному тексту не применяются требования по контрастности.

На практике это означает, что все интерактивные элементы управления должны иметь достаточную контрастность между следующими значениями:
* **[Color](controls/properties-color-border.md)** и **[Fill](controls/properties-color-border.md)**;
* **[PressedColor](controls/properties-color-border.md)** и **[PressedFill](controls/properties-color-border.md)**;
* **[HoverColor](controls/properties-color-border.md)** и **[HoverFill](controls/properties-color-border.md)**.

## <a name="minimum-contrast-for-non-text"></a>Минимальная контрастность для нетекстовых элементов

> [!NOTE]
> В стандарте [WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html) требования к контрастности определены только для текста. Чтобы повысить читаемость, попробуйте применить еще не утвержденные [рекомендации по контрастности WCAG 2.1](https://www.w3.org/TR/WCAG21/#non-text-contrast), в которых описаны все важные элементы пользовательского интерфейса, например кнопки со значками. Для таких компонентов рекомендуется соблюдать соотношение не менее 3:1. Рекомендации, описанные в этом разделе, **необязательны** для соответствия WCAG 2.0.

### <a name="user-interface-components"></a>Компоненты пользовательского интерфейса
Все интерактивные элементы управления должны иметь достаточную контрастность между следующими значениями:
* **[FocusedBorderColor](controls/properties-color-border.md)** и цвета за пределами элемента.

Дополнительные требования по контрастности цветов применяются для тех элементов управления, у которых вся занимаемая область является интерактивной или информативной. К ним относятся, например, **[Button](controls/control-button.md)** и **[Icon](controls/control-shapes-icons.md)** (используемый в качестве кнопки). Эти требования нужны для того, чтобы элемент управления имел четкие границы и пользователь хорошо понимал, в какой зоне его можно щелкнуть или коснуться.

Если такой элемент управления имеет границу, нужно обеспечить достаточную контрастность между следующими значениями:
* **[BorderColor](controls/properties-color-border.md)** и цвета за пределами элемента;
* **[PressedBorderColor](controls/properties-color-border.md)** и цвета за пределами элемента;
* **[HoverBorderColor](controls/properties-color-border.md)** и цвета за пределами элемента.

Если граница не используется, нужно обеспечить достаточную контрастность между следующими значениями:
* **[Fill](controls/properties-color-border.md)** и цвета за пределами элемента;
* **[PressedFill](controls/properties-color-border.md)** и цвета за пределами элемента;
* **[HoverFill](controls/properties-color-border.md)** и цвета за его пределами.

### <a name="graphical-objects"></a>Графические объекты
Если изображение содержит важные сведения, мы рекомендуем применить к нему требования к контрастности. Это относится к элементам управления, которые могут отображать изображения: **[Audio](controls/control-audio-video.md)**, **[Image](controls/control-image.md)**, **[Microphone](controls/control-microphone.md)** или **[Video](controls/control-audio-video.md)**.

Также мы рекомендуем проверить контрастность для видео. Вместо этого или в дополнение к этому можно также предоставить [скрытые субтитры](controls/control-audio-video.md) с описанием видео.

## <a name="provide-other-visual-cues"></a>Предоставление других визуальных подсказок
Следите за тем, чтобы приложение никогда не передавало информацию только изменением цвета. Например, пользователи, не различающие красный и зеленый цвета, не смогут отличить красный цвет ошибки от зеленого сообщения об успешном завершении.

Чтобы передать такие сообщения, можно использовать дополнительные подсказки, например **[значки](controls/control-shapes-icons.md)**, или стили текста, такие как **[курсив](controls/properties-text.md)** и **[подчеркивание](controls/properties-text.md)**.

## <a name="next-steps"></a>Дальнейшие действия
Узнайте больше о [свойствах специальных возможностей](controls/properties-accessibility.md) в элементах управления PowerApps и воспользуйтесь [проверкой читаемости](accessibility-checker.md).
