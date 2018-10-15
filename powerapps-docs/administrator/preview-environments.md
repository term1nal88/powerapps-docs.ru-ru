---
title: Среды предварительной версии | Документация Майкрософт
description: Получите преждевременный доступ к новым функциональным возможностям программы по ознакомлению с предварительной версией PowerApps.
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 08/29/2018
ms.author: manasma
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: e2c4c735827941b32ce5e019eb8d71e4328e4a7a
ms.sourcegitcommit: b8eee36e680036accb0e7d9fc7a434906af1c4d2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2018
ms.locfileid: "43297902"
---
# <a name="powerapps-preview-program"></a>Программа по ознакомлению с предварительной версией PowerApps
PowerApps обновляет платформу и ее возможности каждые несколько дней или недель. Программа по ознакомлению с предварительной версией PowerApps — это способ получить преждевременный доступ к предстоящим функциональным возможностям и обновлениям перед тем, как это будет доступно в других регионах (где развертываются приложения рабочей среды клиентов). 

С помощью программы по ознакомлению с предварительной версией PowerApps можно выполнить следующие действия:
- **Испытание, изучение и тестирование предстоящих функциональных возможностей**. Многие функции будут развернуты сначала в предварительной версии в течение нескольких дней, чтобы получить обратную связь. Участвуя в программе по ознакомлению с предварительной версией, можно быстро узнать о новых функциональных возможностях и предоставить обратную связь. Кроме того, можно использовать новые функциональные возможности, как только они достигнут регионов, где создаются их рабочие приложения.
- **Реализация непрерывности бизнеса, обеспечивая продолжение работы текущих приложений** с предстоящими обновлениями (vNext) PowerApps.

## <a name="what-in-powerapps-is-available-for-preview"></a>Что именно доступно в предварительной версии PowerApps?
Чтобы получить доступ к функциональным возможностям предварительной версии в PowerApps, необходимо находиться в среде предварительной версии. Дополнительные сведения о среде предварительной версии приведены в следующем разделе.
В настоящее время мы запустим предварительную версию для следующих сценариев в PowerApps.
1. **Создание приложений**. Этот сценарий позволяет создавать приложения на основе холста, с помощью следующей версии PowerApps. Это можно сделать, создав приложение в среде предварительной версии. Текущие ограничения включают в себя приложения на основе модели, которые не могут быть созданы в программе по ознакомлению с предварительной версией, но мы над этим работаем.
2. **Управление приложениями**. Этот сценарий позволяет управлять и совместно использовать приложения с помощью [веб-портала PowerApps][2]. Чтобы получить доступ к функциональным возможностям предварительной версии, все, что нужно сделать, это находиться в среде предварительной версии. Она перенесет вас в предварительную версию [веб-портала PowerApps ][3].
3. **Воспроизведение приложений**. Для воспроизведения приложений в предварительной версии нужно использовать веб-проигрыватель. При этом вы автоматически перейдете к [предварительной версии веб-проигрывателя][4]. Приложения будут работать с версией vNext веб-плеера PowerApps. Текущие ограничения d настоящее время недоступны в предварительной версии PowerApps Mobile для iOS, Android и Windows. Воспроизведение приложений, созданных в среде первого выпуска, может не сработать, но мы работаем над этим.
4. **Администрирование PowerApps**. Интерфейс администратора доступен для предварительной версии с помощью [предварительной версии центра администрирования PowerApps][1]

## <a name="how-to-get-early-access-to-the-upcoming-updates"></a>Как получить ранний доступ к предстоящим обновлениям?
В службе PowerApps все приложения и связанные ресурсы хранятся в среде. Ранний доступ ко всем функциональным возможностям предварительной версии также доступен в среде, созданной в регионе, где развернут vNext (предварительная версия). В настоящее время существует только один регион **Предварительная версия (Соединенные Штаты)**, как показано на рисунке ниже.

![](./media/preview-environment/env3-preview.png)

Выберите регион **Предварительная версия (Соединенные Штаты)** для среды и примите согласие на присоединение к программе по ознакомлению с предварительной версией, чтобы получить доступ к следующей версии (vNext) PowerApps.
Все приложения и другие ресурсы, созданные в этой среде, находятся в версии vNext платформы (SAAS).

## <a name="how-to-learn-about-the-latest-updates"></a>Как узнать о последних обновлениях?
О новых функциональных возможностях, доступных для предварительной версии, можно узнать в разделе [What’s new in PowerApps] (Новости о PowerApps)[5]. Функциональные возможности, которые доступны только в предварительной версии, имеют тег "Предварительная версия".

## <a name="key-scenarios-to-test-with-the-preview-program"></a>Ключевые сценарии для тестирования с помощью программы по ознакомлению с предварительной версией
1. **Подтвердите свои рабочие приложения с предстоящими обновлениями PowerApps (vNext)**

   Вы можете проверить работоспособность рабочего приложения с предстоящими обновлениями в PowerApps. Вы можете [скопировать][6] приложения из рабочей среды в среду первого выпуска и запустить приложения для тестирования сценариев. Обратите внимание, что все остальные необходимые ресурсы, такие как CustomAPI, Flow и т.д., также должны быть перемещены вместе с ним. Это создаст другую копию этих приложений и необходимых ресурсов. Можно начать тестирование новых обновлений не только для воспроизведения приложения, но также при редактировании и управлении приложениями.
   
2. **Тестирование новых функциональных возможностей доступно в предварительной версии**

   Сначала мы будем запускать множество новых функциональных возможностей в регионе **Предварительная версия (Соединенные Штаты)**. Можно опробовать новые функциональные возможности до того, как они будут доступны в других регионах (что может повлиять на вашу рабочую среду).

## <a name="how-to-provide-feedback-to-the-product-team"></a>Как отправить отзыв группе разработчиков?
Отзыв можно оставить на [форуме PowerApps] [8] или связаться с [поддержкой][9].

## <a name="what-are-the-known-issues-and-limitations"></a>Каковы известные проблемы и ограничения?
1. **Порталы и клиенты PowerApps, которые недоступны в предварительной версии** 

   Существуют определенные функциональные возможности, службы и порталы, доступные в предварительной версии.
   
   ![](./media/preview-environment/table.png)

2. **Доступ к приложениям, созданным в среде первого выпуска, из Desktop Studio в Windows**

   Как упоминалось выше, Desktop Studio в Windows недоступна в предварительной версии. Таким образом, создание или изменение приложений в среде предварительной версии может быть несовместимым с вашей Desktop Studio и отображать следующее сообщение об ошибке.
   
   ![](./media/preview-environment/error2.jpg)

   В этом случае рекомендуется использовать Web Studio для создания или изменения приложения в среде предварительной версии.

3. **База данных не может быть создана в регионе предварительной версии**

   В настоящее время вы не можете создать базу данных с помощью Common Data Service для приложений в среде региона предварительной версии (США), но мы над этим работаем.


<!--Reference links in article-->
[1]: https://preview.admin.powerapps.com
[2]: https://web.powerapps.com
[3]: https://preview.web.powerapps.com
[4]: https://preview.web.powerapps.com/webplayer
[5]: https://docs.microsoft.com/powerapps/maker/canvas-apps/release-notes
[6]: https://docs.microsoft.com/powerapps/administrator/environment-and-tenant-migration
[7]: https://preview.create.powerapps.com
[8]: https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1
[9]: https://powerapps.microsoft.com/support/
