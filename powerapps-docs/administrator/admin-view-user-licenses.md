---
title: Скачивание списка активных пользователей в клиенте | Документы Майкрософт
description: Это краткое руководство описывает, как скачать список активных пользователей в клиенте.
author: jimholtz
ms.service: powerapps
ms.component: pa-admin
ms.topic: quickstart
ms.date: 03/21/2018
ms.author: jimholtz
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 41f557b7b4def385a505e3bc3047354add81955e
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42832455"
---
# <a name="download-a-list-of-active-users-in-your-tenant"></a>Скачивание списка активных пользователей в клиенте
Если вы являетесь глобальным администратором Office 365 или администратором клиента Azure Active Directory, то можете скачать список активных пользователей в своем клиенте, чтобы можно было просмотреть не только пользователей, которые получали доступ к PowerApps и Microsoft Flow, но и назначенные им лицензии.

В этих разделах вы узнаете, как скачать список активных пользователей в виде CSV-файла и затем просмотреть его в Excel.

Чтобы выполнить приведенные здесь действия, вам потребуются права глобального администратора Office 365 или администратора клиента Azure Active Directory.

## <a name="sign-in-to-the-powerapps-admin-center"></a>Вход в центр администрирования PowerApps
Войдите в центр администрирования по адресу [https://admin.powerapps.com]([https://admin.powerapps.com).

## <a name="download-the-list-of-users"></a>Скачивание списка пользователей
На панели навигации выберите пункт **Пользовательские лицензии**, а затем **Скачать список активных пользовательских лицензий**.

![Меню "Файл", пункт "Общий доступ"](./media/admin-view-user-licenses/download-list.png)

Список пользователей скачивается в виде CSV-файла. Этот процесс может занять несколько минут. Не закрывайте окно до завершения скачивания списка. В противном случае может потребоваться перезапустить процесс.

## <a name="view-the-list"></a>Просмотр списка
После создания CSV-файла откройте его в Excel. Список содержит имя каждого пользователя, адрес электронной почты, тип лицензии и другие сведения.

Пользователь, который воспользовался продуктом по меньшей мере один раз, считается *активным*. Так как это список активных пользователей, он не содержит пользователей, имеющих лицензии PowerApps и Microsoft Flow и никогда не обращавшихся к этим службам. Все лицензии пользователей можно просмотреть в [Центре администрирования Office 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

В следующем примере показаны два пользователя, имеющие лицензии PowerApps и Microsoft Flow. Елене Петровой назначен доступ через подписку Office 365. А у Ивана Петрова есть пробная лицензия каждого продукта.

![Меню "Файл", пункт "Общий доступ"](./media/admin-view-user-licenses/table2.png)

Если пользователь покинул организацию, в столбцах **Имя пользователя** и **Адрес электронной почты** списка будет отображаться значение **Неизвестно**. Если в списке отображается значение **Неизвестно**, но никто не покидал организацию, подождите несколько минут и еще раз скачайте список.

Чтобы добавить лицензии пользователей, откройте [Центр администрирования Office 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

## <a name="next-steps"></a>Дальнейшие действия
В этом разделе вы узнали, как скачать и просмотреть список активных пользователей в клиенте. Следующий раздел рассказывает о том, как скачивать и просматривать список приложений, созданных в ваших средах.

> [!div class="nextstepaction"]
> [Скачивание списка приложений, созданных в ваших средах](admin-view-apps.md)
