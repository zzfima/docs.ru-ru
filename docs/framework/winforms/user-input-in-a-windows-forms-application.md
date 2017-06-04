---
title: "User Input in a Windows Forms Application | Microsoft Docs"
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
  - "Windows Forms, user input"
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# User Input in a Windows Forms Application
В Windows Forms ввод данных пользователем отправляется приложениям в виде сообщений Windows.  Эти сообщения обрабатываются рядом переопределяемых методов на уровне приложений, форм и элементов управления.  Когда эти методы получают сообщения клавиатуры и мыши, они вызывают события, которые могут быть обработаны для получения сведений о вводе данных с мыши или клавиатуры.  Во многих случаях приложения Windows Forms может обработать весь ввод пользователя путем обработки этих событий.  В других случаях приложению может потребоваться переопределить один из обрабатывающих сообщения методов, чтобы перехватить конкретное сообщение перед его получением приложением, формой или элементом управления.  
  
## События мыши и клавиатуры  
 Все элементы управления Windows Forms наследуют набор событий, связанных с вводом мыши и клавиатуры.  Например, элемент управления может обрабатывать событие <xref:System.Windows.Forms.Control.KeyPress> для определения кода знака нажатой клавиши или событие <xref:System.Windows.Forms.Control.MouseClick>, чтобы определить положение указателя мыши при щелчке.  Дополнительные сведения о событиях мыши и клавиатуры см. в разделах [Using Keyboard Events](../../../docs/framework/winforms/using-keyboard-events.md) и [Mouse Events in Windows Forms](../../../docs/framework/winforms/mouse-events-in-windows-forms.md).  
  
## Методы, которые обрабатывают сообщения ввода пользователя  
 Формы и элементы управления имеют доступ к интерфейсу <xref:System.Windows.Forms.IMessageFilter> и набору переопределяемых методов, которые обрабатывают сообщения Windows в различных местах очереди сообщений.  Все эти методы имеют параметр <xref:System.Windows.Forms.Message>, который инкапсулирует подробные данные нижнего уровня о сообщениях Windows.  Можно реализовать или переопределить эти методы для проверки сообщения и его последующего использования или передачи к следующему получателю в очереди сообщений.  В следующей таблице представлены методы, которые обрабатывают все сообщения Windows в формах Windows Forms.  
  
|Метод|Примечания|  
|-----------|----------------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|Данный метод перехватывает помещенные в очередь сообщения Windows \(также называемые отправленными\) на уровне приложения.|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|Данный метод перехватывает сообщения Windows на уровне формы и элемента управления до их обработки.|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|Этот метод обрабатывает сообщения Windows на уровне формы и элемента управления.|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|Этот метод выполняет стандартную обработку сообщений Windows на уровне формы и элемента управления.  Это обеспечивает минимальные функциональные возможности окна.|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|Данный метод перехватывает сообщения на уровне формы и элемента управления после того, как они были обработаны.  Для вызова этого метода необходимо установить бит стиля <xref:System.Windows.Forms.ControlStyles>.|  
  
 Сообщения клавиатуры и мыши также обрабатываются дополнительным набором переопределяемых методов, связанных с этими типами сообщений.  Дополнительные сведения см. в разделах [How Keyboard Input Works](../../../docs/framework/winforms/how-keyboard-input-works.md) и [How Mouse Input Works in Windows Forms](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md).  
  
## См. также  
 [User Input in Windows Forms](../../../docs/framework/winforms/user-input-in-windows-forms.md)   
 [Keyboard Input in a Windows Forms Application](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)   
 [Mouse Input in a Windows Forms Application](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)