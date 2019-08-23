---
title: Элементы управления, разработанные пользователем
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user-drawn
- OnPaint method [Windows Forms]
- user-drawn controls [Windows Forms]
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
ms.openlocfilehash: 50036f5bef323368b4970a080ca7a70cf94252d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966489"
---
# <a name="user-drawn-controls"></a>Элементы управления, разработанные пользователем
.NET Framework предоставляет возможность легко разрабатывать собственные элементы управления. Можно создать пользовательский элемент управления, который является набором стандартных элементов управления, связанных с кодом, или можно разработать собственный элемент управления с нуля. Можно даже использовать наследование для создания элемента управления, который наследуется от существующего элемента управления и достиг его встроенной функциональности. Какой бы подход не использовался, .NET Framework предоставляет функциональные возможности для рисования пользовательского графического интерфейса для любого создаваемого элемента управления.  
  
 Рисование элемента управления осуществляется путем выполнения кода в <xref:System.Windows.Forms.Control.OnPaint%2A> методе элемента управления. Единственным аргументом <xref:System.Windows.Forms.Control.OnPaint%2A> метода <xref:System.Windows.Forms.PaintEventArgs> является объект, предоставляющий всю информацию и функциональные возможности, необходимые для отрисовки элемента управления. <xref:System.Windows.Forms.PaintEventArgs> Предоставляет свойства как два основных объекта, которые будут использоваться при отрисовке элемента управления:  
  
- <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>Object — прямоугольник, представляющий часть элемента управления, который будет нарисован. Это может быть весь элемент управления или его часть в зависимости от того, как этот элемент управления нарисован.  
  
- <xref:System.Drawing.Graphics>объект — инкапсулирует несколько графических объектов и методов, которые предоставляют функции, необходимые для рисования элемента управления.  
  
 Дополнительные сведения <xref:System.Drawing.Graphics> об объекте и его использовании см. в разделе [как Создание графических объектов для рисования](../advanced/how-to-create-graphics-objects-for-drawing.md).  
  
 Событие запускается каждый раз, когда элемент управления рисуется или обновляется на экране, <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> а объект представляет прямоугольник, в котором будет происходить рисование. <xref:System.Windows.Forms.Control.OnPaint%2A> Если необходимо обновить весь элемент управления, то <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> будет представлять размер всего элемента управления. Однако если необходимо обновить только часть элемента управления, <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> объект будет представлять только область, которую необходимо перерисовать. Примером такого случая может быть то, что элемент управления был частично скрыт другим элементом управления или формой в пользовательском интерфейсе.  
  
 При наследовании от <xref:System.Windows.Forms.Control> класса необходимо <xref:System.Windows.Forms.Control.OnPaint%2A> переопределить метод и предоставить код отрисовки графики в. Если вы хотите предоставить пользовательский графический интерфейс для пользовательского элемента управления или наследуемого элемента управления, это можно также сделать, переопределив <xref:System.Windows.Forms.Control.OnPaint%2A> метод. Ниже приведен пример.  
  
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
  
 В предыдущем примере показано, как визуализировать элемент управления с очень простым графическим представлением. Он вызывает <xref:System.Windows.Forms.Control.OnPaint%2A> метод базового класса, <xref:System.Drawing.Pen> создает объект для рисования и, наконец, рисует эллипс в прямоугольнике, определяемом <xref:System.Windows.Forms.Control.Location%2A> и <xref:System.Windows.Forms.Control.Size%2A> элементом управления. Хотя большая часть кода отрисовки будет значительно сложнее, в этом примере демонстрируется использование <xref:System.Drawing.Graphics> объекта, содержащегося <xref:System.Windows.Forms.PaintEventArgs> в объекте. Обратите внимание, что при наследовании от класса, у которого уже есть графическое представление, например <xref:System.Windows.Forms.UserControl> или <xref:System.Windows.Forms.Button>, и вы не хотите внедрять это представление в отрисовку, не следует <xref:System.Windows.Forms.Control.OnPaint%2A> вызывать класс Method.  
  
 Код в <xref:System.Windows.Forms.Control.OnPaint%2A> методе элемента управления будет выполняться при первом рисовании элемента управления и при каждом его обновлении. Чтобы обеспечить перерисовку элемента управления при каждом изменении его размера, добавьте следующую строку в конструктор элемента управления:  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> Используйте свойство для реализации непрямоугольного элемента управления.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [Практическое руководство. Создание графических объектов для рисования](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [Составные элементы управления](constituent-controls.md)
- [Разновидности пользовательских элементов управления](varieties-of-custom-controls.md)
