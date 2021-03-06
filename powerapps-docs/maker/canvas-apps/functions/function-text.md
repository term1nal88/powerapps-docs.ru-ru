---
title: Функция Text | Документация Майкрософт
description: Справочные сведения, включая описание синтаксиса, о функции Text в PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: dab6004afe7350b2375ade21871efe9144b6325b
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42849300"
---
# <a name="text-function-in-powerapps"></a>Функция Text в PowerApps
Форматирует число или значение даты и времени для отображения в виде текстовой строки.

## <a name="description"></a>Описание
Функция **Text** форматирует число или значение даты и времени на основе аргументов следующих типов.

* Стандартный формат даты и времени, который указывается с помощью перечисления **DateTimeFormat**.  Для даты и времени этот подход является предпочтительным, так как он автоматически учитывает язык и страну пользователя.
* Пользовательский формат, описываемый текстовой строкой с заполнителями, которая задает правила форматирования числа или значения даты и времени. Заполнители определяют, сколько разрядов следует отображать, использовать ли разделители группирования и как отображать название месяца. В PowerApps используется тот же набор заполнителей, что и в Microsoft Excel.

Подробнее см. статью о [работе с датами и временем](../show-text-dates-times.md).

### <a name="predefined-datetime-formats"></a> Предопределенные форматы даты и времени

| Предопределенный формат | Описание |
| --- | --- |
| **DateTimeFormat.LongDate** |Полный год, месяц, день месяца и день недели. Названия месяца и дня недели не сокращаются. |
| **DateTimeFormat.LongDateTime** |Полный год, месяц, день месяца и день недели, а также часы (в 12-часовом формате), минуты, секунды и обозначение AM/PM. Названия месяца и дня недели не сокращаются. |
| **DateTimeFormat.LongDateTime24** |Полный год, месяц, день месяца и день недели, а также часы (в 24-часовом формате), минуты и секунды. Названия месяца и дня недели не сокращаются. |
| **DateTimeFormat.LongTime** |Часы (в 12-часовом формате), минуты, секунды и обозначение AM/PM. Аналогично ShortTime. |
| **DateTimeFormat.LongTime24** |Часы (в 24-часовом формате), минуты и секунды. Аналогично ShortTime24. |
| **DateTimeFormat.ShortDate** |Четыре цифры года, две цифры месяца и день месяца. |
| **DateTimeFormat.ShortDateTime** |Четыре цифры года, две цифры месяца и день месяца, а также часы (в 12-часовом формате), минуты, секунды и обозначение AM/PM. |
| **DateTimeFormat.ShortDateTime24** |Четыре цифры года, две цифры месяца и день месяца, а также часы (в 24-часовом формате), минуты и секунды. |
| **DateTimeFormat.ShortTime** |Часы (в 12-часовом формате), минуты, секунды и обозначение AM/PM.  Аналогично LongTime. |
| **DateTimeFormat.ShortTime24** |Часы (в 24-часовом формате), минуты и секунды.  Аналогично LongTime24. |
| **DateTimeFormat.UTC** |Значение даты и времени преобразуется в формат UTC на основе часового пояса для текущего пользователя и форматируется в соответствии со стандартом ISO 8601. |

### <a name="number-placeholders"></a>Заполнители для чисел

