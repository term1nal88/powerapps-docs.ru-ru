---
title: Функция Select | Документация Майкрософт
description: Справочные сведения, включая синтаксис, для функции Select в PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/11/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 74584e5855c6c72c619b4baefc2652f9ccc68997
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42850732"
---
# <a name="select-function-in-powerapps"></a>Функция Select в PowerApps
Имитирует выбор действия для элемента управления, активируя вычисление формулы **OnSelect**.

## <a name="description"></a>Описание
Функция **Select** имитирует выбор действия для элемента управления, как если бы этот элемент управления выбрал пользователь. В результате для целевого элемента управления вычисляется формула **OnSelect**.

Используйте функцию **Select**, чтобы распространить действие выбора на родительский элемент управления. Такой тип распространения является поведением по умолчанию, например, в коллекциях. По умолчанию для свойства **OnSelect** любого элемента управления в элементе управления **[Gallery](../controls/control-gallery.md)** задано значение **Select( Parent )**. Так вы можете задать значение свойства **OnSelect** элемента управления Gallery. При этом формула будет вычисляться независимо от того, где именно в этом элементе управления пользователь может щелкнуть или коснуться.

Если вы хотите, чтобы один или несколько элементов в коллекции выполняли разные действия, задайте свойству **OnSelect** для этих элементов управления значения, отличные от значений по умолчанию. Чтобы элементы управления в коллекции выполняли те же действия, что и сама коллекция, оставьте для свойства **OnSelect** значения по умолчанию.

Функция **Select** помещает в очередь целевую формулу **OnSelect** для последующей обработки, что может произойти после завершения вычисления текущей формулы. Функция **Select** не активирует немедленное вычисление целевой формулы **OnSelect**. Также функция **Select** не ожидает завершения вычисления формулы **OnSelect**.

Функция **Select** не может выходить за пределы таких элементов управления Container, как форма или коллекция. Элементы управления внутри элемента управления Container могут обрабатываться только функцией **Select** в формулах, которые находятся в пределах одного элемента управления контейнера. Вы не можете использовать функцию **Select** на разных экранах.

Вы можете использовать функцию **Select** только с элементами управления со свойством **OnSelect**.

Функцию **Select** можно использовать только в [формулах поведения](../working-with-formulas-in-depth.md).

Элемент управления не может выполнить функцию **Select** по отношению к себе прямо или косвенно через другие элементы управления.

## <a name="syntax"></a>Синтаксис
**Select**( *Control* )

* *Control* — обязательный аргумент.  Элемент управления, выбираемый от имени пользователя.

## <a name="examples"></a>Примеры

#### <a name="basic-usage"></a>Базовое использование

1. Добавьте элемент управления **[Button](../controls/control-button.md)** и переименуйте его в **Button1**, если у него другое имя.

1. Задайте для свойства **OnSelect** кнопки **Button1** эту формулу:

    **Notify( "Hello World" )**

1. На том же экране добавьте второй элемент управления **Button** и в качестве значения свойства **OnSelect** задайте следующую формулу:

    **Select( Button1 )**

1. Удерживая нажатой клавишу ALT, выберите вторую кнопку.

    В верхней части приложения появится уведомление, генерируемое свойством **OnSelect** кнопки **Button1**.

    ![Анимация, в которой показаны параметры свойства OnSelect для двух кнопок и уведомление при нажатии второй кнопки](media/function-select/basic-select.gif)

#### <a name="gallery-control"></a>Элемент управления Gallery

1. Добавьте вертикальный элемент управления **[Gallery](../controls/control-gallery.md)**, который содержит другие элементы управления.

    ![Выбор вертикального элемента управления Gallery, который содержит элементы управления](media/function-select/select-gallery.png)

2. Задайте для свойства **OnSelect** коллекции эту формулу:
 
    **Notify( "Gallery Selected" )**

3. Удерживая нажатой клавишу ALT, щелкните или коснитесь фона коллекции или любого элемента управления в коллекции.

    Все действия отобразят уведомление о **выбранной коллекции** в верхней части приложения.

    С помощью свойства **OnSelect** коллекции можно указать действие по умолчанию, выполняемое, когда пользователь щелкает элемент в коллекции или касается его.

5. Назначьте свойству **OnSelect** элемента управления Image следующую формулу:

    **Notify( "Image Selected", Success )**

6. Удерживая нажатой клавишу Alt, щелкайте разные элементы коллекции или касайтесь их.

    При выборе любого элемента управления в коллекции, кроме изображения, как и раньше отображается уведомление о **выбранной коллекции**. При выборе изображения отображается уведомление о **выбранном изображении**.
 
    Используйте отдельные элементы управления в коллекции для выполнения действий, отличных от действий коллекции по умолчанию.

    ![Анимация, которая отображает значение по умолчанию свойства OnSelect для элемента управления коллекции, а также элемент управления, который принимает другое действие](media/function-select/gallery-select.gif)
