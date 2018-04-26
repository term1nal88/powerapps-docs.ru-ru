---
title: Функция Find | Документация Майкрософт
description: Справочные сведения о функции Find в PowerApps, включая описание синтаксиса и примеры.
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
ms.openlocfilehash: 8e95f03c934e0989269ff9ec21b432f609cb13ad
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="find-function-in-powerapps"></a>Функция Find в PowerApps
Находит текстовую строку, если она существует, в другой строке.

## <a name="description"></a>Описание
Функция **Find** выполняет поиск строки в другой строке и учитывает регистр. Чтобы не учитывать регистр, сначала примените к аргументам функцию **[Lower](function-lower-upper-proper.md)**.

Функция **Find** возвращает начальную позицию найденной строки.  Позиция 1 — это первый знак строки. Функция **Find** возвращает значение *blank* (пусто), если строка, в которой выполняется поиск, не содержит искомой строки.

## <a name="syntax"></a>Синтаксис
**Find**( *Искомая_строка*, *Строка* [, *Начальная_позиция* ] )

* *Искомая_строка* — обязательный аргумент.  Строка, которую требуется найти.
* *Строка* — обязательный аргумент.  Строка, в которой требуется выполнить поиск.
* *Начальная_позиция* — необязательный аргумент.  Начальная позиция, с которой необходимо начать поиск.  Позиция 1 — это первый знак.

