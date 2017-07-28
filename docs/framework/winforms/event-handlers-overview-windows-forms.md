---
title: "Event Handlers Overview (Windows Forms) | Microsoft Docs"
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
  - "Windows Forms, event handling"
  - "event handling, Windows Forms"
  - "event handlers, about event handlers"
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Event Handlers Overview (Windows Forms)
Обработчик событий — это метод, связанный с событием.  При возникновении события выполняется код внутри обработчика событий.  В каждом обработчике событий существует два параметра, которые позволяют правильно обработать событие.  В следующем примере показан обработчик события <xref:System.Windows.Forms.Control.Click> для элемента управления <xref:System.Windows.Forms.Button>.  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)   
{  
  
}  
  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 Первый параметр,`sender`, предоставляет ссылку на объект, вызвавший событие.  Второй параметр, `e`, в примере передает объект, связанный с обрабатываемым событием.  С помощью ссылки на свойства объекта \(а также на его методы\) можно получить сведения, например, о расположении мыши в событиях, вызываемых с помощью мыши, или о данных, которые передаются в ходе событий, возникающих при перетаскивании.  
  
 Обычно каждое событие создает обработчик событий с разными типами объекта события для второго параметра.  Некоторые обработчики событий, например обработчики для событий <xref:System.Windows.Forms.Control.MouseDown> и <xref:System.Windows.Forms.Control.MouseUp>, имеют одинаковый тип объекта для второго параметра.  Для этих типов событий можно использовать один и тот же обработчик событий.  
  
 Можно также использовать один и тот же обработчик событий для обработки одного события для разных элементов управления.  Например, при наличии в форме группы элементов управления <xref:System.Windows.Forms.RadioButton> можно создать один обработчик для события <xref:System.Windows.Forms.Control.Click> и привязать событие <xref:System.Windows.Forms.Control.Click> каждого элемента управления к этому обработчику.  Дополнительные сведения см. в разделе [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).  
  
## См. также  
 [Creating Event Handlers in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)   
 [Events Overview](../../../docs/framework/winforms/events-overview-windows-forms.md)