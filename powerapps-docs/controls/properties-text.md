---
title: "Свойства текста | Документация Майкрософт"
description: "Справочные сведения о таких свойствах, как Text, Tooltip и HintText."
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
ms.openlocfilehash: 1f3d05d98755e8f0eff8af5e3dde5921d0de0301
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2017
---
# <a name="text-properties-in-powerapps"></a>Текстовые свойства в PowerApps
## <a name="overview"></a>Обзор
Настройка текста, отображаемого в элементе управления, подсказке и указании, отображаемом при вводе данных пользователем, а также задание других характеристик текста.

## <a name="text-appearance"></a>Оформление текста
**Font** — имя семейства шрифтов, используемого для отображения текста.

* Применяется к элементам управления **[Добавить изображение](control-add-picture.md)**, **[Кнопка](control-button.md)**, **[Флажок](control-check-box.md)**, **[Гистограмма](control-column-line-chart.md)**, **[Средство выбора даты](control-date-picker.md)**, **[Раскрывающийся список](control-drop-down.md)**, **[Экспорт](control-export-import.md)**, **[HTML-текст](control-html-text.md)**, **[Импорт](control-export-import.md)**, **[Метка](control-text-box.md)**, **[График](control-column-line-chart.md)**, **[Поле со списком](control-list-box.md)**, **[Круговая диаграмма](control-pie-chart.md)**, **[Переключатель](control-radio.md)**, **[Текстовое поле](control-text-input.md)** и **[Таймер](control-timer.md)**.

**FontWeight** — толщина текста в элементе управления: **Bold**, **Semibold**, **Normal** или **Lighter**.

* Применяется к элементам управления **[Добавить изображение](control-add-picture.md)**, **[Кнопка](control-button.md)**, **[Флажок](control-check-box.md)**, **[Средство выбора даты](control-date-picker.md)**, **[Раскрывающийся список](control-drop-down.md)**, **[Экспорт](control-export-import.md)**, **[Импорт](control-export-import.md)**, **[Метка](control-text-box.md)**, **[Поле со списком](control-list-box.md)**, **[Переключатель](control-radio.md)**, **[Текстовое поле](control-text-input.md)** и **[Таймер](control-timer.md)**.

**Italic** — определяет, когда текст в элементе управления отображается курсивом.

* Применяется к элементам управления **[Добавить изображение](control-add-picture.md)**, **[Кнопка](control-button.md)**, **[Флажок](control-check-box.md)**, **[Средство выбора даты](control-date-picker.md)**, **[Раскрывающийся список](control-drop-down.md)**, **[Экспорт](control-export-import.md)**, **[Импорт](control-export-import.md)**, **[Метка](control-text-box.md)**, **[Поле со списком](control-list-box.md)**, **[Переключатель](control-radio.md)**, **[Текстовое поле](control-text-input.md)** и **[Таймер](control-timer.md)**.

**Size** — размер шрифта текста, отображаемого в элементе управления.

* Применяется к элементам управления **[Добавить изображение](control-add-picture.md)**, **[Кнопка](control-button.md)**, **[Флажок](control-check-box.md)**, **[Гистограмма](control-column-line-chart.md)**, **[Средство выбора даты](control-date-picker.md)**, **[Раскрывающийся список](control-drop-down.md)**, **[Экспорт](control-export-import.md)**, **[HTML-текст](control-html-text.md)**, **[Импорт](control-export-import.md)**, **[Метка](control-text-box.md)**, **[График](control-column-line-chart.md)**, **[Поле со списком](control-list-box.md)**, **[Ввод с помощью пера](control-pen-input.md)**, **[Круговая диаграмма](control-pie-chart.md)**, **[Переключатель](control-radio.md)**, **[Текстовое поле](control-text-input.md)** и **[Таймер](control-timer.md)**.

**Strikethrough** — определяет, когда текст, отображаемый в элементе управления, перечеркивается.

* Применяется к элементам управления **[Добавить изображение](control-add-picture.md)**, **[Кнопка](control-button.md)**, **[Флажок](control-check-box.md)**, **[Раскрывающийся список](control-drop-down.md)**, **[Экспорт](control-export-import.md)**, **[Импорт](control-export-import.md)**, **[Метка](control-text-box.md)**, **[Поле со списком](control-list-box.md)**, **[Переключатель](control-radio.md)**, **[Текстовое поле](control-text-input.md)** и **[Таймер](control-timer.md)**.

**Underline** — определяет, когда текст, отображаемый в элементе управления, подчеркивается.

* Применяется к элементам управления **[Добавить изображение](control-add-picture.md)**, **[Кнопка](control-button.md)**, **[Флажок](control-check-box.md)**, **[Раскрывающийся список](control-drop-down.md)**, **[Экспорт](control-export-import.md)**, **[Импорт](control-export-import.md)**, **[Метка](control-text-box.md)**, **[Поле со списком](control-list-box.md)**, **[Переключатель](control-radio.md)**, **[Текстовое поле](control-text-input.md)** и **[Таймер](control-timer.md)**.

## <a name="text-placement"></a>Положение текста
**Align** — расположение текста относительно центра элемента управления по горизонтали.

* Применяется к элементам управления **[Добавить изображение](control-add-picture.md)**, **[Кнопка](control-button.md)**, **[Экспорт](control-export-import.md)**, **[Импорт](control-export-import.md)**, **[Метка](control-text-box.md)**, **[Переключатель](control-radio.md)**, **[Текстовое поле](control-text-input.md)** и **[Таймер](control-timer.md)**.

**LineHeight** — расстояние, например, между строками текста или элементами списка.

* Применяется к элементам управления **[Поле со списком](control-list-box.md)**, **[Метка](control-text-box.md)**, **[Переключатель](control-radio.md)** и **[Текстовое поле](control-text-input.md)**.

**VerticalAlign** — расположение текста относительно центра элемента управления по вертикали.

* Применяется к элементам управления **[Добавление изображения](control-add-picture.md)**, **[Кнопка](control-button.md)**, **[Флажок](control-check-box.md)**, **[Экспорт](control-export-import.md)**, **[Импорт](control-export-import.md)** и **[Метка](control-text-box.md)**.

