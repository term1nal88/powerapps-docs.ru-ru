---
title: Удаление настраиваемой сущности | Документация Майкрософт
description: Пошаговые инструкции по удалению настраиваемых сущностей и очистке всех данных в PowerApps.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
ms.openlocfilehash: b17da30916b06b5b76b16cc6bf9758b988549f6f
ms.sourcegitcommit: 0b051bba173353d7ceda3b60921e7e009eb00709
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "39218655"
---
# <a name="delete-a-custom-entity"></a>Удаление настраиваемой сущности
Вы можете удалять только настраиваемые сущности, но не стандартные.

1. На сайте [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) разверните раздел **Данные** и выберите элемент **Сущности** в области навигации слева.

    ![Сведения о сущности](./media/data-platform-cds-create-entity/entitylist.png "Список сущностей")

2. Выберите в списке сущность, которую нужно удалить, а затем выберите на панели команд команду **Удалить сущность**.

3. В появившемся диалоговом окне нажмите кнопку **Удалить**, чтобы удалить сущность.

>[!NOTE]
>Удаляя сущность, вы удаляете ее определение и все содержащиеся в ней данные. Удаленные сущности и их данные восстановить невозможно.

>[!NOTE]
>Удалив сущность, вы можете нарушить работу приложения или последовательности операций, которые ее используют.

>[!NOTE]
>Если сущность А [использует данные](data-platform-entity-lookup.md) из сущности Б, возможно, сначала потребуется удалить сущность Б, и только потом — сущность A.

