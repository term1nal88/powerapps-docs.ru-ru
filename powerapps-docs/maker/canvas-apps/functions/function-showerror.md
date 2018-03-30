---
title: Функция ShowError | Документы Майкрософт
description: Справочные сведения о функции ShowError в PowerApps, включая описание синтаксиса и примеры
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
ms.date: 03/21/2018
ms.author: gregli
ms.openlocfilehash: 7c1d5a8c7b35d316a2720d564977170029e28359
ms.sourcegitcommit: a9d33322228c398d29964429602dc3fe19fa67d2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="showerror-function-in-powerapps"></a>Функция ShowError в PowerApps
Выводит сообщение об ошибке для пользователя.

## <a name="description"></a>Описание
Функция **ShowError** выводит сообщение об ошибке для пользователя.  Сообщения отображаются как при разработке, так и при использовании приложения.

Функция **ShowError** может использоваться только в [формулах поведения](../working-with-formulas-in-depth.md).

Функция **ShowError** всегда возвращает *true*.

Функцию **ShowError** можно использовать совместно с функцией [**IfError**](function-iferror.md) для определения ошибок и выдачи пользовательских сообщений об ошибках.

## <a name="syntax"></a>Синтаксис
**ShowError**( *Message* )

* *Message* — обязательный параметр.  Сообщение, отображаемое для пользователя. 

## <a name="examples"></a>Примеры

### <a name="step-by-step"></a>Шаг за шагом

1. Добавьте элемент управления **Button** на экран.

2. Укажите следующее значение для свойства **OnSelect** элемента управления **Button**:

    **ShowError( "Hello, World" )**

3. Нажмите кнопку.  

    При каждом нажатии на кнопку для пользователя будет отображаться сообщение **Hello, World**.

    ![Вызов функции ShowError из метода Button.OnSelect и отображение сообщения "Hello, World" в виде красного баннера в среде разработки](media/function-showerror/hello-world.png)
