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
ms.openlocfilehash: 2e8281f401088f43aa7785ac5dcf7b2f07bb6f96
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "31826226"
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