| Заполнитель | Описание |
| --- | --- |
| **0** (*ноль*) |Отображает незначащие нули, если число имеет меньше разрядов, чем количество нулей в строке форматирования. Например, формат **#.00** позволяет отобразить значение **8,9** как **8,90**. |
| **#** |Работает так же, как **0** (ноль). Но в этом случае функция **Text** не возвращает дополнительные нули, если число имеет слева или справа от десятичного разделителя меньше цифр, чем количество символов # в строке форматирования. Например, число **8,9** при использовании формата **#.##** будет отображаться как **8,9**. |
| **.** (*точка*) |Отображает символ десятичного разделителя.  Поведение этого символа зависит от языка пользовательского формата, подробные сведения см. в разделе [Глобальные приложения](#global-apps). |
| **,** (*запятая*) |Отображает символ разделителя разрядов, обычно отделяющий значения тысяч. Функция **Text** разделяет число запятыми, если в строке форматирования есть запятая между символами номера (**#**) или нулями.  Поведение этого символа зависит от языка пользовательского формата, подробные сведения см. в разделе [Глобальные приложения](#global-apps). |

Если число имеет больше разрядов справа от десятичного разделителя, чем количество заполнителей в строке форматирования, число округляется до стольких десятичных разрядов, сколько указано заполнителей. Если число имеет больше разрядов слева от десятичного разделителя, чем количество заполнителей в строке форматирования, отображаются все дополнительные цифры. Если в строке форматирования слева от десятичной запятой указаны только символы номера (#), числа меньше 1 начинаются с десятичного разделителя (например, **.47**).

### <a name="date-and-time-placeholders"></a>Заполнители даты и времени

|                                                                                                 Заполнитель                                                                                                  |                                                                                                     Описание                                                                                                     |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                    **m**                                                                                                     |                                                                               Отображает месяц в виде числа без нуля в начале.                                                                                |
|                                                                                                    **mm**                                                                                                    |                                                                        Отображает месяц в виде числа с нулем в начале, если требуется.                                                                         |
|                                                                                                   **mmm**                                                                                                    |                                                                             Отображает сокращенное название месяца (от **янв** до **дек**).                                                                             |
|                                                                                                   **mmmm**                                                                                                   |                                                                          Отображает полное название месяца (от **января** до **декабря**).                                                                           |
|                                                                                                    **d**                                                                                                     |                                                                                Отображает день месяца в виде числа без нуля в начале.                                                                                 |
|                                                                                                    **dd**                                                                                                    |                                                                         Отображает день месяца в виде числа с нулем в начале, если требуется.                                                                          |
|                                                                                                   **ddd**                                                                                                    |                                                                              Отображает сокращенное название дня недели (от **вс** до **сб**).                                                                              |
|                                                                                                   **dddd**                                                                                                   |                                                                            Отображает полное название дня недели (от **воскресенья** до **субботы**).                                                                            |
|                                                                                                    **yy**                                                                                                    |                                                                                      Отображает год в виде двузначного числа.                                                                                       |
|                                                                                                   **yyyy**                                                                                                   |                                                                                      Отображает год в виде четырехзначного числа.                                                                                      |
|                                                                                                    **h**                                                                                                     |                                                                                Отображает время в виде числа без нуля в начале.                                                                                |
|                                                                                                    **hh**                                                                                                    | Отображает часы в виде числа с нулем в начале, если требуется. Если строка форматирования содержит обозначения **AM** или **PM**, часы отображаются в 12-часовом формате. В противном случае часы отображаются в 24-часовом формате. |
|                                                                                                    **m**                                                                                                     |                                                                         Отображает минуты в виде числа без нуля в начале.  > [!NOTE]                                                                          |
|            > Для отображения минут символы **m** или **mm** должны располагаться сразу после символов **h** или **hh** или непосредственно перед символами **ss**; в противном случае функция **Text** возвращает не минуты, а номер месяца.            |                                                                                                                                                                                                                     |
|                                                                                                    **mm**                                                                                                    |                                                                   Отображает минуты в виде числа с нулем в начале, если требуется. > [!NOTE]                                                                   |
| > Для отображения минут символы **m** или **mm** должны располагаться сразу после символов **h** или **hh** или непосредственно перед символами **ss**. В противном случае функция **Text** возвращает не минуты, а номер месяца. |                                                                                                                                                                                                                     |
|                                                                                                    **s**                                                                                                     |                                                                               Отображает секунды в виде числа без нуля в начале.                                                                               |
|                                                                                                    **ss**                                                                                                    |                                                                        Отображает секунды в виде числа с нулем в начале, если требуется.                                                                        |
|                                                                                                    **f**                                                                                                     |                                                                                         Отображает доли секунды.                                                                                          |
|                                                                                    **AM/PM**, **am/pm**, **A/P** или **a/p**                                                                                    |               Отображает часы в 12-часовом формате. Функция **Text** возвращает обозначения "AM", "am", "A" или "a" для значений времени с полуночи до полудня или обозначения "PM", "pm", "P" или "p" для значений времени с полудня до полуночи.                |

### <a name="literal-placeholders"></a>Литеральные заполнители
В строку форматирования можно включить также перечисленные ниже символы.  Функция **Text** будет отображать их без изменения. Остальные символы зарезервированы для новых заполнителей, поэтому их не следует использовать.

| Символ | Описание |
| --- | --- |
| Любой символ валюты |Знак доллара, знак центов, знак евро, и т. д. |
| **+** |Знак "плюс" |
| **(** |Левая круглая скобка |
| **:** |Двоеточие |
| **^** |Диакритический знак циркумфлекс (курсор) |
| **'** |Апостроф |
| **{** |Левая фигурная скобка |
| **<** |Знак "меньше" |
| **=** |Знак "равно" |
| **-** |Знак "минус" |
| **/** |Косая черта |
| **)** |Правая круглая скобка |
| **&** |Амперсанд |
| **~** |Тильда |
| **}** |Правая фигурная скобка |
| **>** |Знак "больше" |
| &nbsp; |Символ пробела |

## <a name="global-apps"></a>Глобальные приложения
Функция **Text** учитывает региональные форматы.  Во многих языках она используется для правильного оформления дат, времени, валют и чисел.  Чтобы сделать все правильно, ей нужны два блока информации.

* **Язык пользовательского формата.** Создатель кода указывает, как следует интерпретировать пользовательский формат.  Знаки разделителей (**.** и **,**) имеют разные значения в разных языках.  Для этого передается специальный заполнитель, содержащий тег с указанием языка.  Более того, [стандартные форматы даты и времени](#predefined-datetime-formats) не зависят от языка.
* **Язык результата.** Пользователь определяет, какой язык используется для отображения возвращаемых результатов.  Названия месяцев и дней недели должны отображаться на том языке, который установлен в приложении для пользователя.  Для этого функция **Text** принимает третий (необязательный) аргумент. 

В обоих случаях язык определяется [тегом языка](function-language.md#language-tags).  Чтобы увидеть список поддерживаемых языков, введите в строке формул или в расширенном представлении команду **Text (1234, "",)** и изучите список языковых обозначений, которые будут предложены в качестве значений для третьего аргумента.

#### <a name="custom-format-language-placeholder"></a>Заполнитель для языка пользовательского формата
Чтобы указать язык пользовательского формата, используйте следующий синтаксис.

| Заполнитель | Описание |
| --- | --- |
| **[$-*LanguageTag*]** |Здесь *LanguageTag* обозначает тег языка, возвращаемый функцией **Language**.  Можно использовать только обозначение языка, например **[$en]** для английского языка, или в сочетании с обозначением региона, например **[$-en-GB]** для английского языка и Великобритании. |

Заполнитель с указанием языка может находиться в любом месте пользовательской строки форматирования, но должен встречаться только один раз.

Если при составлении формулы вы не используете заполнитель с указанием языка, а строка форматирования будет неоднозначной с точки зрения глобальных параметров, средство разработки автоматически добавит тег, обозначающий текущий язык вашей системы.  

Если этот заполнитель отсутствует при выполнении приложения, по умолчанию подразумевается наличие тега **[$-en-US]**. 

> [!NOTE]
> В будущих версиях синтаксис этого заполнителя может быть изменен, чтобы избежать путаницы с аналогичным заполнителем другого формата, который поддерживается в Excel.

#### <a name="result-language-tag"></a>Тег для языка результата
Функция **Text** возвращает строковые названия месяцев и дней недели в переводе на нужный язык, а также соответствующие обозначения AM/PM, десятичные разделители и разделители разрядов.

По умолчанию функция **Text** использует язык пользователя, запустившего приложение.  Функция **Language** возвращает тег языка для текущего пользователя.  Это значение по умолчанию можно переопределить, указав тег языка при запуске функции **Text** в виде третьего (необязательного) аргумента.

## <a name="syntax"></a>Синтаксис
**Text**( *Number*, *DateTimeFormatEnum* [, *ResultLanguageTag* ] )

* *Number* — обязательный аргумент. Числовое значение или значение даты и времени, которое нужно отформатировать.
* *DateTimeFormat* — обязательный аргумент.  Значение из списка **DateTimeFormat**.
* *ResultLanguageTag* — необязательный аргумент.  Тег языка для форматирования результата.  По умолчанию используется язык текущего пользователя.

**Text**( *Number*, *CustomFormat* [, *ResultLanguageTag* ] )

* *Number* — обязательный аргумент. Числовое значение или значение даты и времени, которое нужно отформатировать.
* *CustomFormat* — обязательный аргумент. Один или несколько заполнителей, заключенные в двойные кавычки.
* *ResultLanguageTag* — необязательный аргумент.  Тег языка для форматирования результата.  По умолчанию используется язык текущего пользователя.

## <a name="examples"></a>Примеры
Пользователь, выполняющий эти формулы, находится в США и использует английский язык.  Функция **Language** возвращает значение "en-US".

### <a name="number"></a>Номер

| Формула | Описание | Возвращаемый результат |
| --- | --- | --- |
| **Text(&nbsp;1234.59,&nbsp;"####.#"&nbsp;)** |Форматирует число с одним знаком после десятичного разделителя. |"1234.6" |
| **Text(&nbsp;8.9,&nbsp;"#.000"&nbsp;)** |Дополняет десятичную часть числа замыкающими нулями, если потребуется. |"8.900" |
| **Text(&nbsp;0.631,&nbsp;"0.#"&nbsp;)** |Дополняет целую часть числа ведущими нулями, если потребуется. |"0.6" |
| **Text(&nbsp;12,&nbsp;"#.0#"&nbsp;)**<br>**Text(&nbsp;1234.568,&nbsp;"#.0#"&nbsp;)** |Дополняет десятичную часть числа нулями до одного десятичного разряда, но использует два десятичных разряда, если они предоставлены. |"12.0"<br>"1234.57" |
| **Text(&nbsp;12000,&nbsp;"$ #,###"&nbsp;)**<br>**Text(&nbsp;1200000,&nbsp;"$&nbsp;#,###"&nbsp;)** |Добавляет разделитель разрядов после каждых трех цифр целой части числа, а также добавляет символ валюты. |"$&nbsp;12,000"<br>"$&nbsp;1,200,000" |

### <a name="datetime"></a>Дата и время
* Результаты по состоянию на **14:37:47** в **понедельник, 23 ноября 2015 г.**
* (тихоокеанское стандартное время (UTC-8))

| Формула | Описание | Возвращаемый результат |
| --- | --- | --- |
| **Text( Now(), DateTimeFormat.LongDate )** |Форматирует как длинную строку даты с соблюдением языка и языковых стандартов текущего пользователя. |"Monday, November 23, 2015" |
| **Text( Now(), DateTimeFormat.LongDateTime )** |Форматирует как длинную строку даты и времени с соблюдением языка и языковых стандартов текущего пользователя и временем в 12-часовом формате. |"Monday, November 23, 2015 2:37:47 PM" |
| **Text( Now(), DateTimeFormat.LongTime24 )** |Форматирует как длинную строку времени в 24-часовом формате. |"14:37:47" |
| **Text( Now(), DateTimeFormat.ShortDate )** |Форматирует как короткую строку даты с соблюдением языка и языковых стандартов текущего пользователя. |"11/23/2015" |
| **Text( Now(), "d-mmm-yy" )** |Форматирует в соответствии с переданными заполнителями: <ul><li>**d** заменяется одной или двумя цифрами, обозначающими номер месяца.<li>**-** передается напрямую в результат, как литеральный символ.<li>**mmm** заменяется трехбуквенным сокращением для месяца.<li>**-** также передается напрямую в результат.<li>**yy** заменяется двузначным номером года.</ul> |"23-Nov-15" |

### <a name="global-apps"></a>Глобальные приложения

| Формула | Описание | Возвращаемый результат |
| --- | --- | --- |
| **Text( 1234567.89, "[$-en-US]$ #,###" )** |Использует **,** в качестве разделителя разрядов, помещая его после каждых трех символов, а также использует **$** как символ валюты. Так как десятичные знаки не должны отображаться, значение округляется до ближайшего большего целого числа. Указывать **[$-En-US]** здесь необязательно, так как это значение по умолчанию. |"$ 1,234,568" |
| **Text( 1234567.89, "[$-es-ES]&euro; #,###" )** |Использует **,** в качестве десятичного разделителя и **&euro;** как символ валюты.  Так как **[$-fr-FR]** только определяет способ интерпретации строки форматирования, в результат будут переданы символы, определяемые тегом языка по умолчанию ("en-US"). Используется **.** (точка) в качестве десятичного разделителя и **$** для обозначения денежной единицы. |"$ 1234567.89" |
| **Text( 1234567.89, "[$-es-ES]&euro; #,###", "es-ES" )** |Использует **,** в качестве десятичного разделителя.  Тег языка результат имеет значение "fr-FR", то есть используется символ **,** (запятая) в качестве десятичного разделителя и **&euro;** как символ валюты. |"&euro; 1234567,89" |
| **Text( Date(2016,1,31), "dddd mmmm d" )** |Возвращает день недели, месяц и день месяца на языке текущего пользователя. Так как все эти заполнители не зависят от языка, указывать тега языка в строке форматирования не требуется. |"Saturday January 31" |
| **Text( Date(2016,1,31), "dddd mmmm d", "es-ES" )** |Возвращает день недели, месяц и день месяца на языке "es-ES". |"domingo enero 31" |

