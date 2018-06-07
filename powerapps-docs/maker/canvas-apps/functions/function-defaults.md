---
title: Функция Defaults | Документация Майкрософт
description: Справочные сведения о функции Defaults в PowerApps, включая описание синтаксиса и примеры.
services: ''
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/01/2015
ms.author: gregli
ms.openlocfilehash: b62b2b8575d1ff0e5a55a97db6e6650af5a593c1
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "31825816"
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

