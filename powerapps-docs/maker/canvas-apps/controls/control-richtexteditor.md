---
title: Справка по элементу управления "Редактор форматированного текста" | Документы Майкрософт
description: Сведения об элементе управления "Редактор форматированного текста" с описанием его свойств и примерами
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/24/2018
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e469cc3769c8deeb5046dc79f34b9ae42788b2d2
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42865181"
---
# <a name="rich-text-editor-control-experimental-in-powerapps"></a>Элемент управления "Редактор форматированного текста" (экспериментальная функция) в PowerApps
Экспериментальный элемент управления, который позволяет пользователям форматировать текст в режиме WYSIWYG.  Выходные данные имеют формат HTML.

## <a name="description"></a>Описание
Элемент управления **Редактор форматированного текста** предоставляет пользователям приложения область для форматирования текста в режиме WYSIWYG.  Входные и выходные данные элемента управления имеют формат HTML.

Элемент управления позволяет вставлять форматированный текст, скопированный, например, из веб-браузера или приложения Word.  

Элемент управления предназначен для форматирования текста и не гарантирует сохранения целостности входных данных в формате HTML.  Теги скрипта, стиля, объекта и другие потенциально опасные теги удаляются редактором.  Это означает, что, если форматированный текст был создан вне PowerApps, он может выглядеть не так, как в приложении, в котором он был создан.

В настоящее время поддерживаются следующие возможности:
- полужирное и курсивное начертание, подчеркивание;
- цвет текста, цвет выделения;
- размер текста;
- нумерованные списки, маркированные списки;
- гиперссылки;
- удаление форматирования.

Чтобы использовать элемент управления в форме, выберите карточку "Изменить многострочный текст" и настройте ее, вставив элемент управления "Редактор форматированного текста".

## <a name="limitations"></a>Ограничения
Текущая версия элемента управления является экспериментальной и имеет указанные ниже временные ограничения.
- Элемент управления имеет ограниченные возможности форматирования текста.  

- Элемент управления в основном предназначен для использования в браузерах на больших экранах.  Использовать его на мобильном телефоне может быть неудобно.

- Известные проблемы при работе в студии Windows или браузере Edge.  В настоящее время рекомендуется использовать веб-студию в Chrome.


## <a name="key-properties"></a>Основные свойства
**[Default](properties-core.md)**  — входное свойство, определяющее начальный текст, отображаемый в редакторе.

**HtmlText** — выходное свойство, содержащее итоговый форматированный текст в формате HTML.



## <a name="additional-properties"></a>Дополнительные свойства
**[AccessibleLabel](properties-accessibility.md)** — метка для средств чтения с экрана. Необходимо описать назначение вложений.

**[DisplayMode](properties-core.md)** — в зависимости от значения этого режима элемент управления разрешает пользователю добавлять и редактировать файлы (**Изменение**) или только отображать данные (**Просмотр**), либо элемент будет вообще отключен (**Отключено**).

**[Height](properties-size-location.md)**  — расстояние между верхним и нижним краем элемента управления.

**[TabIndex](properties-accessibility.md)** — порядок навигации с помощью клавиатуры относительно других элементов управления.

**[Visible](properties-core.md)** — отображение или скрытие элемента управления.

**[Width](properties-size-location.md)**  — расстояние между левым и правым краем элемента управления.

**[X](properties-size-location.md)** — расстояние между левым краем элемента управления и левым краем его родительского контейнера (или экрана, если родительского контейнера нет).

**[Y](properties-size-location.md)** — расстояние между верхним краем элемента управления и верхним краем его родительского контейнера (или экрана, если родительского контейнера нет).
