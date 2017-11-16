---
title: "Функция User | Документация Майкрософт"
description: "Справочные сведения, включая описание синтаксиса, о функции User в PowerApps"
services: 
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/07/2016
ms.author: gregli
ms.openlocfilehash: 6fee690b849a305d1dd97361cd76b74889f258d9
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2017
---
# <a name="user-function-in-powerapps"></a>Функция User в PowerApps
Возвращает сведения о текущем пользователе.

## <a name="description"></a>Описание
Функция **User** возвращает [запись](../working-with-tables.md#records) c информацией о текущем пользователе:

| Свойство | Описание |
| --- | --- |
| **User().Email** |Адрес электронной почты текущего пользователя. |
| **User().FullName** |Полное имя текущего пользователя, то есть имя и фамилия. |
| **User().Image** |Изображение текущего пользователя. Здесь будет URL-адрес изображения в формате "blob:*идентификатор*". Чтобы отобразить это изображение в приложении, присвойте полученное значение параметру **[Image](../controls/properties-visual.md)** элемента управления **[Image](../controls/control-image.md)**. |

**Примечание**. Информация возвращается для текущего пользователя PowerApps.  Она будет совпадать с информацией раздела со сведениями об учетной записи, которая отображается в проигрывателях и студии PowerApps и доступна вне создаваемых приложений.  Она может не совпадать с информацией о текущем пользователе Office 365 или других служб.

## <a name="syntax"></a>Синтаксис
**User**()

## <a name="examples"></a>Примеры
Текущий пользователь PowerApps, о котором есть следующая информация:

* полное имя — **John Doe**;
* адрес электронной почты — **"john.doe@contoso.com"**;
* изображение — ![](media/function-user/john-doe-picture.png). 

| Формула | Описание | Возвращаемый результат |
| --- | --- | --- |
| **User()** |Запись со всеми данными для текущего пользователя PowerApps. |{FullName:&nbsp;"John Doe", Email:&nbsp;"john.doe@contoso.com", Image:&nbsp;"blob:1234...5678"} |
| **User().Email** |Адрес электронной почты текущего пользователя PowerApps. |"john.doe@contoso.com" |
| **User().FullName** |Полное имя текущего пользователя PowerApps. |"John Doe" |
| **User().Image** |URL-адрес изображения текущего пользователя PowerApps.  Чтобы отобразить это изображение в приложении, присвойте полученное значение параметру **Image** элемента управления **Image**. |"blob:1234...5678"<br><br>С использованием **ImageControl.Image**:<br>![](media/function-user/john-doe-picture.png) |

