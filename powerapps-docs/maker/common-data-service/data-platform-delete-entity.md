---
title: Краткое руководство по удалению настраиваемой сущности и очистке данных | Документы Майкрософт
description: Краткое руководство по удалению настраиваемой сущности и очистке данных
services: powerapps
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 3/21/2018
ms.author: clwesene
ms.openlocfilehash: 399d3e8bac215df7612ac12d922dfe644dc59f96
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="quickstart-delete-a-custom-entity"></a>Краткое руководство. Удаление настраиваемой сущности
Вы можете удалять только настраиваемые сущности, но не стандартные.

1. На сайте [powerapps.com](https://web.powerapps.com) разверните раздел **Данные** и выберите элемент **Сущности** в области навигации слева.

    ![Сведения о сущности](./media/data-platform-cds-create-entity/entitylist.png "Список сущностей")

2. Выберите в списке сущность, которую нужно удалить, а затем выберите на панели команд команду **Удалить сущность**.
3. В появившемся диалоговом окне нажмите кнопку **Удалить**, чтобы удалить сущность.

>[!NOTE]
>Удаляя сущность, вы удаляете ее определение и все содержащиеся в ней данные. Удаленные сущности и их данные восстановить невозможно.

>[!NOTE]
>Удалив сущность, вы можете нарушить работу приложения или последовательности операций, которые ее используют.

>[!NOTE]
>Если сущность А [использует данные](data-platform-entity-lookup.md) из сущности Б, возможно, сначала потребуется удалить сущность Б, и только потом — сущность A.

