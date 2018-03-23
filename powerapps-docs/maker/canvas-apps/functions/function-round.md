---
title: Функции Round, RoundDown и RoundUp | Документация Майкрософт
description: Справочные сведения о функциях Round, RoundDown и RoundUp в PowerApps, включая описание синтаксиса
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
ms.openlocfilehash: cfb0e8351b1e51a07962e08b2894d02203b274c7
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="round-rounddown-and-roundup-functions-in-powerapps"></a>Функции Round, RoundDown и RoundUp в PowerApps
Округление чисел.

## <a name="description"></a>Описание
Функции **Round**, **RoundDown** и **RoundUp** округляют число до указанного количества знаков после запятой (десятичных разрядов).

* Функция **Round** округляет число в большую сторону, если следующая цифра после запятой больше или равна 5. В противном случае число округляется в меньшую сторону.
* Функция **RoundDown** всегда округляет число в меньшую сторону — до предыдущего (меньшего) числа.
* Функция **RoundUp** всегда округляет число в большую сторону — до следующего (большего) числа.

При передаче одного числа возвращаемое значение является округленной версией такого числа.  При передаче [таблицы](../working-with-tables.md), содержащей один столбец с числами, возвращаемое значение представляет таблицу из одного столбца с округленными числами. Таблицу с несколькими столбцами можно преобразовать в таблицу с одним столбцом, как описано в статье об [использовании таблиц](../working-with-tables.md).

## <a name="syntax"></a>Синтаксис
**Round**( *Number*, *DecimalPlaces* )<br>**RoundDown**( *Number*, *DecimalPlaces* )<br>**RoundUp**( *Number*, *DecimalPlaces* )

* *Number* — обязательный аргумент. Число, которое нужно округлить.
* *DecimalPlaces* — обязательный аргумент.  Количество знаков после запятой, до которого нужно округлить число.  Используйте 0, если необходимо округлить до целого числа.  

