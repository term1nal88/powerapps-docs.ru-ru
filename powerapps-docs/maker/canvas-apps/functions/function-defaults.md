---
title: Функция Defaults | Документация Майкрософт
description: Справочные сведения о функции Defaults в PowerApps, включая описание синтаксиса и примеры.
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
ms.date: 11/01/2015
ms.author: gregli
ms.openlocfilehash: eb1c6b802eff4aa5bd02a2ec52626b8788c42b73
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="defaults-function-in-powerapps"></a>Функция Defaults в PowerApps
Возвращает значения по умолчанию для [источника данных](../working-with-data-sources.md).  

## <a name="description"></a>Описание
Используйте функцию **Defaults** для предварительного заполнения формы ввода данных, чтобы облегчить ее заполнение.

Эта функция возвращает [запись](../working-with-tables.md#records), которая содержит значения по умолчанию для источника данных.  Если [столбец](../working-with-tables.md#columns) в источнике данных не содержит значения по умолчанию, то это свойство не будет отображаться.

Источники данных различаются по объему предоставляемых по умолчанию сведений, включая возможность не предоставлять их совсем.  При работе с [коллекцией](../working-with-data-sources.md#collections) или другим источником данных, который не поддерживает значения по умолчанию, функция **Defaults** возвращает [пустую](function-isblank-isempty.md) запись.

Чтобы [создать запись](../working-with-data-sources.md), можно использовать функцию **Defaults** в сочетании с функцией **[Patch](function-patch.md)**.

## <a name="syntax"></a>Синтаксис
**Defaults**( *Источник_данных* )

* *Источник_данных* — обязательный аргумент. Источник данных, для которого необходимо получить значения по умолчанию.

## <a name="examples"></a>Примеры
| Формула | Описание | Возвращаемый результат |
| --- | --- | --- |
| **Defaults(&nbsp;Scores&nbsp;)** |Возвращает значения по умолчанию для источника данных **Scores**. |**{ Score: 0 }** |

