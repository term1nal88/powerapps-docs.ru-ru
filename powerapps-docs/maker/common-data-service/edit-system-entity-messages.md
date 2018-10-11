---
title: Изменение сообщений системных сущностей с помощью PowerApps | Документы Майкрософт
description: Узнайте, как изменять сообщения системных сущностей
ms.custom: ''
ms.date: 05/15/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 3ccbd8de-8d6f-4058-87f7-15463667cfc6
caps.latest.revision: 41
ms.author: matp
manager: kvivek
ms.openlocfilehash: 797d6855bea421abd90752dd9ae0ad73a9d92f38
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39702888"
---
# <a name="edit-system-entity-messages"></a>Изменение сообщений системных сущностей

Отображаемое имя по умолчанию для некоторых системных сущностей используется в тексте пользовательского интерфейса и сообщений об ошибках в Common Data Service for Apps. При изменении отображаемого имени необходимо также обновить любые сообщения, в которых используется отображаемое имя по умолчанию. Например, если изменить отображаемое имя *Учетная запись* на имя *Компания*, в сообщениях об ошибке будет по-прежнему использоваться старое имя.  

На портале PowerApps невозможно изменять системные сообщения, необходимо использовать обозреватель решений.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Если в обозревателе решений под сущностью отображается узел **Сообщения**, можно изменить определенный текст, который включает в себя ссылки на исходное отображаемое имя сущности. 

![Сообщения сущности](../model-driven-apps/media/entity-messages.png)

Изменить этот текст просто. Дважды щелкните сообщение, чтобы увидеть форму с тремя полями.  
  
|Поле|Описание|  
|-----------|-----------------|  
|**Строка отображаемого имени по умолчанию**|Показывает исходный текст.|  
|**Строка настраиваемого отображаемого имени**|Измените этот текст, чтобы изменить отображаемое имя.|  
|**Комментарий**|Необязательно. Добавьте комментарий о том, что изменено и почему.|  
  
В тексте некоторых сообщений могут содержаться заполнители. Эти заполнители представляют собой числа, заключенные в скобки. Пример: `{0}`. Заполнители позволяют вставлять текст в сообщение. При изменении сообщений обязательно сохраняйте в тексте заполнители. 

Нажмите ![Сохранить](media/save-entity-icon-solution-explorer.png), чтобы сохранить изменения. Нажмите **Сохранить и закрыть**, чтобы сохранить и закрыть форму.

> [!NOTE]
> Хотя интерфейс редактирования сообщений системных сущностей содержит ссылки на множество имен сущностей, список не является исчерпывающим. Более комплексный подход см. в разделе [Обновление локализуемого текста на базовом языке](../model-driven-apps/translate-localizable-text.md#updating-localizable-text-in-the-base-language).

## <a name="programmatically-update-entity-display-strings"></a>Программное обновление отображаемых имен сущностей

Для разработчиков, которым необходима возможность работать с именами сущностей в коде, строки отображаемых имен хранятся в сущности [DisplayString](../../developer/common-data-service/reference/entities/displaystring.md). 

Сущность `DisplayString` не содержит строки отображаемых имен по умолчанию. Атрибуты этой сущности, содержащие текст, — это [CustomDisplayString](../../developer/common-data-service/reference/entities/displaystring.md#BKMK_CustomDisplayString) и [PublishedDisplayString](../../developer/common-data-service/reference/entities/displaystring.md#BKMK_PublishedDisplayString). По умолчанию эти атрибуты имеют значение null, если строка отображаемого имени не была изменена и опубликована. Значение `PublishedDisplayString` доступно только для чтения и отражает текущее опубликованное значение `CustomDisplayString`.
 
## <a name="see-also"></a>См. также
[Изменение сущности](edit-entities.md)<br />
[Перевод локализуемого текста для приложения на основе моделей](../model-driven-apps/translate-localizable-text.md)
