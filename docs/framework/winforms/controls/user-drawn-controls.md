---
title: "Элементы управления, разработанные пользователем"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user-drawn
- OnPaint method [Windows Forms]
- user-drawn controls [Windows Forms]
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e9e486058850616c2304ce0032c35baa855fdf2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="user-drawn-controls"></a>Элементы управления, разработанные пользователем
Платформа .NET Framework предоставляет возможность легко разрабатывать собственные элементы управления. Можно создать пользовательский элемент управления, который представляет собой набор стандартных элементов управления, связанных с помощью кода, или можно разработать собственный элемент управления с самого начала копирования. Можно даже использовать наследование для создания элемента управления, который наследует от существующего элемента управления и добавить его функциональные возможности. Независимо от подхода, .NET Framework обеспечивает возможность создания пользовательского интерфейса для любого элемента управления, создаваемые вами.  
  
 Рисование элемента управления сопровождается выполнением кода в элементе управления <xref:System.Windows.Forms.Control.OnPaint%2A> метод. Единственным аргументом <xref:System.Windows.Forms.Control.OnPaint%2A> метод <xref:System.Windows.Forms.PaintEventArgs> объект, предоставляющий все сведения и функциональные возможности, необходимые для визуализации элемента управления. <xref:System.Windows.Forms.PaintEventArgs> Предоставляет два объекта-участника, которые будут использоваться при отрисовке элемента управления в виде свойств:  
  
-   <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>Объект - прямоугольник, представляющий элемент управления, которая будет нарисована. Это может быть весь элемент управления или элемента управления в зависимости от того, как отображается элемент управления.  
  
-   <xref:System.Drawing.Graphics>объект - инкапсулирует несколько графических объектов и методов, которые предоставляют функциональные возможности, необходимые для рисования элемента управления.  
  
 Дополнительные сведения о <xref:System.Drawing.Graphics> объекта и способах ее использования см. в разделе [как: Создание графических объектов для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A> Событие каждый раз, когда элемент управления рисуется или обновляется на экране и <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> объект представляет прямоугольник, в котором рисования будет иметь место. Если весь элемент управления должен быть обновлен, <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> будет представлять размер всего элемента управления. Если только часть элемента управления необходимо обновить, однако <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> будет представлять только область, которая должна быть перерисованы. Пример в этом случае может быть, если элемент управления частично закрыт другим элементом управления или формы в пользовательском интерфейсе.  
  
 При наследовании от <xref:System.Windows.Forms.Control> , необходимо переопределить <xref:System.Windows.Forms.Control.OnPaint%2A> метод и предоставить код отрисовки графики в пределах. Если вы хотите предоставить пользовательский элемент управления или элемент управления пользовательского интерфейса, это можно также сделать путем переопределения <xref:System.Windows.Forms.Control.OnPaint%2A> метод. Ниже показан пример:  
  
```vb  
Protected Overrides Sub OnPaint(ByVal e As PaintEventArgs)  
   ' Call the OnPaint method of the base class.  
   MyBase.OnPaint(e)  
  
   ' Declare and instantiate a drawing pen.  
   Using myPen As System.Drawing.Pen = New System.Drawing.Pen(Color.Aqua)  
      ' Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, New Rectangle(Me.Location, Me.Size))  
   End Using
End Sub  
```  
  
```csharp  
protected override void OnPaint(PaintEventArgs e)  
{  
   // Call the OnPaint method of the base class.  
   base.OnPaint(e);  
  
   // Declare and instantiate a new pen.  
   using (System.Drawing.Pen myPen = new System.Drawing.Pen(Color.Aqua))  
   {
      // Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, new Rectangle(this.Location,   
         this.Size));  
   }
}  
```  
  
 В предыдущем примере показано, как для отображения элемента управления с очень простым графическим представлением. Он вызывает <xref:System.Windows.Forms.Control.OnPaint%2A> метод базового класса, он создает <xref:System.Drawing.Pen> для рисования объектов, и наконец определяется рисуется эллипс в прямоугольнике <xref:System.Windows.Forms.Control.Location%2A> и <xref:System.Windows.Forms.Control.Size%2A> элемента управления. Несмотря на то, что большая часть кода отрисовки будет намного более сложным, в этом примере показано использование функции <xref:System.Drawing.Graphics> объект, содержащийся в <xref:System.Windows.Forms.PaintEventArgs> объекта. Обратите внимание, что если наследуются от класса, который уже имеет графическое представление, например <xref:System.Windows.Forms.UserControl> или <xref:System.Windows.Forms.Button>и необходимо включить это представление в отрисовку, не следует вызывать базовый класс <xref:System.Windows.Forms.Control.OnPaint%2A> метод.  
  
 Код в <xref:System.Windows.Forms.Control.OnPaint%2A> метод элемента управления будет выполняться при первом рисовании элемента управления, и при его обновлении. Чтобы убедиться, что элемент управления перерисовывается при каждом изменении его размера, конструктор элемента управления добавьте следующую строку:  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
>  Используйте <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> свойство для реализации нестандартной управления.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Control.Region%2A>  
 <xref:System.Windows.Forms.ControlStyles>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Windows.Forms.PaintEventArgs>  
 [Практическое руководство. Создание графических объектов для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Составные элементы управления](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 [Разновидности пользовательских элементов управления](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
