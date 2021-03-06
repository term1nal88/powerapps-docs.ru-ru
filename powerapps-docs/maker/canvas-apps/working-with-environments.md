---
title: Работа со средами | Документация Майкрософт
description: Переключение сред и понимание механизма изменения содержимого на ваших страницах.
author: linhtranms
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/14/2016
ms.author: litran
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c4e02adfdd5c1c4e49bb1a605ccfff463369f750
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42835297"
---
# <a name="working-with-environments-and-microsoft-powerapps"></a>Работа со средами и Microsoft PowerApps
С помощью PowerApps можно работать в различных средах и легко переключаться между ними. Общие сведения о средах см. в [обзоре сред](../../administrator/environments-overview.md), в котором подробно объясняется, для чего предназначены среды, а также рассматриваются способы создания и управления ими. В этой статье будут рассмотрены следующие темы, касающиеся сред:

* как переключать среды на сайте powerapps.com;
* как создавать приложения в правильной среде;
* как просматривать приложения в правильной среде.

## <a name="switch-the-environment"></a>Переключение сред
При регистрации и первом входе на сайт powerapps.com вы, вероятно, будете использовать среду по умолчанию. Это можно проверить в правом верхнем углу страницы.

![Среда по умолчанию](./media/working-with-environments/env-dropdown.png)

*Среда по умолчанию* доступна для всех пользователей. Для начала вы можете создавать приложения в этой среде и использовать их совместно с другими пользователями. Помимо сред, [созданных вами](../../administrator/environments-administration.md), вы также можете иметь доступ к средам, которые создали другие пользователи, если у вас есть соответствующее разрешение. Для переключения сред необходимо щелкнуть раскрывающийся список сред в верхнем правом углу и выбрать нужную среду. В этом примере показано переключение из *среды по умолчанию* в *среду 1*.

![Переключение сред](./media/working-with-environments/switch-env.png)

После переключения в другую среду (например, среду 1) отобразятся все приложения, которые вы создали или к которым у вас есть доступ в этой среде.

## <a name="create-apps-in-the-right-environment"></a>Создание приложений в правильной среде
Приложения можно разрабатывать в создаваемой среде или в среде, к которой вам предоставлен доступ. Однако создание собственной среды требует [определенного плана](../../administrator/pricing-billing-skus.md). Перед созданием приложения **необходимо выбрать среду, в которой оно будет создано**. В противном случае придется перемещать приложения между средами.

Чтобы создать приложение в правильной среде, выполните одно из следующих действий.

- Если решение PowerApps Studio не открыто, [выполните вход](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), выберите среду, в которой вы хотите создать приложение, в левой области выберите **Приложения**, а затем — **Создать приложение**.

- Если решение PowerApps Studio открыто, снова выберите среду в правом верхнем углу.

5. На странице **учетной записи** рядом с именем текущей среды щелкните **Изменить**.

6. Выберите среду, в которой нужно создать приложение.

    ![Переключение сред в PowerApps Studio](./media/working-with-environments/studio-env-dropdown2.PNG)

7. Нажмите кнопку **New** (Создать), чтобы приступить к созданию приложения. Теперь приложение будет находиться в среде, которую вы выбрали на шаге 6.

    ![Переключение сред в PowerApps Studio](./media/working-with-environments/new-app.PNG)

## <a name="view-apps-in-the-right-environment"></a>Просмотр приложений в правильной среде
При работе с веб-сайтом [powerapps.com](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) или PowerApps Studio отображаемый список приложений, подключений и пр. всегда фильтруется с учетом среды, выбранной в раскрывающемся списке. Если необходимые приложения не отображаются, всегда проверяйте, правильно ли выбрана среда.

Дополнительные сведения о средах см. в [этом обзоре](../../administrator/environments-overview.md).
