---
title: Удаление приложения на основе модели | Документы Майкрософт
description: Сведения о том, как удалить приложение на основе модели из среды PowerApps.
keywords: ''
ms.date: 05/31/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: e82e7f64-37ad-41e5-acd7-16309881c6a2
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 9
topic-status: Drafting
ms.openlocfilehash: 9512c0b1c13f408b92c0c18f08946ea9afa1e62b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39704003"
---
# <a name="delete-a-model-driven-app"></a>Удаление приложения на основе модели

Удаление устаревших приложений из среды.

1. Войдите в [PowerApps](https://web.powerapps.com/).
2. Откройте [обозреватель решений](advanced-navigation.md#solution-explorer). 
3. В окне решения в разделе **Компоненты** выберите **Приложения**.
4. Выберите приложение, которое требуется удалить, а затем выберите **Удалить** на панели команд.

    ![Удаление приложения](media/app-module-solution-window.png "Удаление приложения")

5. В появившемся окне подтверждения выберите **Удалить**.

   Приложение удалено из среды.
  
Если компонент имеет зависимости (например, отношения), то перед удалением приложения необходимо удалить зависимости. Чтобы просмотреть зависимости приложения, выберите приложение и затем нажмите **Показать зависимости** на панели команд.

> [!NOTE]
> При удалении приложения рекомендуется удалять связанную с ним карту сайта. Если не удалить связанную карту сайта, конструктор карты сайта выведет ошибку при первом создании другого приложения с таким же именем. Однако ошибку можно игнорировать, и ошибка не выводится при попытке снова создать приложение.


