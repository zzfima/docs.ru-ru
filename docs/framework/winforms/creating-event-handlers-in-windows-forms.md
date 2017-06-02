---
title: "Creating Event Handlers in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "event handling [Windows Forms]"
  - "Windows Forms controls, event handling"
  - "Windows Forms, event handling"
  - "events [Windows Forms], event handlers"
  - "event handlers [Windows Forms]"
ms.assetid: 6514e530-c6b8-489c-a8d2-eda7b7072701
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Creating Event Handlers in Windows Forms
Обработчик событий — это процедура в коде, определяющая, какие действия должны выполняться при возникновении тех или иных событий, например, если пользователь нажимает кнопку или сообщение поступает в очередь.  При порождении события запускается получивший его обработчик или несколько обработчиков.  События могут назначаться сразу нескольким обработчикам, а методы, которые управляют конкретными событиями, можно изменять динамически.  Для создания обработчиков событий можно также использовать Конструктор Windows Forms.  
  
## В этом подразделе  
 [Events Overview](../../../docs/framework/winforms/events-overview-windows-forms.md)  
 Объясняет модель событий и роли делегатов.  
  
 [Event Handlers Overview](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)  
 Описывает порядок обработки событий.  
  
 [How to: Create Event Handlers at Run Time for Windows Forms](../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md)  
 Динамически выдает инструкции по реагированию на системные или пользовательские события.  
  
 [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)  
 Выдает инструкции по назначению одной и той же функциональности нескольким элементам управления с помощью событий.  
  
 [Order of Events in Windows Forms](../../../docs/framework/winforms/order-of-events-in-windows-forms.md)  
 Описывает порядок порождения событий в элементах управления Windows Forms.  
  
 [Руководство: создание обработчика событий с помощью конструктора](http://msdn.microsoft.com/ru-ru/8461e9b8-14e8-406f-936e-3726732b23d2)  
 Описывает использование Конструктора Windows Forms для создания обработчиков событий.  
  
## Связанные подразделы  
 [События](../../../docs/standard/events/index.md)  
 Содержит ссылки на разделы по обработке и порождению событий с помощью [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].  
  
 [Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md)  
 Представляет распространенные проблемы, возникающие у обработчиков событий в наследуемых компонентах.