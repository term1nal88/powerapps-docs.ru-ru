---
title: Добавление списка, раскрывающегося списка и переключателей | Документация Майкрософт
description: Создание и настройка элементов множественного выбора в PowerApps
services: ''
suite: powerapps
documentationcenter: ''
author: lonu
manager: anneta
editor: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/23/2016
ms.author: lonu
ms.openlocfilehash: 8eacac89f7578a83757299b8e627cf757fb1c6d7
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="add-a-list-box-a-drop-down-list-or-radio-buttons"></a>Добавление списка, раскрывающегося списка и переключателей
В PowerApps есть элементы управления с возможностью выбора одного или нескольких вариантов, включая переключатели, обычный и раскрывающийся список. В этой статье мы добавим эти элементы управления и воспользуемся формулой **Table** для создания списков. При выборе элемента в списке обновляются другие элементы управления.

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]

## <a name="add-a-list-box"></a>Добавление списка
1. На вкладке **Insert** (Вставка) выберите **Controls** (Элементы управления), а затем — элемент **List box** (Список):  

    ![][2]  

2. Переименуйте **список** в **MyListBox** (Мой список):  

    ![][3]

3. Установите для свойства **[Items](controls/properties-core.md)** (Элементы) следующее выражение:  
   ```["circle","triangle","rectangle"]```  <br/>

    Содержимое конструктора будет выглядеть примерно так:

    ![][4]

4. На вкладке **Insert** (Вставка) выберите **Icons** (Значки), выберите круг и переместите его под **список**:

    ![][5]  

5. Добавьте треугольник и прямоугольник, а затем расположите эти фигуры в один ряд под **списком**:

    ![][6]  

6. Установите для свойства **[Visible](controls/properties-core.md)** (Видимость) фигур указанные ниже функции.  

   | Фигура | Функция в свойстве Visible |
   | --- | --- |
   | круг |```If("circle" in MyListBox.SelectedItems.Value, true)``` |
   | треугольник |```If("triangle" in MyListBox.SelectedItems.Value, true)``` |
   | прямоугольник |```If("rectangle" in MyListBox.SelectedItems.Value, true)``` |

7. Проверьте созданные элементы управления в режиме предварительного просмотра: ![][1]. Выберите в **списке** разные фигуры. Вы увидите только фигуры, которые выбираете. Нажмите клавишу ESC или значок **X**, чтобы вернуться на предыдущий экран.

В этих инструкциях мы использовали выражение для создания списка элементов в элементе управления **Список**. В зависимости от выбранного в списке **элемента** отображается та или иная фигура. Тот же метод можно применять и к другим элементам. Например, с помощью **списка** можно выводить на экран изображения товаров, их описания и т. д.

## <a name="add-radio-buttons"></a>Добавление переключателей
1. На вкладке **Home** (Главная) выберите **New Screen** (Создать экран).

2. На вкладке **Insert** (Вставка) выберите **Controls** (Элементы управления), а затем — **Radio** (Переключатель).

    ![][10]  

3. Переименуйте **переключатель** в **Choices** (Варианты выбора) и установите для свойства **[Items](controls/properties-core.md)** (Элементы) следующую формулу:  
   ```["red","green","blue"]```  <br/>

    ![][12]  

    При необходимости измените размер элемента управления таким образом, чтобы отображались все варианты.

4. На вкладке **Insert** (Вставка) выберите **Icons** (Значки), а затем — круг.

5. Установите для свойства **[Fill](controls/properties-color-border.md)** (Заливка) круга следующую функцию:  
   ```If(Choices.Selected.Value = "red", RGBA(192, 0, 0, 1), Choices.Selected.Value = "green", RGBA(0, 176, 80, 1), Choices.Selected.Value = "blue", RGBA(0, 32, 96, 1))```  

    В этой формуле цвет круга меняется в зависимости от того, какой переключатель установлен.

6. Переместите круг под **переключатель**, как в этом примере:

    ![][14]  

7. Проверьте созданные элементы управления в режиме предварительного просмотра: ![][1]. Установите другой переключатель, чтобы сменить цвет круга. Нажмите клавишу ESC или значок **X**, чтобы вернуться на предыдущий экран.

## <a name="add-a-drop-down-list"></a>Добавление раскрывающегося списка
1. Добавьте экран, а на него — элемент управления **Drop down** (Раскрывающийся список).

    ![][15]  

2. Переименуйте его в **DDChoices** и установите для свойства **[Items](controls/properties-core.md)** (Элементы) следующую формулу:<br>
   **["red","green","blue"]**

3. Добавьте круг, переместите его под **раскрывающийся список** и установите для свойства **[Fill](controls/properties-color-border.md)** (Заливка) круга следующую формулу:  
   ```If(DDChoices.Selected.Value = "red", RGBA(192, 0, 0, 1), DDChoices.Selected.Value = "green", RGBA(0, 176, 80, 1), DDChoices.Selected.Value = "blue", RGBA(0, 32, 96, 1))```

4. Проверьте созданные элементы управления в режиме предварительного просмотра: ![][1]. Выберите другой параметр, чтобы сменить цвет круга.

[1]: ./media/add-list-box-drop-down-list-radio-button/preview.png
[2]: ./media/add-list-box-drop-down-list-radio-button/listbox.png
[3]: ./media/add-list-box-drop-down-list-radio-button/renamelistbox.png
[4]: ./media/add-list-box-drop-down-list-radio-button/itemslistbox.png
[5]: ./media/add-list-box-drop-down-list-radio-button/circle.png
[6]: ./media/add-list-box-drop-down-list-radio-button/allshapes.png
[10]: ./media/add-list-box-drop-down-list-radio-button/radiobutton.png
[12]: ./media/add-list-box-drop-down-list-radio-button/itemsradio.png
[14]: ./media/add-list-box-drop-down-list-radio-button/radiocircle.png
[15]: ./media/add-list-box-drop-down-list-radio-button/dropdown.png
