---
title: Функции Trim и TrimEnds | Документация Майкрософт
description: Справочные сведения, включая синтаксис и пример, для функций Trim и TrimEnds в PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 09/09/2016
ms.author: gregli
ms.openlocfilehash: f94144c0b279cc61c0af15c95e7cccf73bb124cd
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2018
ms.locfileid: "37898428"
---
# <a name="trim-and-trimends-functions-in-powerapps"></a>Функции Trim и TrimEnds в PowerApps
Удаляют лишние пробелы из текстовой строки.

## <a name="description"></a>Описание
Функция **Trim** удаляет все пробелы из текстовой строки, за исключением одиночных пробелов между словами.  

Функция **TrimEnds** удаляет все пробелы из начала и конца текстовой строки, но оставляет пробелы между словами без изменений.

Если указать одну строку текста, обе функции возвращают строку с удаленными лишними пробелами. Если указать [таблицу](../working-with-tables.md) из одного столбца, содержащую строки, возвращается таблица из одного столбца со строками без пробелов. Таблицу с несколькими столбцами можно преобразовать в таблицу с одним столбцом, как описано в статье об [использовании таблиц](../working-with-tables.md).

С точки зрения удаления лишних пробелов между словами **Trim** аналогична функции СЖПРОБЕЛЫ в Microsoft Excel. Функция **TrimEnds** аналогична функциям в языках программирования, которые удаляют пробелы только в начале и конце каждой строки.

## <a name="syntax"></a>Синтаксис
**Trim**( *строка* )<br>**TrimEnds**( *строка* )

* *строка* — обязательный аргумент. Строка текста, из которой необходимо удалить лишние пробелы.

**Trim**( *таблица_из_одного_столбца* )<br>**TrimEnds**( *таблица_из_одного_столбца* )

* *SingleColumnTable* — обязательный аргумент. Таблица из одного столбца строк для удаления лишних пробелов.

## <a name="example"></a>Пример

| Формула | Описание | Возвращаемый результат |
| --- | --- | --- |
| **Trim(&nbsp;"&nbsp;&nbsp;&nbsp;Привет,&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;мир&nbsp;&nbsp;&nbsp;"&nbsp;)** |Удаляет все пробелы из начала и конца строки и лишние пробелы внутри строки. |"Привет, мир" |
| **TrimEnds(&nbsp;"&nbsp;&nbsp;&nbsp;Привет,&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;мир&nbsp;&nbsp;&nbsp;"&nbsp;)** |Удаляет все пробелы из начала и конца строки. |"Привет,&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;мир" |

В следующих примерах используется коллекция из одного столбца с именем **Spaces**, содержащая следующие строки:

![](media/function-trim/input-strings.png)

Для создания этой коллекции установите в свойстве **OnSelect** элемента управления **[Button](../controls/control-button.md)** следующую формулу, откройте режим предварительного просмотра и нажмите кнопку:
<br>**ClearCollect( Spaces, [ "&nbsp;&nbsp;&nbsp;Елена&nbsp;&nbsp;&nbsp;Иванова&nbsp;&nbsp;&nbsp;", "&nbsp;&nbsp;&nbsp;&nbsp;Иван&nbsp;&nbsp;&nbsp;да&nbsp;&nbsp;&nbsp;Марья", "Уже&nbsp;без пробелов", "&nbsp;&nbsp;&nbsp;Венера,&nbsp;&nbsp;&nbsp;Земля,&nbsp;&nbsp;&nbsp;Марс&nbsp;&nbsp;", "Масло&nbsp;и&nbsp;вода&nbsp;&nbsp;&nbsp;" ] )**

| Формула | Описание | Возвращаемый результат |
| --- | --- | --- |
| **Trim(&nbsp;Spaces&nbsp;)** |Удаляет все пробелы в начале и конце каждой строки и лишние пробелы внутри строк для каждой строки в коллекции **Spaces**. |<style> img { max-width: none } </style> ![](media/function-trim/output-trim.png) |
| **TrimEnds(&nbsp;Spaces&nbsp;)** |Удаляет все пробелы в начале и конце каждой строки в коллекции **Spaces**. |<style> img { max-width: none } </style> ![](media/function-trim/output-trimends.png) |

> [!NOTE]
> Лишние пробелы не отображаются, если отобразить коллекцию, выбрав пункт **Коллекции** в меню **Файл**. Для проверки длины строки используйте функцию **[Len](function-len.md)**.

