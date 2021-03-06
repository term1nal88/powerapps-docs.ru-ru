---
title: Создание политики защиты от потери данных (DLP) | Документы Майкрософт
description: Это краткое руководство описывает создание политики защиты от потери данных (DLP) PowerApps.
author: jimholtz
ms.service: powerapps
ms.component: pa-admin
ms.topic: quickstart
ms.date: 03/30/2018
ms.author: jimholtz
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 2ebacd128846e45cc936e3f66560f6fcf27d50b8
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42840687"
---
# <a name="create-a-data-loss-prevention-dlp-policy"></a>Создание политики защиты от потери данных (DLP)
Чтобы защитить данные в организации, в PowerApps можно создать и применить политики, определяющие, каким пользовательским соединителям предоставляется общий доступ к конкретным бизнес-данным. Эти политики, которые задают правила совместного использования данных, известны как политики защиты от потери данных. Политики DLP обеспечивают унифицированное управление данными в рамках организации, а также предотвращают случайную публикацию важных бизнес-данных через соединители, такие как сайты социальных сетей.

В этой статье вы узнаете, как создать для отдельной среды политику DLP, которая предотвращает публикацию в Twitter данных из баз Common Data Service и SharePoint.

## <a name="prerequisites"></a>Технические условия
Для выполнения приведенных здесь действий требуется **одно** из следующего:
* Разрешения администратора домена клиента Azure Active Directory
* Разрешения глобального администратора Office 365
* Разрешения администратора среды PowerApps, а также лицензия плана 2 для PowerApps, плана 2 для Microsoft Flow или [пробная лицензия плана 2 для PowerApps](https://web.powerapps.com/signup?redirect=marketing&email=)

Дополнительные сведения см. в статье [Администрирование сред в PowerApps](environments-administration.md).

## <a name="sign-in-to-the-powerapps-admin-center"></a>Вход в центр администрирования PowerApps
Войдите в центр администрирования по адресу [https://admin.powerapps.com]([https://admin.powerapps.com).

## <a name="create-a-dlp-policy"></a>Создание политики защиты от потери данных
1. На панели навигации выберите **Политики данных**, а затем выберите **Создать политику**.

    ![](./media/create-dlp-policy/new-data-policy.png)
2. Поле **Имя политики данных** заполняется автоматически на основе даты и времени создания политики. Замените имя на **Безопасный доступ к данным Contoso**.

    ![](./media/create-dlp-policy/policy-name.png)
3. Параметры на вкладке **Среды** различаются в зависимости от того, являетесь ли вы администратором среды или администратором клиента. Если вы являетесь администратором среды, выберите среду в раскрывающемся списке и нажмите кнопку **Продолжить**.

    ![](./media/create-dlp-policy/select-environment.png)

    Если вы являетесь администратором клиента, вы можете создать политики DLP, применяемые для одной среды, нескольких или всех сред в рамках клиента (включая созданных с помощью пробной лицензии). В этом разделе мы выберем вариант **Применить ТОЛЬКО к выбранным окружениям** и укажем среду в раскрывающемся списке. После этого щелкните или коснитесь **Продолжить**.

    ![](./media/create-dlp-policy/select-environment-tenant.png)

    Обратите внимание, что политики DLP среды не могут переопределять политики DLP в масштабах клиента.
4. На вкладке **Группы данных** в разделе **Только бизнес-данные** нажмите кнопку **Добавить**.

    ![](./media/create-dlp-policy/data-groups.png)
5. В окне **Добавление соединителей** выберите **Common Data Service** и **SharePoint** (может потребоваться прокрутить список вниз или выполнить поиск), а затем выберите **Добавление соединителей**, чтобы добавить их в группу данных **Только бизнес-данные**.

    ![](./media/create-dlp-policy/add-connectors.png)

    Соединители могут одновременно находиться только в одной в группе данных и по умолчанию добавляются в группу **Бизнес-данные запрещены**. Переместив Common Data Service и SharePoint в группу **Только бизнес-данные**, вы запрещаете пользователям создавать последовательности и приложения, которые объединяют два этих соединителя с любым соединителем из группы **Бизнес-данные запрещены**.

6. Нажмите кнопку **Сохранить политику**.

    ![](./media/create-dlp-policy/save-policy.png)

Политика "Secure Data Access for Contoso" создается и отображается в списке политик защиты от потери данных. Так как соединитель Twitter находится в группе **Бизнес-данные запрещены**, эта политика запрещает Common Data Service и SharePoint предоставлять свои данные соединителю Twitter для общего доступа.

Администраторам рекомендуется распространять сведения о политиках DLP внутри организации, чтобы пользователи учитывали их при создании приложений.

## <a name="next-steps"></a>Дальнейшие действия
В этом разделе вы узнали, как создать для отдельной среды политику DLP, которая предотвратит случайную публикацию важных бизнес-данных в соединители, такие как Twitter. Дополнительные сведения о политиках DLP см. в статье, посвященной управлению ими.

> [!div class="nextstepaction"]
> [Управление политиками защиты от потери данных](prevent-data-loss.md)
