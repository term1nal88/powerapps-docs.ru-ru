---
title: Назначение порядка форм управляемых моделью приложений в PowerApps | MicrosoftDocs
description: Научитесь назначать форму по умолчанию в приложении
ms.custom: ''
ms.date: 06/22/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 914c5694-9c80-4424-be89-9f63256b4811
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="assign-model-driven-app-form-order"></a>Назначение порядка форм управляемых моделью приложений

 При наличии нескольких основных форм, экспресс-форм для создания или мобильных форм для сущности можно назначить порядок форм. Порядок форм определяет, какие из доступных форм будут отображаться по умолчанию. Доступным основным или мобильным формам также можно назначить роли безопасности. Дополнительные сведения см. в разделе [Контроль доступа к формам](control-access-forms.md).  
  
 Невозможно назначить роли безопасности экспресс-формам для создания, поэтому единственной формой, которая будет использоваться каждым пользователем, является форма вверху списка форм.  
  
## <a name="to-assign-a-form-order"></a>Назначение порядка форм  
  
1.  Откройте [обозреватель решений](advanced-navigation.md#solution-explorer), разверните нужную сущность и выберите **Формы**.  
  
2.  На панели инструментов списка выберите **Порядок форм**.  

     > [!div class="mx-imgBorder"] 
     > ![Команда панели инструментов порядка форм](media/form-order.png)
  
3.  Выберите **Набор основных форм**, **Набор форм быстрого создания**, **Набор экспресс-форм** или **Набор мобильных форм** в зависимости от типа форм, с которыми требуется работать. Дополнительные сведения: [Тип форм](types-forms.md). 
  
4.  В диалоговом окне **Порядок форм** представлен простой список, в котором можно перемещать выбранную форму вверх или вниз.  
  
5.  После задания требуемого порядка, нажмите кнопку **OK**, чтобы закрыть диалоговое окно.  

## <a name="next-steps"></a>Дальнейшие действия

[Изменение переходов в форме](use-the-form-editor-legacy.md)
