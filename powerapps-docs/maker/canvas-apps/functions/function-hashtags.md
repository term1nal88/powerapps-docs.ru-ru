---
title: Функция HashTags | Документация Майкрософт
description: Справочные сведения о функции HashTags в PowerApps, включая описание синтаксиса и примеры
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
ms.openlocfilehash: ebeecf7ae429f9e18c1b41b7c0f0ddd7da5be07c
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "31826223"
---
# <a name="hashtags-function-in-powerapps"></a>Функция HashTags в PowerApps
Извлекает хэш-теги (#string — строки) из строки или текста.

## <a name="description"></a>Описание
Функция **HashTags** проверяет строку на наличие хэш-тегов. Хэш-теги начинаются с символа решетки (#), после которого следует комбинация из:

* прописных и строчных букв;
* цифр;
* символов подчеркивания;
* символов валют (например, $).

Функция **HashTags** возвращает [таблицу](../working-with-tables.md) с одним столбцом, в которой содержатся хэш-теги из строки.  Если в строке нет хэш-тегов, функция возвращает [пустую](function-isblank-isempty.md) таблицу с одним столбцом.

## <a name="syntax"></a>Синтаксис
**HashTags**( *String* )

* *String* — обязательный аргумент.  Строка, проверяемая на наличие хэш-тегов.

## <a name="examples"></a>Примеры
### <a name="step-by-step"></a>Шаг за шагом
1. Добавьте элемент управления **[Текстовое поле](../controls/control-text-input.md)**, назовите его **Tweet** и введите следующее предложение:
   
    **Это #приложение #ПРОСТО_СУПЕР и может #сЧитать123 или #123абв, но не #1–23 и не #$\*(#@")**
2. Добавьте вертикальную пользовательскую коллекцию и задайте для свойства **[Items](../controls/properties-core.md)** следующую функцию:
   
    **HashTags(Tweet.Text)**
3. Добавьте элемент управления **[Метка](../controls/control-text-box.md)** к шаблону коллекции.
   
    В коллекции отобразятся такие хэш-теги:
   
   * **\#приложение**;
   * **\#ПРОСТО_СУПЕР**;
   * **\#сЧитать123**;
   * **\#123абв**;
   * **\#1**.

