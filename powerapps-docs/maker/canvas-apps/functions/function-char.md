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
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: aec27b788fff8434cfdc4e0e130487f718a42aa6
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42826372"
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

