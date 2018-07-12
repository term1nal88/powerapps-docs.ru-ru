---
title: Функция Split | Документация Майкрософт
description: Справочные сведения о функции Split в PowerApps, включая описание синтаксиса и примеры
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 08/28/2017
ms.author: gregli
ms.openlocfilehash: 7989a795afc0085bfa0e78d4b9d0bebeb26619c6
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2018
ms.locfileid: "37899279"
---
# <a name="split-function-in-powerapps"></a>Функция Split в PowerApps
Разбивает строку текста на таблицу с подстроками.

## <a name="description"></a>Описание
Функция **Split** разбивает строку текста на таблицу с подстроками.  Используйте функцию **Split**, чтобы разбивать списки с разделителями-запятыми, даты с косой чертой, а также другие элементы с четко определенными разделителями.  

Строка разделителя используется для разбивки текстовой строки.  Разделитель может содержать ноль, один или несколько символов, которые в текстовой строке обрабатываются как одно целое.  Если используется *пустая* строка или строка нулевой длины, будет разделен каждый символ.  Соответствующие строки разделители не возвращаются в результатах.  Если соответствующий разделитель не найден, вся строка текста возвращается как один результат.

Используйте функцию **[Concat](function-concatenate.md)**, чтобы перекомпоновать строку (без разделителей).  

## <a name="syntax"></a>Синтаксис
**Split**( *Text*, *Separator* )

* *Text* — обязательный аргумент.  Разбиваемый текст.
* *Separator* — обязательный аргумент.  Разделитель, используемый для разбивки строки.  Может включать ноль, один или несколько символов.

## <a name="examples"></a>Примеры

| Формула | Описание | Возвращаемый результат |
| --- | --- | --- |
| **Split( "Apples,&nbsp;Oranges,&nbsp;Bananas", "," )** |Разбивает определения фруктов, используя в качестве разделителя запятую.  Пробел за запятой в состав разделителя не входит, поэтому в результате возвращаются подстроки "&nbsp;Oranges" и "&nbsp;Bananas". |<style> img { max-width: none; } </style> ![](media/function-split/fruit1.png) |
| **TrimEnds( Split( "Apples,&nbsp;Oranges,&nbsp;Bananas", "," ) )** |Пример, аналогичный предыдущему. Но здесь пробел удаляется с помощью [функции **TrimEnds**](function-trim.md), которая обрабатывает столбец таблицы, созданных функцией **Split**. Мы также можно использовать разделитель **",&nbsp;"**, который включает пробел после запятой, но такая конфигурация не будет работать правильно, если пробел будет отсутствовать или будет двойным. |<style> img { max-width: none; } </style> ![](media/function-split/fruit2.png) |
| **Split( "08/28/17", "/" )** |Разбивает элементы даты, используя в качестве разделителя косую черту. |<style> img { max-width: none; } </style> ![](media/function-split/date.png) |
| **Split( "Hello,&nbsp;World", "," )** |Разбивает слова, используя в качестве разделителя запятую.  Вторая подстрока начинается с пробела, так как этот символ следует после запятой. |<style> img { max-width: none; } </style> ![](media/function-split/comma.png) |
| **Split( "Hello,&nbsp;World", "o" )** |Разбивает строку, используя в качестве разделителя символ o. |<style> img { max-width: none; } </style> ![](media/function-split/o.png) |
| **Split( "Hello,&nbsp;World", "l" )** |Разбивает строку, используя в качестве разделителя символ l. Так как между двумя символами **l** в слове **Hello** ничего нет, возвращается *пустое* значение. |<style> img { max-width: none; } </style> ![](media/function-split/l.png) |
| **Split( "Hello,&nbsp;World", "ll" )** |Разбивает строку, используя в качестве разделителя символы ll. |<style> img { max-width: none; } </style> ![](media/function-split/ll.png) |
| **Split( "Hello,&nbsp;World", "%" )** |Разбивает строку, используя в качестве разделителя символ %. Так как этого разделителя в строке нет, возвращается целая строка. |<style> img { max-width: none; } </style> ![](media/function-split/percent.png) |
| **Split( "Hello,&nbsp;World", "" )** |Разбивает строку, используя в качестве разделителя пустую строку (0 знаков). Строка будет разбита посимвольно. |<style> img { max-width: none; } </style> ![](media/function-split/none.png) |

