---
title: Функции EncodeUrl и PlainText | Документация Майкрософт
description: Справочные сведения о функциях EncodeUrl и PlainText в PowerApps, включая описание синтаксиса и примеры.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 30d3378f46e587e45314c30be1fce3c36b2bb120
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42833004"
---
# <a name="encodeurl-and-plaintext-functions-in-powerapps"></a>Функции EncodeUrl и PlainText в PowerApps
Кодируют и декодируют строки.

## <a name="description"></a>Описание
Функция **EncodeUrl** кодирует строку URL-адреса, заменяя знаки, отличные от буквенно-цифровых, на % и шестнадцатеричные числа.  

Функция **PlainText** удаляет HTML- и XML-теги, преобразуя теги, подобные этим, в соответствующие символы:

* **&amp;nbsp;**
* **&amp;quot;**

Возвращаемым значением этих функций является кодированная или декодированная строка.   

## <a name="syntax"></a>Синтаксис
**EncodeUrl**( *String* )

* *Строка* — обязательный аргумент.  URL-адрес, который необходимо кодировать.

**PlainText**( *String* )

* *строка* — обязательный аргумент. Строка, из которой будут удалены HTML- и XML-теги.

## <a name="examples"></a>Примеры
Если показать RSS-канал в коллекции текста, а затем задать свойству **[Text](../controls/properties-core.md)** метки в этой коллекции значение **ThisItem.description**, то метка может отобразить необработанный HTML- или XML-код, как в этом примере:

    <p>We have done an unusually&nbsp;&quot;deep&quot; globalization and localization.<p>

Если задать свойству **[Text](../controls/properties-core.md)** метки значение **PlainText(ThisItem.description)**, то отображаемый текст будет иметь такой вид:

    We have done an unusually "deep" globalization and localization.
