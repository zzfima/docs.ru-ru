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
# <a name="user-drawn-controls"></a><span data-ttu-id="5e607-102">Элементы управления, разработанные пользователем</span><span class="sxs-lookup"><span data-stu-id="5e607-102">User-Drawn Controls</span></span>
<span data-ttu-id="5e607-103">Рамочный механизм .NET позволяет легко разрабатывать собственные элементы управления.</span><span class="sxs-lookup"><span data-stu-id="5e607-103">The .NET Framework provides you with the ability to easily develop your own controls.</span></span> <span data-ttu-id="5e607-104">Вы можете создать пользовательский контроль, который представляет собой набор стандартных элементов управления, связанных между собой кодом, или вы можете создать свой собственный элемент управления с нуля.</span><span class="sxs-lookup"><span data-stu-id="5e607-104">You can create a user control, which is a set of standard controls bound together by code, or you can design your own control from the ground up.</span></span> <span data-ttu-id="5e607-105">Вы даже можете использовать наследование для создания элемента управления, который наследует от существующего элемента управления и добавляет ему присущую ему функциональность.</span><span class="sxs-lookup"><span data-stu-id="5e607-105">You can even use inheritance to create a control that inherits from an existing control and add to its inherent functionality.</span></span> <span data-ttu-id="5e607-106">Какой бы подход вы ни использовали, в интерфейсе .NET содержится функциональность для создания пользовательского графического интерфейса для любого создаваемого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5e607-106">Whatever approach you use, the .NET Framework provides the functionality to draw a custom graphical interface for any control you create.</span></span>  
  
 <span data-ttu-id="5e607-107">Картина элемента управления осуществляется путем выполнения кода <xref:System.Windows.Forms.Control.OnPaint%2A> в методе управления.</span><span class="sxs-lookup"><span data-stu-id="5e607-107">Painting of a control is accomplished by the execution of code in the control's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="5e607-108">Единственным аргументом <xref:System.Windows.Forms.Control.OnPaint%2A> метода <xref:System.Windows.Forms.PaintEventArgs> является объект, который предоставляет всю информацию и функциональность, необходимые для визуализации вашего контроля.</span><span class="sxs-lookup"><span data-stu-id="5e607-108">The single argument of the <xref:System.Windows.Forms.Control.OnPaint%2A> method is a <xref:System.Windows.Forms.PaintEventArgs> object that provides all of the information and functionality required to render your control.</span></span> <span data-ttu-id="5e607-109">В <xref:System.Windows.Forms.PaintEventArgs> свойствах предусмотрены два основных объекта, которые будут использоваться при визуализации элемента управления:</span><span class="sxs-lookup"><span data-stu-id="5e607-109">The <xref:System.Windows.Forms.PaintEventArgs> provides as properties two principal objects that will be used in the rendering of your control:</span></span>  
  
- <span data-ttu-id="5e607-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>объект - прямоугольник, представляющий ту часть элемента управления, которая будет нарисована.</span><span class="sxs-lookup"><span data-stu-id="5e607-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object - the rectangle that represents the part of the control that will be drawn.</span></span> <span data-ttu-id="5e607-111">Это может быть весь элемент управления или часть элемента управления в зависимости от того, как элемент управления обращается.</span><span class="sxs-lookup"><span data-stu-id="5e607-111">This can be the entire control, or part of the control depending on how the control is drawn.</span></span>  
  
