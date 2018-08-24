---
title: Функция HashTags | Документация Майкрософт
description: Справочные сведения о функции HashTags в PowerApps, включая описание синтаксиса и примеры
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 66fad5a1afd9086bf07da88a93ac68b756dfb3d6
ms.sourcegitcommit: 521a7b8e6ae72a211045b54d153a8a8c8f59172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40021325"
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
   
    **Это #приложение #ПРОСТО_СУПЕР и может #сЧитать123 или #123абв, но не #1–23 и не #$\*(#\@")**
2. Добавьте вертикальную пользовательскую коллекцию и задайте для свойства **[Items](../controls/properties-core.md)** следующую функцию:
   
    **HashTags(Tweet.Text)**
3. Добавьте элемент управления **[Метка](../controls/control-text-box.md)** к шаблону коллекции.
   
    В коллекции отобразятся такие хэш-теги:
   
   * **\#приложение**;
   * **\#ПРОСТО_СУПЕР**;
   * **\#сЧитать123**;
   * **\#123абв**;
   * **\#1**.

