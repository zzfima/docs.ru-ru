---
title: "Составные элементы управления | Microsoft Docs"
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
  - "составляющие элементы управления"
  - "пользовательские элементы управления [Windows Forms], составляющие элементы управления"
  - "пользовательские элементы управления [Windows Forms], составляющие элементы управления"
  - "UserControl - класс"
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Составные элементы управления
Так называемые *составные элементы управления* \(элементы управления, входящие в состав пользовательских элементов управления\) являются не очень гибкими с точки зрения пользовательской отрисовки графики.  Все элементы управления Windows Forms производят отрисовку, используя собственный метод <xref:System.Windows.Forms.Control.OnPaint%2A>.  Это защищенный метод, поэтому он недоступен разработчику, и его выполнение нельзя запретить при рисовании элемента управления.  Однако это не означает, что нельзя добавить код, который будет изменять внешний вид составного элемента управления.  Дополнительная отрисовка может выполняться путем добавления обработчика событий.  Предположим, что разрабатывается элемент управления <xref:System.Windows.Forms.UserControl> с кнопкой `MyButton`.  При необходимости дополнительной отрисовки, помимо выполняемой классом [Button Class](frlrfSystemWebUIWebControlsButtonClassTopic), в пользовательский элемент управления можно добавить код следующим образом:  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=   
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,   
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
>  Некоторые элементы управления Windows Forms, такие как <xref:System.Windows.Forms.TextBox>, рисуются непосредственно операционной системой Windows.  В этих экземплярах вызов метода <xref:System.Windows.Forms.Control.OnPaint%2A> никогда не производится и, следовательно, приведенный выше код никогда не будет выполняться.  
  
 В данном примере создается метод, который выполняется каждый раз, когда выполняется событие `MyButton.Paint`. В результате к элементу управления добавляется дополнительное графическое представление.  Обратите внимание, что это не запрещает выполнение `MyButton.OnPaint`, поэтому рисование, обычно выполняемое с помощью кнопки, по\-прежнему будет выполняться наряду с рисованием, определенным пользователем.  Дополнительные сведения о технологии GDI\+ и пользовательской отрисовке см. в разделе [Создание графических изображений с помощью GDI\+](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  При необходимости получения уникального представления элемента управления лучше всего создать наследуемый элемент управления и записать для него пользовательский код отрисовки.  Дополнительные сведения см. в разделе [Элементы управления, разработанные пользователем](../../../../docs/framework/winforms/controls/user-drawn-controls.md).  
  
## См. также  
 <xref:System.Windows.Forms.UserControl>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [Элементы управления, разработанные пользователем](../../../../docs/framework/winforms/controls/user-drawn-controls.md)   
 [Практическое руководство. Создание объектов Graphics для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Создание собственных элементов управления](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)