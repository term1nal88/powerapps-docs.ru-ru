---
title: "Отображение сведений о текущем пользователе | Документация Майкрософт"
description: "Вставка функции User для отображения имени и электронной почты пользователя, выполнившего вход в PowerApps."
services: 
suite: powerapps
documentationcenter: 
author: lonu
manager: anneta
editor: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2016
ms.author: lonu
ms.openlocfilehash: ce4d0db7a82e87d25df950c99da718bf8c84b9bd
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2018
---
# <a name="show-information-about-a-powerapps-user"></a>Отображение сведений о пользователе PowerApps
Функция User может показать полное имя, электронный адрес и рисунок, который связаны с пользователем, выполнившим вход. Эти сведения можно использовать для автоматического заполнения формы.

Например, можно использовать эту функцию для следующего.

* Создание регистрационной формы для пользователей, предназначенной для посещения учебных занятий, добровольного участия в мероприятиях, регистрации в киоске и многого другого.
* Отображение полного имени в приложении для отдела кадров.
* Автоматически ввод электронного адреса при обращении в службу поддержки.

По сути, эту возможность можно применять везде, где пользователям удобно использовать формы или метки, которые заполняются автоматически.

[!INCLUDE [app-customization-requirements](includes/app-customization-requirements.md)]

## <a name="show-user-details"></a>Отображение сведений о пользователе
1. На вкладке **Вставка** щелкните или коснитесь **Мультимедиа**, а затем — **Изображение**.
   
   ![][2]
2. Задайте для свойства **[Image](controls/properties-visual.md)** следующую формулу.
   <br>**User().Image**
   
    ![][3]
3. На вкладке **Вставка** щелкните или коснитесь **Текст**, а затем — **Метка**.  
   
    ![][4]
4. Для свойства **[Text](controls/properties-core.md)** задайте следующую формулу.
   <br>**User().FullName**
   
   ![][6]
   
   При этом в метке автоматически появится ваше полное имя. Переместите метку под элемент управления "Изображение", как показано ниже.
   
   ![][5]
5. Добавьте другую метку и установите в ее свойстве **[Text](controls/properties-core.md)** формулу:
   <br>**User().Email**  
   
    ![][8]
   
    При этом в метке автоматически появится ваш электронный адрес. Переместите метку под первую метку, как показано ниже.  
   
    ![][7]

[2]: ./media/show-current-user/add-image.png
[3]: ./media/show-current-user/imageproperty.png
[4]: ./media/show-current-user/insertlabel.png
[5]: ./media/show-current-user/label.png
[6]: ./media/show-current-user/textproperty.png
[7]: ./media/show-current-user/secondlabel.png
[8]: ./media/show-current-user/email.png
[9]: ./media/show-current-user/preview.png
