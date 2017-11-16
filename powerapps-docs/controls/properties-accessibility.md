---
title: "Свойства специальных возможностей | Документация Майкрософт"
description: "Справочные сведения о таких свойствах, как TabIndex и Tooltip."
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
ms.date: 01/26/2017
ms.author: anneta
ms.openlocfilehash: d8cc9d6c8586856dcaa27f67d3ea1fdc17fa0433
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2017
---
# <a name="accessibility-properties-in-powerapps"></a>Свойства специальных возможностей в PowerApps
## <a name="overview"></a>Обзор
Настройка свойств, предназначенных упростить альтернативные способы взаимодействия с элементами управления, подходящие для пользователей с ослабленным зрением.

## <a name="properties"></a>Свойства
**Tooltip** — пояснительный текст, отображаемый при наведении указателя мыши на элемент управления.  Текст используется в метках Aria, предназначенных для средств чтения с экрана.

* Применяется к элементам управления **[Звук](control-audio-video.md)**, **[Кнопка](control-button.md)**, **[Камера](control-camera.md)**, **[Флажок](control-check-box.md)**, **[Раскрывающийся список](control-drop-down.md)**, **[HTML-текст](control-html-text.md)**, **[Изображение](control-image.md)**, **[Метка](control-text-box.md)**, **[Поле со списком](control-list-box.md)**, **[Микрофон](control-microphone.md)**, **[Средство просмотра PDF](control-pdf-viewer.md)**, **[Ввод с помощью пера](control-pen-input.md)**, **[Переключатель](control-radio.md)**, **[Оценка](control-rating.md)**, **[Ползунок](control-slider.md)**, **[Текстовое поле](control-text-input.md)**, **[Таймер](control-timer.md)**, **[Переключатель](control-toggle.md)** и **[Видео](control-audio-video.md)**.

**TabIndex** — определяет последовательность перехода между элементами управления с помощью клавиши TAB.

Нулевое значение по умолчанию задает последовательность перехода по умолчанию, в зависимости от координат X и Y элемента управления.  Если задать значение больше нуля, то при переходе элемент управления будет предшествовать всем элементам управления со значениями по умолчанию.  При переходе элемент управления со значением 2 свойства TabIndex будет предшествовать элементу управления со свойством TabIndex, имеющим значение 3 или выше.

Обратите внимание, что в таких контейнерах, как элементы управления "Форма" и "Коллекция", при переходе всегда перебираются все элементы в контейнере, и только потом происходит переход к элементам управления за его пределами.  Порядковый номер контейнера при переходе равен наименьшему значению свойства TabIndex дочернего элемента управления.

Если задать для параметра TabIndex значение -1, на вкладке будет отключен доступ к элементу управления. Изображения, значки и фигуры также будут невидимы для средства чтения с экрана.

* Это относится к элементам управления **[Кнопка](control-button.md)**, **[Средство выбора даты](control-date-picker.md)**, **[Раскрывающийся список](control-drop-down.md)**, **[Изображение](control-image.md)**, **[Импорт](control-export-import.md)**, **[Поле со списком](control-list-box.md)**, **[Переключатель](control-radio.md)**, **[Оценка](control-rating.md)**, **[Ползунок](control-slider.md)**, **[Текстовое поле](control-text-input.md)** и **[Переключатель](control-toggle.md)**.

