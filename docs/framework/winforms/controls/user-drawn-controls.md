---
title: "Элементы управления, разработанные пользователем | Microsoft Docs"
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
  - "пользовательские элементы управления [Windows Forms], настраиваемые пользователем"
  - "OnPaint - метод [Windows Forms]"
  - "настраиваемые пользователем элементы управления [Windows Forms]"
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Элементы управления, разработанные пользователем
Платформа .NET Framework предоставляет возможность достаточно просто разрабатывать собственные элементы управления.  Можно создать пользовательские элементы управления, представляющие собой набор стандартных элементов управления, связанных с помощью кода, или разработать собственный элемент управления "с нуля".  Можно даже использовать наследование для создания элемента управления, который наследует из существующего элемента управления, и добавить к унаследованным возможностям новые.  Независимо от выбранного подхода платформа .NET Framework обеспечивает возможность создания пользовательского интерфейса для любого разрабатываемого элемента управления.  
  
 Рисование элемента управления сопровождается выполнением кода в методе <xref:System.Windows.Forms.Control.OnPaint%2A> элемента управления.  Единственным аргументом метода <xref:System.Windows.Forms.Control.OnPaint%2A> является объект <xref:System.Windows.Forms.PaintEventArgs>, предоставляющий все сведения и функциональные возможности, необходимые для отрисовки элемента управления.  <xref:System.Windows.Forms.PaintEventArgs> предоставляет в виде свойств два объекта\-участника, которые будут использоваться при отрисовке элемента управления.  
  
-   Объект <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> — это прямоугольник, представляющий ту часть элемента управления, которая будет нарисована.  Это может быть весь элемент управления или его часть, в зависимости от того, как рисуется элемент управления.  
  
-   Объект <xref:System.Drawing.Graphics> инскапсулирует несколько графических объектов и методов, предоставляющих функциональные возможности, необходимые для рисования элемента управления.  
  
 Дополнительные сведения об объекте <xref:System.Drawing.Graphics> и о том, как им пользоваться, содержатся в разделе [Практическое руководство. Создание объектов Graphics для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  
  
 Каждый раз, когда элемент управления рисуется или обновляется на экране, запускается событие <xref:System.Windows.Forms.Control.OnPaint%2A>. При этом объект <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> представляет прямоугольник, в котором будет выполняться рисование.  При необходимости обновления всего элемента управления объект <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> будет предоставлять его размеры.  Если обновляться должна только часть элемента управления, объект <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> будет предоставлять только ту область, которая должна быть перерисована.  Примером может служить ситуация, когда один элемент управления частично закрыт другим элементом управления или другой формой пользовательского интерфейса.  
  
 При наследовании из класса <xref:System.Windows.Forms.Control> необходимо переопределить метод <xref:System.Windows.Forms.Control.OnPaint%2A> и поместить в него код графической отрисовки.  Переопределить метод <xref:System.Windows.Forms.Control.OnPaint%2A> требуется также при предоставлении пользовательского графического интерфейса для наследуемого или пользовательского элемента управления.  Ниже представлен пример.  
  
```vb  
Protected Overrides Sub OnPaint(ByVal pe As PaintEventArgs)  
   ' Call the OnPaint method of the base class.  
   MyBase.OnPaint(pe)  
  
   ' Declare and instantiate a drawing pen.  
   Dim myPen As System.Drawing.Pen = New System.Drawing.Pen(Color.Aqua)  
  
   ' Draw an aqua rectangle in the rectangle represented by the control.  
   pe.Graphics.DrawRectangle(myPen, New Rectangle(Me.Location, Me.Size))  
End Sub  
  
```  
  
```csharp  
protected override void OnPaint(PaintEventArgs pe)  
{  
   // Call the OnPaint method of the base class.  
   base.OnPaint(pe);  
  
   // Declare and instantiate a new pen.  
   System.Drawing.Pen myPen = new System.Drawing.Pen(Color.Aqua);  
  
   // Draw an aqua rectangle in the rectangle represented by the control.  
   pe.Graphics.DrawRectangle(myPen, new Rectangle(this.Location,   
      this.Size));  
}  
  
```  
  
 В предыдущем примере описывается отрисовка элемента управления с очень простым графическим представлением.  В примере вызывается метод <xref:System.Windows.Forms.Control.OnPaint%2A> базового класса, создается объект <xref:System.Drawing.Pen>, с помощью которого будет выполняться рисование, и в прямоугольнике, заданном свойствами <xref:System.Windows.Forms.Control.Location%2A> и <xref:System.Windows.Forms.Control.Size%2A> элемента управления, рисуется эллипс.  В этом примере описывается использование объекта <xref:System.Drawing.Graphics>, содержащегося в объекте <xref:System.Windows.Forms.PaintEventArgs>, но следует отметить, что в большинстве случаев код отрисовки будет намного более сложным.  Необходимо также отметить, что при наследовании из класса, уже имеющего графическое представление \(такого как <xref:System.Windows.Forms.UserControl> или <xref:System.Windows.Forms.Button>\), в случае, если это представление не должно включаться в отрисовку, не следует вызывать метод базового класса <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
 Код, содержащийся в методе <xref:System.Windows.Forms.Control.OnPaint%2A> элемента управления, будет выполняться при первом рисовании элемента управления и при каждом его обновлении.  Чтобы убедиться, что элемент управления перерисовывается при каждом изменении его размеров, следует добавить в конструктор элемента управления следующую строку:  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
  
```  
  
> [!NOTE]
>  Чтобы реализовать элемент управления непрямоугольной формы, следует использовать свойство <xref:System.Windows.Forms.Control.Region%2A?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Windows.Forms.Control.Region%2A>   
 <xref:System.Windows.Forms.ControlStyles>   
 <xref:System.Drawing.Graphics>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 <xref:System.Windows.Forms.PaintEventArgs>   
 [Практическое руководство. Создание объектов Graphics для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Составные элементы управления](../../../../docs/framework/winforms/controls/constituent-controls.md)   
 [Создание собственных элементов управления](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)