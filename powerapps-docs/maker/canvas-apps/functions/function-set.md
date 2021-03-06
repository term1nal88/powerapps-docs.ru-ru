---
title: Функция Set | Документация Майкрософт
description: Справочные сведения о функции Set в PowerApps, включая описание синтаксиса и примеры
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/29/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 96b8b8276b385a49bd29be150b9a41ba08ba67ba
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42862825"
---
# <a name="set-function-in-powerapps"></a>Функция Set в PowerApps
Задает значение глобальной переменной.

## <a name="overview"></a>Обзор
Функция **Set** задает значение глобальной переменной, которая временно содержит блок информации, например число нажатий кнопки или результаты выполнения операций с данными.  

Глобальные переменные доступны во всем приложении и на всех экранах.  Это самые простые переменные, которые подойдут для большинства ситуаций.  Существуют также переменные контекста, которые применяются к одному экрану, и коллекции, которые позволяют изменять таблицы на уровне строк.  Дополнительные сведения о других вариантах см. в описании [принципов работы с переменными](../working-with-variables.md).

Служба PowerApps основывается на формулах, которые автоматически вычисляются при взаимодействии пользователя с приложением.  Глобальные переменные не предоставляют эту возможность. Кроме того, они могут усложнить как процесс создания, так и структуру самого приложения.  Прежде чем приступить к работе с переменной, см. описание [принципов работы с переменными](../working-with-variables.md).

## <a name="description"></a>Описание
Глобальные переменные создаются неявно с помощью функции **Set**.  Для этого не требуется явное объявление.  Если для глобальных переменных удалить все функции **Set**, эти переменные исчезнут.  Чтобы очистить переменную, задайте в качестве ее значения результат функции [**Blank**](function-isblank-isempty.md).

Чтобы просмотреть значения, определения и сведения об использовании переменных, перейдите в среде разработки к меню "Файл", а затем откройте представление "Переменные".

Как показано далее в примерах, глобальные переменные могут содержать несколько типов данных, в том числе:

* одиночное значение;
* запись;
* таблица;
* ссылку на объект;
* любой результат формулы.

Значение глобальной переменной хранится, пока приложение не будет закрыто.  После этого значение глобальной переменной будет потеряно. При следующей загрузке приложения значение нужно будет создать снова.

Имена глобальных переменных не должны совпадать с именами существующей коллекции или элемента управления.  Но они могут совпадать с именами переменных контекста.  Чтобы устранить неоднозначность между этими переменными, используйте [оператор устранения неоднозначности](operators.md#disambiguation-operator).

Функция **Set** не возвращает значение, и ее можно использовать только в [формуле поведения](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Синтаксис
**Set**( *VariableName*, *Value* )

* *VariableName* — обязательный аргумент.  Имя создаваемой или обновляемой глобальной переменной.
* *Value* — обязательный аргумент.  Значение, присваиваемое переменной контекста.

## <a name="examples"></a>Примеры

| Формула | Описание | Возвращаемый результат |
| --- | --- | --- |
| **Set(&nbsp;Counter,&nbsp;1&nbsp;)** |Создает или изменяет глобальную переменную **Counter**, задав для нее значение **1**. |Переменная контекста **Counter** имеет значение **1**. Вы можете добавить ссылку на эту переменную, используя имя **Counter** в формуле на любом экране. |
| **Set(&nbsp;Counter,&nbsp;2&nbsp;)** |Изменяет значение глобальной переменной **Counter** из предыдущего примера на **2**. |Переменная контекста **Counter** имеет значение **2**. |
| **Set(&nbsp;Counter,&nbsp;Counter + 1&nbsp;)** |Увеличивает значение глобальной переменной **Counter** из предыдущего примера до **3**. |Глобальная переменная **Counter** имеет значение **3**. |
| **Set(&nbsp;Name,&nbsp;"Lily" )** |Создает или изменяет глобальную переменную **Name**, задав для нее значение **Lily**. |Глобальная переменная **Name** имеет значение **Lily**. |
| **Set(&nbsp;Person,&nbsp;{&nbsp;Name:&nbsp;"Milton", Address:&nbsp;"1&nbsp;Main&nbsp;St"&nbsp;} )** |Создает или изменяет глобальную переменную **Person**, задавая для нее запись в качестве значения. Запись содержит два столбца: **Name** и **Address**. Столбец **Name** имеет значение **Milton**, а столбец **Address** — **1 Main St**. |Глобальной переменной **Person** присваивается значение записи **{&nbsp;Name:&nbsp;"Milton", Address:&nbsp;"1&nbsp;Main&nbsp;St"&nbsp;}**.<br><br>Добавьте ссылку на эту запись в целом по имени **Person** или на ее отдельный столбец с помощью параметра **Person.Name** или **Person.Address**. |
| **Set(&nbsp;Person, Patch(&nbsp;Person,&nbsp;{Address:&nbsp;"2&nbsp;Main&nbsp;St"&nbsp;}&nbsp;)&nbsp;)** |В сочетании с функцией **[Patch](function-patch.md)** обновляет глобальную переменную **Person**, задав для столбца **Address** значение **2 Main St**. |Глобальной переменной **Person** присваивается значение записи **{&nbsp;Name:&nbsp;"Milton", Address:&nbsp;"2&nbsp;Main&nbsp;St"&nbsp;}**. |

