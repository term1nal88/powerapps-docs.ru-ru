---
title: "Настройка карточки | Документация Майкрософт"
description: "Выполнение основной и дополнительной настройки в карточке"
services: 
suite: powerapps
documentationcenter: 
author: skjerland
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/30/2016
ms.author: sharik
ms.openlocfilehash: 9fdde89b254e491f2dc333261649df7fd156f2c2
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2018
---
# <a name="customize-a-card-in-microsoft-powerapps"></a>Настройка карточки в Microsoft PowerApps
Выполните основную настройку (без разблокировки карточки), например измените элемент управления. Выполните дополнительную настройку, разблокировав карточку и, например, добавив элемент управления, недоступный по умолчанию для этой карточки.

Общие сведения см. в статье [Общие сведения о карточках данных](working-with-cards.md).

## <a name="prerequisites"></a>Технические условия

* Узнайте, как [добавлять и настраивать элементы управления](add-configure-controls.md).
* В этом разделе описаны только общие принципы. Подробные пошаговые инструкции можно найти в следующих статьях:

  1. [Создание приложения с помощью SharePoint](app-from-sharepoint.md).
  2. [Настройка макета](customize-layout-sharepoint.md).
  3. [Настройка формы](customize-forms-sharepoint.md).

## <a name="customize-a-locked-card"></a>Настройка заблокированной карточки
В этой процедуре элемент управления **[Toggle](controls/control-toggle.md)** (Двухпозиционный переключатель) заменяется элементом управления **[Radio](controls/control-radio.md)** (Переключатель) без разблокирования карточки.

1. На экране **EditScreen1** щелкните или нажмите на карточку **Paid**, чтобы выбрать ее.

    ![](./media/customize-card/select-paid-card.png)

2. В правой области щелкните (коснитесь) селектор карточки **Paid**, а затем выберите **Изменить параметры**.

    ![](./media/customize-card/select-toggle-paid.png)

    Изменения отразятся на экране.

    ![](./media/customize-card/display-radio.png)
   
    Информацию о том, какие типы столбцов SharePoint поддерживают конкретные типы карточек, см. в разделе с описанием [известных проблем](connections/connection-sharepoint-online.md#known-issues).

## <a name="unlock-and-customize-a-card"></a>Разблокировка и настройка карточки
В этой процедуре карточка разблокируется, а затем элемент управления **[Text input](controls/control-text-input.md)** (Текстовое поле ввода) заменяется элементом управления **[Slider](controls/control-slider.md)** (Ползунок).

1. На экране **EditScreen1** щелкните или нажмите на карточку **Quantity**.

2. На панели справа щелкните или нажмите на значок многоточия для этой карточки, а затем выберите **Advanced options** (Дополнительные параметры).

    ![Открытие раздела Advanced options (Дополнительные параметры)](./media/customize-card/advanced-options.png)
3. В верхней части панели справа коснитесь значка разблокировки карточки.

    ![Разблокировка карточки](./media/customize-card/unlock-card.png)
4. В карточке удалите элемент управления **Input text** (Текстовое поле ввода) и добавьте элемент управления **Slider** (Ползунок). Назовите новый элемент управления **QtySlider**.

5. На панели справа установите для свойства **Update** (Обновление) карточки **Quantity** следующую формулу:<br>
   **QtySlider.Value**

   > [!NOTE]
> Если свойство **Update** не отображается, щелкните или нажмите **Другие параметры** в разделе **Данные**.


6. Щелкните или нажмите на ползунок, чтобы выбрать его, и откройте список элементов управления в верхней части правой панели.

7. Щелкните или нажмите **ErrorMessage4** и установите для свойства **Height** (Высота) следующую формулу:<br>
   **QtySlider.Y + QtySlider.Height**
