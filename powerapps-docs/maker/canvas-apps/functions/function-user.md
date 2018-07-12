---
title: Функция User | Документация Майкрософт
description: Справочные сведения, включая описание синтаксиса, о функции User в PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/07/2016
ms.author: gregli
ms.openlocfilehash: 9ec6730a03781bdbffc9c80d815e960de2ce6064
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2018
ms.locfileid: "37899072"
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

> [!NOTE]
> Информация возвращается для текущего пользователя PowerApps.  Она будет совпадать с информацией раздела со сведениями об учетной записи, которая отображается в проигрывателях и студии PowerApps и доступна вне создаваемых приложений.  Она может не совпадать с информацией о текущем пользователе Office 365 или других служб.

## <a name="syntax"></a>Синтаксис
**User**()

## <a name="examples"></a>Примеры
Текущий пользователь PowerApps, о котором есть следующая информация:

* полное имя — **John Doe**;
* адрес электронной почты — **"john.doe@contoso.com"**;
* изображение — ![](media/function-user/john-doe-picture.png). 

|       Формула       |                                                                    Описание                                                                    |                                                 Возвращаемый результат                                                  |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
|     **User()**      |                                             Запись со всеми данными для текущего пользователя PowerApps.                                             |    {FullName:&nbsp;"John Doe", Email:&nbsp;"john.doe@contoso.com", Image:&nbsp;"blob:1234...5678"}    |
|  **User().Email**   |                                                 Адрес электронной почты текущего пользователя PowerApps.                                                  |                                         "john.doe@contoso.com"                                          |
| **User().FullName** |                                                   Полное имя текущего пользователя PowerApps.                                                    |                                               "John Doe"                                                |
|  **User().Image**   | URL-адрес изображения текущего пользователя PowerApps.  Чтобы отобразить это изображение в приложении, присвойте полученное значение параметру **Image** элемента управления **Image**. | "blob:1234...5678"<br><br>С использованием **ImageControl.Image**:<br>![](media/function-user/john-doe-picture.png) |

