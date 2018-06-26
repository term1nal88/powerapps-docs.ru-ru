---
title: Функции Round, RoundDown и RoundUp | Документация Майкрософт
description: Справочные сведения о функциях Round, RoundDown и RoundUp в PowerApps, включая описание синтаксиса
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
ms.openlocfilehash: 07771027ea728d65bfb35d79fb67bdef1ac80f1a
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "31825793"
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

