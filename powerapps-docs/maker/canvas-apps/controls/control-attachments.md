---
title: Справка по элементу управления "Вложения" | Документация Майкрософт
description: Сведения об элементе управления "Вложения" с описанием его свойств и примерами
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 04/23/2018
ms.author: fikaradz
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: da9c8f85844e37d6af8e1063b36496c820fbfa07
ms.sourcegitcommit: e2a9d1a6090cdd8aa78515b49f38ed2365217ea6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49384255"
---
# <a name="attachments-control-in-powerapps"></a>Элемент управления "Вложения" в PowerApps
Элемент управления, который позволяет пользователям скачивать файлы на устройства, а также добавлять их в список SharePoint или сущность Common Data Service for Apps и удалять их оттуда.

## <a name="limitations"></a>Ограничения
Элемент управления вложениями имеет следующие ограничения.
1. Вложения поддерживаются в списках SharePoint и сущностях CDS for Apps.

1. Функции передачи и удаления поддерживаются только в форме.  Элемент управления вложениями будет недоступен в режиме редактирования, но не в форме. Учтите, что для сохранения результатов добавления и удаления на серверной части пользователь должен сохранить форму.

1. Вы можете передавать файлы размером до 10 МБ.  

## <a name="description"></a>Описание
Элемент управления **Вложения** позволяет открывать файлы, добавлять их в список SharePoint или сущность CDS for Apps и удалять их оттуда.

## <a name="key-properties"></a>Основные свойства
**[Items](properties-core.md)** — источник, описывающий файлы, которые могут быть скачаны.

**MaxAttachments** — максимальное число файлов, которое будет принимать элемент управления.

**MaxAttachmentSize** — максимально допустимый размер файла (в МБ) каждого нового вложения.  Сейчас установлено ограничение в 10 МБ.

**OnAttach** — поведение приложения, когда пользователь добавляет файл.

**OnRemove** — поведение приложения, когда пользователь удаляет вложенный файл.

**[OnSelect](properties-core.md)** — поведение приложения, когда пользователь выбирает вложение.

## <a name="additional-properties"></a>Дополнительные свойства
**[AccessibleLabel](properties-accessibility.md)** — метка для средств чтения с экрана. Необходимо описать назначение вложений.

**AddAttachmentText** — текст метки для ссылки, с помощью которой добавляется новое вложение.

**[BorderColor](properties-color-border.md)**  — цвет границы элемента управления.

**[BorderStyle](properties-color-border.md)**  — стиль границы элемента управления: **Сплошная**, **Штриховая**, **Пунктирная** или **Отсутствует**.

**[BorderThickness](properties-color-border.md)**  — толщина границы элемента управления.

**[DisplayMode](properties-core.md)** — в зависимости от значения этого режима элемент управления разрешает пользователю добавлять и редактировать файлы (**Изменение**) или только отображать данные (**Просмотр**), либо элемент будет вообще отключен (**Отключено**).

**[FocusedBorderColor](properties-color-border.md)** — цвет границы элемента управления при наведении фокуса.

**[FocusedBorderThickness](properties-color-border.md)** — толщина границы элемента управления при наведении фокуса.

**[Height](properties-size-location.md)**  — расстояние между верхним и нижним краем элемента управления.

**MaxAttachmentsText** — текст, который заменяет ссылку "Присоединить файл", когда элемент управления содержит максимальное допустимое число файлов.

**NoAttachmentsText** — информационный текст, который видит пользователь, когда нет файлов для отображения.

**[TabIndex](properties-accessibility.md)** — порядок навигации с помощью клавиатуры относительно других элементов управления.

**[Visible](properties-core.md)** — отображение или скрытие элемента управления.

**[Width](properties-size-location.md)**  — расстояние между левым и правым краем элемента управления.

**[X](properties-size-location.md)** — расстояние между левым краем элемента управления и левым краем его родительского контейнера (или экрана, если родительского контейнера нет).

**[Y](properties-size-location.md)** — расстояние между верхним краем элемента управления и верхним краем его родительского контейнера (или экрана, если родительского контейнера нет).


## <a name="example"></a>Пример
1. С помощью списка SharePoint создайте на основе данных приложение в качестве источника данных. Или добавьте форму в приложение и укажите в качестве источника данных список SharePoint.

2. Выберите элемент управления **Форма** в представлении в виде дерева слева.

3. Выберите элемент **Данные** на вкладке "Свойства" на панели параметров справа.

4. В разделе **Поля**, включите поле **Вложения**.

    Поле "Вложения", связанное со списком SharePoint, отобразится в форме.

[Сведения о том, как добавить и настроить элемент управления].(../add-configure-controls.md)


## <a name="accessibility-guidelines"></a>Руководство по настройке специальных возможностей
### <a name="color-contrast"></a>Контрастность
Необходимо настроить достаточный контраст для следующих элементов:
* **ItemColor** и **ItemFill**
* **ItemHoverColor** и **ItemHoverFill**
* **ItemPressedColor** и **ItemPressedFill**
* **AddedItemColor** и **AddedItemFill**
* **RemovedItemColor** и **RemovedItemFill**
* **ItemErrorColor** и **ItemErrorFill**
* **AddAttachmentColor** и **Fill**
* **MaxAttachmentsColor** и **Fill**
* **NoAttachmentsColor** и **Fill**

Это дополнение к [стандартным требованиям по цветовому контрасту](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Поддержка средства чтения с экрана
Должны присутствовать следующие свойства:
* **[AccessibleLabel](properties-accessibility.md)**
* **AddAttachmentsText**
* **MaxAttachmentsText**
* **NoAttachmentsText**

### <a name="keyboard-support"></a>Поддержка клавиатуры
* Значение элемента **[TabIndex](properties-accessibility.md)** должно быть равно нулю или больше нуля, чтобы пользователи могли использовать навигацию с помощью клавиатуры.
* Индикаторы фокуса должны быть хорошо видны. Для этого используются элементы **[FocusedBorderColor](properties-color-border.md)** и **[FocusedBorderThickness](properties-color-border.md)**.