- <span data-ttu-id="5e607-112"><xref:System.Drawing.Graphics>объект - инкапсулирует несколько графически ориентированных объектов и методов, которые обеспечивают функциональность, необходимую для рисования вашего управления.</span><span class="sxs-lookup"><span data-stu-id="5e607-112"><xref:System.Drawing.Graphics> object - encapsulates several graphics-oriented objects and methods that provide the functionality necessary to draw your control.</span></span>  
  
 <span data-ttu-id="5e607-113">Для получения дополнительной <xref:System.Drawing.Graphics> информации об объекте и о том, как его использовать, см. [How to: Create Graphics Objects for Drawing](../advanced/how-to-create-graphics-objects-for-drawing.md)</span><span class="sxs-lookup"><span data-stu-id="5e607-113">For more information on the <xref:System.Drawing.Graphics> object and how to use it, see [How to: Create Graphics Objects for Drawing](../advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
 <span data-ttu-id="5e607-114">Событие <xref:System.Windows.Forms.Control.OnPaint%2A> выключается всякий раз, когда элемент управления нарисован или обновляется на экране, и <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> объект представляет прямоугольник, в котором будет происходить живопись.</span><span class="sxs-lookup"><span data-stu-id="5e607-114">The <xref:System.Windows.Forms.Control.OnPaint%2A> event is fired whenever the control is drawn or refreshed on the screen, and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object represents the rectangle in which painting will take place.</span></span> <span data-ttu-id="5e607-115">Если весь элемент управления должен быть <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> обновлен, будет представлять размер всего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5e607-115">If the entire control needs to be refreshed, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> will represent the size of the entire control.</span></span> <span data-ttu-id="5e607-116">Однако, если необходимо обновить только часть элемента управления, <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> объект будет представлять только область, которая должна быть перерисована.</span><span class="sxs-lookup"><span data-stu-id="5e607-116">If only part of the control needs to be refreshed, however, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object will represent only the region that needs to be redrawn.</span></span> <span data-ttu-id="5e607-117">Примером такого случая может быть случай, когда элемент управления частично заслонен другим элементом управления или формой в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="5e607-117">An example of such a case would be when a control was partially obscured by another control or form in the user interface.</span></span>  
  
 <span data-ttu-id="5e607-118">При наследовании <xref:System.Windows.Forms.Control> от класса <xref:System.Windows.Forms.Control.OnPaint%2A> необходимо переопределить метод и предоставить графический код.</span><span class="sxs-lookup"><span data-stu-id="5e607-118">When inheriting from the <xref:System.Windows.Forms.Control> class, you must override the <xref:System.Windows.Forms.Control.OnPaint%2A> method and provide graphics-rendering code within.</span></span> <span data-ttu-id="5e607-119">Если вы хотите предоставить пользовательский графический интерфейс для управления пользователем или унаследованного элемента управления, вы также можете сделать это, переопределив <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="5e607-119">If you want to provide a custom graphical interface to a user control or an inherited control, you can also do so by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="5e607-120">Пример приведен ниже.</span><span class="sxs-lookup"><span data-stu-id="5e607-120">An example is shown below:</span></span>  
  
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
  
 <span data-ttu-id="5e607-121">Предыдущий пример показывает, как сделать элемент управления с очень простым графическим представлением.</span><span class="sxs-lookup"><span data-stu-id="5e607-121">The preceding example demonstrates how to render a control with a very simple graphical representation.</span></span> <span data-ttu-id="5e607-122">Он вызывает <xref:System.Windows.Forms.Control.OnPaint%2A> метод базового класса, <xref:System.Drawing.Pen> он создает объект, с помощью <xref:System.Windows.Forms.Control.Location%2A> <xref:System.Windows.Forms.Control.Size%2A> которого рисовать, и, наконец, рисует эллипс в прямоугольнике, определяемом и элементом управления.</span><span class="sxs-lookup"><span data-stu-id="5e607-122">It calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class, it creates a <xref:System.Drawing.Pen> object with which to draw, and finally draws an ellipse in the rectangle determined by the <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Size%2A> of the control.</span></span> <span data-ttu-id="5e607-123">Хотя большинство кода рендеринга будет значительно сложнее, чем этот <xref:System.Drawing.Graphics> пример, <xref:System.Windows.Forms.PaintEventArgs> этот пример демонстрирует использование объекта, содержащегося в объекте.</span><span class="sxs-lookup"><span data-stu-id="5e607-123">Although most rendering code will be significantly more complicated than this, this example demonstrates the use of the <xref:System.Drawing.Graphics> object contained within the <xref:System.Windows.Forms.PaintEventArgs> object.</span></span> <span data-ttu-id="5e607-124">Обратите внимание, что если вы наследуете от класса, <xref:System.Windows.Forms.UserControl> который <xref:System.Windows.Forms.Button>уже имеет графическое представление, например, или, и вы не <xref:System.Windows.Forms.Control.OnPaint%2A> хотите, чтобы включить это представление в вашей визуализации, вы не должны называть метод вашего базового класса.</span><span class="sxs-lookup"><span data-stu-id="5e607-124">Note that if you are inheriting from a class that already has a graphical representation, such as <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Button>, and you do not wish to incorporate that representation into your rendering, you should not call your base class's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
 <span data-ttu-id="5e607-125">Код в <xref:System.Windows.Forms.Control.OnPaint%2A> методе управления будет выполняться при первом нарисованном элементе управления и при обновлении.</span><span class="sxs-lookup"><span data-stu-id="5e607-125">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="5e607-126">Чтобы убедиться, что элемент управления перерисовывается каждый раз, когда он перестраивается, добавьте следующую строку к конструктору элемента управления:</span><span class="sxs-lookup"><span data-stu-id="5e607-126">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> <span data-ttu-id="5e607-127">Используйте <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> свойство для реализации непрямоугольного управления.</span><span class="sxs-lookup"><span data-stu-id="5e607-127">Use the <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> property to implement a non-rectangular control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e607-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5e607-128">See also</span></span>

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [<span data-ttu-id="5e607-129">Практическое руководство. Создание объектов Graphics для рисования</span><span class="sxs-lookup"><span data-stu-id="5e607-129">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="5e607-130">Составные элементы управления</span><span class="sxs-lookup"><span data-stu-id="5e607-130">Constituent Controls</span></span>](constituent-controls.md)
- [<span data-ttu-id="5e607-131">Создание собственных элементов управления</span><span class="sxs-lookup"><span data-stu-id="5e607-131">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
