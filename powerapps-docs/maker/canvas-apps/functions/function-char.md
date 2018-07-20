---
title: Функция Char | Документация Майкрософт
description: Справочные сведения о функции Char в PowerApps, включая описание синтаксиса и примеры.
dauthor: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 9c701527fb02613332cfa5bc542681f8c119f3b3
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2018
ms.locfileid: "39014565"
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

