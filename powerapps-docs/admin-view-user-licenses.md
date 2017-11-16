---
title: "Просмотр лицензий пользователя | Документация Майкрософт"
description: "Администраторы могут скачать список лицензий пользователей для PowerApps и Microsoft Flow"
services: 
suite: powerapps
documentationcenter: na
author: manasmamsft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/02/2017
ms.author: manasma
ms.openlocfilehash: ba60c227b287532f6abe2e2b2e88f6cbe7dd0cd3
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2017
---
# <a name="identify-powerapps-users-in-your-organization"></a>Определение пользователей PowerApps в организации
Глобальный администратор Office 365 или администратор клиента Azure Active Directory может скачать список пользователей в организации, которым назначены лицензии на использование PowerApps, Microsoft Flow (или обе службы) и которые помимо лицензий также имеют доступ к этим продуктам. Список содержит имя каждого пользователя, адрес электронной почты, тип лицензии и другие сведения. Например, пользователю могут быть назначены такие лицензии и права доступа:

* пробная лицензия PowerApps или Microsoft Flow;
* доступ к PowerApps и Microsoft Flow через лицензию Office 365;
* доступ к PowerApps и Microsoft Flow через лицензию Dynamics 365;
* доступ к планам PowerApps и Microsoft Flow.

## <a name="download-the-list-of-users"></a>Скачивание списка пользователей
1. В центре администрирования PowerApps выберите слева пункт **Лицензии пользователей**.
   
    **Важно!** Этот параметр доступен только глобальным администраторам Office 365 и администраторам клиента Azure Active Directory.
   
    ![Меню "Файл", пункт "Общий доступ"](./media/admin-view-user-licenses/leftnav.png)
2. Выберите действие **Скачать список активных лицензий пользователей**.
   
    ![Меню "Файл", пункт "Общий доступ"](./media/admin-view-user-licenses/download-list.png)
   
    Скачивание файла может занять несколько минут. Подождите несколько минут, пока скачается CSV-файл, и откройте его в Excel.
   
    **Примечание.** Если закрыть окно до завершения скачивания файла, может потребоваться перезапустить процесс.

В этом примере показаны два пользователя, которым разными способами назначены лицензии PowerApps и Microsoft Flow. Елене Петровой назначен доступ через подписку Office 365. А у Ивана Петрова есть пробная лицензия каждого продукта.

![Меню "Файл", пункт "Общий доступ"](./media/admin-view-user-licenses/table2.png)

Этот список не содержит пользователей, у которых есть лицензия PowerApps и Microsoft Flow и которые никогда не обращались к этим службам. Все лицензии пользователей можно просмотреть в [центре администрирования Office 365][1].

Если пользователь покинул организацию, в столбцах **Имя пользователя** и **Адрес электронной почты** списка будет отображаться значение **Неизвестно**. Если в списке отображается значение **Неизвестно**, но никто не покидал организацию, подождите несколько минут и еще раз скачайте список.

Чтобы добавить лицензии пользователей, откройте [центр администрирования Office 365][1].

<!--Reference links in article-->
[1]:https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc
