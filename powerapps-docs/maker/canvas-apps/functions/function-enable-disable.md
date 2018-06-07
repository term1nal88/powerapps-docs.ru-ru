---
title: Функции Enable и Disable | Документация Майкрософт
description: Справочные сведения о функциях Enable и Disable в PowerApps, включая описание синтаксиса и примеры.
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
ms.openlocfilehash: b35d819730715917f3092ca803b9a38ea9173edc
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "31825126"
---
# <a name="enable-and-disable-functions-in-powerapps"></a>Функции Enable и Disable в PowerApps
Включает или отключает [сигнал](signals.md).

## <a name="overview"></a>Обзор
Некоторые сигналы могут часто изменяться, при этом требуется, чтобы приложение выполняло повторное вычисление.  Частые изменения в течение длительного периода времени могут привести к разрядке батареи устройства. Эти функции можно использовать, чтобы вручную включать или отключать сигнал.

Когда сигнал не используется, он автоматически отключается.

## <a name="description"></a>Описание
Функции **Enable** и **Disable** включают и отключают сигнал соответственно.

В настоящее время эти функции работают только для сигнала **[Location](signals.md)**.

Эти функции не возвращают никаких значений. Их можно использовать только в [формулах поведения](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Синтаксис
**Enable**( *Сигнал* )<br>**Disable**( *Сигнал* )

* *Сигнал* — обязательный аргумент.  Сигнал, который необходимо включить или отключить.

