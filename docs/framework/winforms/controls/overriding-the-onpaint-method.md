---
title: "Переопределение метода OnPaint | Microsoft Docs"
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
  - "OnPaint - метод, переопределение в пользовательских элементах управления Windows Forms"
  - "Paint - событие, обработка событий в пользовательских элементах управления Windows Forms"
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Переопределение метода OnPaint
Основные шаги для переопределения любого события, определенного в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], идентичны и обобщены в следующем списке.  
  
#### Переопределение наследуемого события  
  
1.  Переопределите защищенный метод `On`*EventName*.  
  
2.  Вызовите метод `On`*EventName* базового класса из переопределенного метода `On`*EventName*, чтобы зарегистрированные делегаты получили событие.  
  
 Событие <xref:System.Windows.Forms.Control.Paint> описано здесь подробно, так как каждый элемент управления Windows Forms должен переопределять событие <xref:System.Windows.Forms.Control.Paint>, наследуемое им от класса <xref:System.Windows.Forms.Control>.  В базовом классе <xref:System.Windows.Forms.Control> не содержатся сведения о способе отображения производного элемента управления и какой\-либо логике рисования в методе <xref:System.Windows.Forms.Control.OnPaint%2A>.  Метод <xref:System.Windows.Forms.Control.OnPaint%2A> класса <xref:System.Windows.Forms.Control> лишь отправляет событие <xref:System.Windows.Forms.Control.Paint> зарегистрированным получателям событий.  
  
 Пример переопределения метода <xref:System.Windows.Forms.Control.OnPaint%2A> представлен в разделе [Руководство: Разработка простого элемента управления форм Windows Forms](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md).  Следующий фрагмент кода взят из этого образца.  
  
```vb  
Public Class FirstControl  
   Inherits Control  
  
   Public Sub New()  
   End Sub  
  
   Protected Overrides Sub OnPaint(e As PaintEventArgs)  
      ' Call the OnPaint method of the base class.  
      MyBase.OnPaint(e)  
      ' Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, New SolidBrush(ForeColor), RectangleF.op_Implicit(ClientRectangle))  
   End Sub  
End Class   
```  
  
```csharp  
public class FirstControl : Control{  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }   
}   
```  
  
 Класс <xref:System.Windows.Forms.PaintEventArgs> содержит данные для события <xref:System.Windows.Forms.Control.Paint>.  Он имеет два свойства, как показано в следующем коде.  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   ...  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property   
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs {  
...  
    public System.Drawing.Rectangle ClipRectangle {}  
    public System.Drawing.Graphics Graphics {}  
...  
}  
```  
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> — прямоугольник для рисования, а свойство <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> ссылается на объект <xref:System.Drawing.Graphics>.  Классы в пространстве имен <xref:System.Drawing?displayProperty=fullName> — управляемые классы, предоставляющие доступ к функциональности [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], новой библиотеки графики Windows.  Объект <xref:System.Drawing.Graphics> содержит методы для рисования точек, строк, линий, дуг, эллипсов и многих других форм.  
  
 Элемент управления вызывает свой метод <xref:System.Windows.Forms.Control.OnPaint%2A> в случае необходимости изменения его визуального отображения.  Этот метод в свою очередь инициирует событие <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 [События](../../../../docs/standard/events/index.md)   
 [Отрисовка элементов управления Windows Forms](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)   
 [Определение событий](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)