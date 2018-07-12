---
title: Функция Char | Документация Майкрософт
description: Справочные сведения о функции Char в PowerApps, включая описание синтаксиса и примеры.
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: b5d63b26498b94943f5340d9f57f3255390c7c94
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2018
ms.locfileid: "37895990"
---
# <a name="char-function-in-powerapps"></a>Функция Char в PowerApps
Эта функция преобразовывает код знака в строку.

## <a name="description"></a>Описание
Функция **Char** возвращает строку, содержащую соответствующий знак ASCII для вашей платформы.

## <a name="syntax"></a>Синтаксис
**Char**( *Код_знака* )

* *Код_знака* — обязательный аргумент. Код знака ASCII для преобразования.

## <a name="examples"></a>Примеры

| Формула | Описание | Возвращаемый результат |
| --- | --- | --- |
| **Char( 65 )** |Возвращает знак, соответствующий коду ASCII 65. |A |
| **Char( 105 )** |Возвращает знак, соответствующий коду ASCII 105. |i |
| **Char( 35 )** |Возвращает знак, соответствующий коду ASCII 35. |# |

