---
title: "События изменения свойств | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "пользовательские элементы управления [Windows Forms], изменение свойств (с использованием кода)"
  - "свойства [Windows Forms], изменения"
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# События изменения свойств
Если требуется, чтобы элемент управления отправлял уведомления при изменении свойства с именем *PropertyName*, определите событие с именем *PropertyName*`Changed` и метод с именем `On`*PropertyName*`Changed`, инициирующий событие.  Правила именования в Windows Forms требуют добавления слова *Changed* к имени свойства.  Связанный тип делегата события для измененных свойством событий — <xref:System.EventHandler>, а тип данных события – <xref:System.EventArgs>.  Базовый класс <xref:System.Windows.Forms.Control> определяет множество измененных свойством событий, таких как <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged> и другие.  Вспомогательные сведения о событиях см. в разделах [События](../../../../docs/standard/events/index.md) и [События элементов управления Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md).  
  
 Полезность измененных свойством событий состоит в том, что они позволяют пользователям элемента управления присоединять обработчики событий, реагирующие на изменение.  Если для элемента управления требуется реакция на инициированное им измененное свойством событие, вместо прикрепления делегата к событию переопределите соответствующий метод `On`*PropertyName*`Changed`.  Элемент управления обычно отвечает на измененное свойством событие, обновляя другие свойства, либо частично или полностью обновляя поверхность рисования.  
  
 Следующий пример показывает, как пользовательский элемент управления `FlashTrackBar` отвечает на некоторые измененные свойством события, которые он наследует от <xref:System.Windows.Forms.Control>.  Полный пример содержится в разделе [Практическое руководство. Создание элемента управления, показывающего прогресс в форме Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## См. также  
 [События](../../../../docs/standard/events/index.md)   
 [События элементов управления Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)   
 [Свойства элементов управления Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)