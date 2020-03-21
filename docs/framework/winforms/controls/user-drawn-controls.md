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
ms.openlocfilehash: c68c8c88376cfe7295962264c466030115f2f3db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182012"
---
# <a name="user-drawn-controls"></a>Элементы управления, разработанные пользователем
Рамочный механизм .NET позволяет легко разрабатывать собственные элементы управления. Вы можете создать пользовательский контроль, который представляет собой набор стандартных элементов управления, связанных между собой кодом, или вы можете создать свой собственный элемент управления с нуля. Вы даже можете использовать наследование для создания элемента управления, который наследует от существующего элемента управления и добавляет ему присущую ему функциональность. Какой бы подход вы ни использовали, в интерфейсе .NET содержится функциональность для создания пользовательского графического интерфейса для любого создаваемого элемента управления.  
  
 Картина элемента управления осуществляется путем выполнения кода <xref:System.Windows.Forms.Control.OnPaint%2A> в методе управления. Единственным аргументом <xref:System.Windows.Forms.Control.OnPaint%2A> метода <xref:System.Windows.Forms.PaintEventArgs> является объект, который предоставляет всю информацию и функциональность, необходимые для визуализации вашего контроля. В <xref:System.Windows.Forms.PaintEventArgs> свойствах предусмотрены два основных объекта, которые будут использоваться при визуализации элемента управления:  
  
- <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>объект - прямоугольник, представляющий ту часть элемента управления, которая будет нарисована. Это может быть весь элемент управления или часть элемента управления в зависимости от того, как элемент управления обращается.  
  
- <xref:System.Drawing.Graphics>объект - инкапсулирует несколько графически ориентированных объектов и методов, которые обеспечивают функциональность, необходимую для рисования вашего управления.  
  
 Для получения дополнительной <xref:System.Drawing.Graphics> информации об объекте и о том, как его использовать, см. [How to: Create Graphics Objects for Drawing](../advanced/how-to-create-graphics-objects-for-drawing.md)  
  
 Событие <xref:System.Windows.Forms.Control.OnPaint%2A> выключается всякий раз, когда элемент управления нарисован или обновляется на экране, и <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> объект представляет прямоугольник, в котором будет происходить живопись. Если весь элемент управления должен быть <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> обновлен, будет представлять размер всего элемента управления. Однако, если необходимо обновить только часть элемента управления, <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> объект будет представлять только область, которая должна быть перерисована. Примером такого случая может быть случай, когда элемент управления частично заслонен другим элементом управления или формой в пользовательском интерфейсе.  
  
 При наследовании <xref:System.Windows.Forms.Control> от класса <xref:System.Windows.Forms.Control.OnPaint%2A> необходимо переопределить метод и предоставить графический код. Если вы хотите предоставить пользовательский графический интерфейс для управления пользователем или унаследованного элемента управления, вы также можете сделать это, переопределив <xref:System.Windows.Forms.Control.OnPaint%2A> метод. Пример приведен ниже.  
  
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
  
 Предыдущий пример показывает, как сделать элемент управления с очень простым графическим представлением. Он вызывает <xref:System.Windows.Forms.Control.OnPaint%2A> метод базового класса, <xref:System.Drawing.Pen> он создает объект, с помощью <xref:System.Windows.Forms.Control.Location%2A> <xref:System.Windows.Forms.Control.Size%2A> которого рисовать, и, наконец, рисует эллипс в прямоугольнике, определяемом и элементом управления. Хотя большинство кода рендеринга будет значительно сложнее, чем этот <xref:System.Drawing.Graphics> пример, <xref:System.Windows.Forms.PaintEventArgs> этот пример демонстрирует использование объекта, содержащегося в объекте. Обратите внимание, что если вы наследуете от класса, <xref:System.Windows.Forms.UserControl> который <xref:System.Windows.Forms.Button>уже имеет графическое представление, например, или, и вы не <xref:System.Windows.Forms.Control.OnPaint%2A> хотите, чтобы включить это представление в вашей визуализации, вы не должны называть метод вашего базового класса.  
  
 Код в <xref:System.Windows.Forms.Control.OnPaint%2A> методе управления будет выполняться при первом нарисованном элементе управления и при обновлении. Чтобы убедиться, что элемент управления перерисовывается каждый раз, когда он перестраивается, добавьте следующую строку к конструктору элемента управления:  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> Используйте <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> свойство для реализации непрямоугольного управления.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [Практическое руководство. Создание объектов Graphics для рисования](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [Составные элементы управления](constituent-controls.md)
- [Создание собственных элементов управления](varieties-of-custom-controls.md)
