---
title: Справка по элементу управления "Экран" | Документация Майкрософт
description: Сведения об элементе управления "Экран" с описанием его свойств и примерами
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
ms.openlocfilehash: 15264a783922891a84e805cea211f2945bca3f3e
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42863904"
---
# <a name="screen-control-in-powerapps"></a>Элемент управления "Экран" в PowerApps
Элемент пользовательского интерфейса приложения, содержащий один или несколько других элементов управления.

## <a name="description"></a>Описание
В большинстве приложений есть несколько элементов управления **Экран**, которые содержат элементы управления **[Метка](control-text-box.md)**, **[Кнопка](control-button.md)** и другие, отображающие данные и поддерживающие навигацию.

## <a name="key-properties"></a>Основные свойства
**[BackgroundImage](properties-visual.md)**  — имя файла изображения, которое используется в качестве фона экрана.

**[Fill](properties-color-border.md)**  — цвет фона элемента управления.

## <a name="additional-properties"></a>Дополнительные свойства
**[ImagePosition](properties-visual.md)**  — расположение изображения на экране или в элементе управления, если его размеры отличаются от размеров изображения (**Fill**, **Fit**, **Stretch**, **Tile** или **Center**).

**OnHidden** — поведение приложения при выходе пользователя с экрана.

**OnVisible** — поведение приложения при переходе пользователя на экран.

**OnStart** — поведение приложения, когда пользователь открывает его.

* Формула, заданная для этого свойства, выполняется перед появлением первого экрана приложения. Вызовите функцию [**Navigate**](../functions/function-navigate.md), чтобы изменить экран, который будет отображаться первым при запуске приложения.
* Невозможно задать [переменные контекста](../working-with-variables.md) с помощью функции [**UpdateContext**](../functions/function-updatecontext.md), так как экран еще не появился. Тем не менее можно передавать переменные контекста в функцию **Navigate**, а затем создать и заполнить [коллекцию](../working-with-variables.md) с помощью функции [**Collect**](../functions/function-clear-collect-clearcollect.md).
* После обновления приложения формула, заданная для этого свойства, будет выполняться при загрузке приложения в PowerApps Studio. Чтобы увидеть результат изменения этого свойства, необходимо сохранить, закрыть и повторно загрузить приложение.
* Свойство **OnStart** относится к приложению, а не экрану. Для удобства редактирования его можно просмотреть и изменить на первом экране приложения. Если удалить первый экран или изменить порядок экранов, это свойство может оказаться трудно найти. В этом случае сохраните, закройте и повторно загрузите приложение. После этого данное свойство снова станет свойством первого экрана.

## <a name="related-functions"></a>Связанные функции
[**Distinct**(*источник*, *столбец*)](../functions/function-distinct.md)

## <a name="example"></a>Пример
1. Добавьте элемент управления **[Переключатель](control-radio.md)**, назовите его **ScreenFills** и укажите для свойства **[Items](properties-core.md)** следующее значение:<br>
   **["Red", "Green"]**
   
    Не знаете, как [добавить, назвать и настроить элемент управления](../add-configure-controls.md)?
2. Присвойте элементу управления **Экран** по умолчанию имя **Source**, добавьте еще один элемент управления **Экран** и назовите его **Target**.
3. В элементе **Source** добавьте элемент управления **[Фигура](control-shapes-icons.md)** (например, стрелку) и укажите для свойства **[OnSelect](properties-core.md)** следующую формулу:<br>
   **Navigate(Цель; ScreenTransition.Fade)**
   
    Нужны дополнительные сведения о функции **[Navigate](../functions/function-navigate.md)** или [других функциях](../formula-reference.md)?
4. В элементе **Target** добавьте элемент управления **[Фигура](control-shapes-icons.md)** (например, стрелку) и укажите для свойства **[OnSelect](properties-core.md)** следующую формулу:<br>
   **Navigate(Source, ScreenTransition.Fade)**
5. Укажите для свойства **[Fill](properties-color-border.md)** элемента **Target** следующую формулу:<br>
   **If("Red" in ScreenFills.Selected.Value, RGBA(255, 0, 0, 1), RGBA(54, 176, 75, 1))**
6. В элементе **Source** нажмите клавишу F5, выберите вариант в элементе управления **[Переключатель](control-radio.md)** и нажмите элемент управления **[Фигура](control-shapes-icons.md)**.
   
    Элемент **Target** отображается в выбранном цвете.
7. В элементе **Target** нажмите элемент управления **[Фигура](control-shapes-icons.md)**, чтобы вернуться в элемент **Source**.
8. (Необязательно) Выберите другой вариант в элементе управления **[Переключатель](control-radio.md)**, нажмите элемент управления **[Фигура](control-shapes-icons.md)** и убедитесь, что элемент **Target** отображается в другом цвете.
9. Нажмите клавишу ESC, чтобы вернуться в рабочую область по умолчанию.


## <a name="accessibility-guidelines"></a>Руководство по настройке специальных возможностей
### <a name="color-contrast"></a>Контрастность
При использовании элемента **Screen** в качестве фона для текста, необходимо настроить достаточный контраст для следующих элементов:
* элемент **[Fill](properties-color-border.md)** и текст;
* элемент **[BackgroundImage](properties-visual.md)** и текст (если применимо).

Например, элемент **Screen** содержит элемент **[Label](control-text-box.md)**, и метка имеет прозрачное заполнение, элемент **[Fill](properties-color-border.md)** экрана становится цветом фона для метки.

Целесообразно проверить контраст не только текста, но и основных графических объектов, включая отмеченные звездочкой изображения, в элементе управления **[Rating](control-rating.md)**.

### <a name="screen-reader-support"></a>Поддержка средства чтения с экрана
* У каждого элемента **Screen** должно быть понятное имя. Имя экрана можно просматривать и редактировать, как и имена других элементов управления, — в представлении дерева на панели элементов управления или в заголовке панели свойств.

    > [!NOTE]
  > При загрузке нового элемента **Screen** средства чтения с экрана будут сообщать его имя. 
