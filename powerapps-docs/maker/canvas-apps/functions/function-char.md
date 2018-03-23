---
title: Функция Char | Документация Майкрософт
description: Справочные сведения о функции Char в PowerApps, включая описание синтаксиса и примеры.
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 7ce510840845b1a1df2d590c4f3ffdddfc5bfb9c
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
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

