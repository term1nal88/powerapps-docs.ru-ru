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
ms.openlocfilehash: 3f7df27ed5b49d60437ba8e5a070fcb676f828e4
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2018
ms.locfileid: "39020706"
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
