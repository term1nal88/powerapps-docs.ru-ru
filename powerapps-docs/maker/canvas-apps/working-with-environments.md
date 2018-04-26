---
title: Работа со средами | Документация Майкрософт
description: Переключение сред и понимание механизма изменения содержимого на ваших страницах.
documentationcenter: na
author: linhtranms
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 10/14/2016
ms.author: litran
ms.openlocfilehash: fa1dcd264e99a2bea333d7b6aa0bbf2e04cd47e9
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
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
Вы можете создавать приложения в существующих средах, к которым у вас есть доступ, или в новых средах. Однако создание собственной среды требует определенного плана. Дополнительные сведения см. [здесь](../../administrator/pricing-billing-skus.md). Перед созданием приложения **необходимо выбрать среду, в которой оно будет создано**. В противном случае придется перемещать приложения между средами.

1. Если вы находитесь на сайте [powerapps.com](http://web.powerapps.com), выберите среду, в которой нужно создать приложение. Если вы находитесь в *PowerApps Studio* или *PowerApps Studio для Интернета*, перейдите к шагу 4.

2. Нажмите кнопку **+ Создать приложение**.

3. Выберите **PowerApps Studio** или **PowerApps Studio для Интернета**.

4. Когда *PowerApps Studio* или *PowerApps Studio для Интернета* откроется, снова выберите среду в правом верхнем углу. В будущем мы исправим это неудобство, однако в текущем выпуске необходимо выбирать среду каждый раз при создании приложения в новой среде.

    ![Переключение сред в PowerApps Studio](./media/working-with-environments/studio-switch-env.PNG)

5. На странице **учетной записи** рядом с именем текущей среды щелкните **Изменить**.

    ![Переключение сред в PowerApps Studio](./media/working-with-environments/studio-env-dropdown.PNG)

6. Выберите среду, в которой нужно создать приложение.

    ![Переключение сред в PowerApps Studio](./media/working-with-environments/studio-env-dropdown2.PNG)

7. Нажмите кнопку **New** (Создать), чтобы приступить к созданию приложения. Теперь приложение будет находиться в среде, которую вы выбрали на шаге 6.

    ![Переключение сред в PowerApps Studio](./media/working-with-environments/new-app.PNG)

## <a name="view-apps-in-the-right-environment"></a>Просмотр приложений в правильной среде
При работе с веб-сайтом [powerapps.com](http://web.powerapps.com), версией PowerApps Studio для Windows или PowerApps Studio для Интернета отображаемый список приложений, подключений и пр. всегда фильтруется с учетом среды, выбранной в раскрывающемся списке. Если необходимые приложения не отображаются, всегда проверяйте, правильно ли выбрана среда.

Для переключения сред на веб-сайте [powerapps.com](http://web.powerapps.com):

![Переключение сред](./media/working-with-environments/switch-env.png)

Для переключения сред в PowerApps Studio для Windows или PowerApps Studio для Интернета:

![Переключение сред в PowerApps Studio](./media/working-with-environments/studio-switch-env.PNG)

Дополнительные сведения о средах см. в [этом обзоре](../../administrator/environments-overview.md).
