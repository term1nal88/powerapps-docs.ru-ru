---
title: Функция Reset | Документация Майкрософт
description: Справочные сведения о функции Reset в PowerApps, включая описание синтаксиса и пример
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/06/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9c032c237018fbd564dd1143f20951dfb42d9795
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42832886"
---
# <a name="reset-function-in-powerapps"></a>Функция Reset в PowerApps
Сбрасывает элемент управления до значения по умолчанию и отменяет все изменения, внесенные пользователем.  

## <a name="description"></a>Описание
Функция **Reset** сбрасывает элемент управления до значения свойства **Default** и  отменяет все изменения, внесенные пользователем.

Элементы управления, которые включены в элементы управления [**Коллекция**](../controls/control-gallery.md) или [**Форма изменения**](../controls/control-form-detail.md), невозможно сбросить извне.  Вы можете их сбросить в формулах элементов управления в пределах той же коллекции или формы.  Кроме того, с помощью функции [**ResetForm**](function-form.md) можно сбросить все элементы управления в форме. 

Функция **Reset** используется как предпочтительная альтернатива переключению свойства **Reset** для элементов управления вводом.  Свойство **Reset** может быть более удобным, если необходимо одновременно сбросить несколько элементов управления из нескольких формул.  Переключить свойство **Reset** можно с помощью элемента управления [**Button**](../controls/control-button.md) с формулой **Reset = Button.Pressed**. Либо с помощью переменной с формулой **Reset = MyVar** и переключением **MyVar** с формулой **Button.OnSelect = Set( MyVar, true ); Set( MyVar, false )**.    

Элементы управления ввода также сбрасываются при изменении их свойства **Default**.

Функция **Reset** не возвращает значение, и ее можно использовать только в [формулах поведения](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Синтаксис
**Reset**( *Control* )

* *Control* — обязательный аргумент. Сбрасываемый элемент управления.

## <a name="example"></a>Пример
1. Вставьте элемент управления **Текстовое поле** на экран.  По умолчанию ему присваивается имя **TextInput1**, а его свойству **Default** — значение **"Text input"**.
2. Введите новое значение в текстовое поле.  
3. Вставьте элемент управления **Button** на экран.
4. Задайте для свойства кнопки **OnSelect** формулу **Reset( TextInput1 )**.
5. Нажмите кнопку.  Это можно сделать даже на этапе разработки, щелкнув края элемента управления.
6. Содержимое текстового поля будет сброшено до значения свойства **Default**.

