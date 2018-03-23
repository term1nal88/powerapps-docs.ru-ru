---
title: Функция Find | Документация Майкрософт
description: Справочные сведения о функции Find в PowerApps, включая описание синтаксиса и примеры.
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
ms.openlocfilehash: f43575fbe84173485ef39f3988bf6a049a4b9417
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
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

