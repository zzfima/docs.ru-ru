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
ms.openlocfilehash: 06513fc44782c78d2d69b82130542949519c0107
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947957"
---
# <a name="user-drawn-controls"></a><span data-ttu-id="231a8-102">Элементы управления, разработанные пользователем</span><span class="sxs-lookup"><span data-stu-id="231a8-102">User-Drawn Controls</span></span>
<span data-ttu-id="231a8-103">.NET Framework дает возможность легко разрабатывать собственные элементы управления.</span><span class="sxs-lookup"><span data-stu-id="231a8-103">The .NET Framework provides you with the ability to easily develop your own controls.</span></span> <span data-ttu-id="231a8-104">Вы можете создать пользовательский элемент управления, который представляет собой набор стандартных элементов управления, связанных с помощью кода, или можно разработать собственный элемент управления с нуля вверх.</span><span class="sxs-lookup"><span data-stu-id="231a8-104">You can create a user control, which is a set of standard controls bound together by code, or you can design your own control from the ground up.</span></span> <span data-ttu-id="231a8-105">Можно даже использовать наследование создать элемент управления, который наследует от существующего элемента управления и добавить его функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="231a8-105">You can even use inheritance to create a control that inherits from an existing control and add to its inherent functionality.</span></span> <span data-ttu-id="231a8-106">Какой бы подход, вы используете, платформа .NET Framework предоставляет функциональные возможности для создания пользовательского интерфейса для любого элемента управления, которые можно создать.</span><span class="sxs-lookup"><span data-stu-id="231a8-106">Whatever approach you use, the .NET Framework provides the functionality to draw a custom graphical interface for any control you create.</span></span>  
  
 <span data-ttu-id="231a8-107">Рисование элемента управления достигается путем выполнения кода в элементе управления <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="231a8-107">Painting of a control is accomplished by the execution of code in the control's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="231a8-108">Единственным аргументом <xref:System.Windows.Forms.Control.OnPaint%2A> метод <xref:System.Windows.Forms.PaintEventArgs> объект, предоставляющий все сведения и функциональные возможности, необходимые для подготовки к просмотру элемента управления.</span><span class="sxs-lookup"><span data-stu-id="231a8-108">The single argument of the <xref:System.Windows.Forms.Control.OnPaint%2A> method is a <xref:System.Windows.Forms.PaintEventArgs> object that provides all of the information and functionality required to render your control.</span></span> <span data-ttu-id="231a8-109"><xref:System.Windows.Forms.PaintEventArgs> Предоставляет два объекта-участника, которые будут использоваться при подготовке к просмотру элемента управления в виде свойств:</span><span class="sxs-lookup"><span data-stu-id="231a8-109">The <xref:System.Windows.Forms.PaintEventArgs> provides as properties two principal objects that will be used in the rendering of your control:</span></span>  
  
- <span data-ttu-id="231a8-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Объект - прямоугольник, представляющий часть элемента управления, который будет заменен.</span><span class="sxs-lookup"><span data-stu-id="231a8-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object - the rectangle that represents the part of the control that will be drawn.</span></span> <span data-ttu-id="231a8-111">Это может быть весь элемент управления или части элемента управления в зависимости от того, как элемент управления отображается.</span><span class="sxs-lookup"><span data-stu-id="231a8-111">This can be the entire control, or part of the control depending on how the control is drawn.</span></span>  
  
- <span data-ttu-id="231a8-112"><xref:System.Drawing.Graphics> объект - инкапсулирует несколько графических объектов и методов, которые предоставляют функциональные возможности, необходимые для рисования элемента управления.</span><span class="sxs-lookup"><span data-stu-id="231a8-112"><xref:System.Drawing.Graphics> object - encapsulates several graphics-oriented objects and methods that provide the functionality necessary to draw your control.</span></span>  
  
 <span data-ttu-id="231a8-113">Дополнительные сведения о <xref:System.Drawing.Graphics> объекта и как его использовать, см. в разделе [как: Создание объектов Graphics для рисования](../advanced/how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="231a8-113">For more information on the <xref:System.Drawing.Graphics> object and how to use it, see [How to: Create Graphics Objects for Drawing](../advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
 <span data-ttu-id="231a8-114"><xref:System.Windows.Forms.Control.OnPaint%2A> Событие каждый раз, когда рисуется элемент управления или обновляется на экране и <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> представляет прямоугольник, в котором рисования, будет иметь место.</span><span class="sxs-lookup"><span data-stu-id="231a8-114">The <xref:System.Windows.Forms.Control.OnPaint%2A> event is fired whenever the control is drawn or refreshed on the screen, and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object represents the rectangle in which painting will take place.</span></span> <span data-ttu-id="231a8-115">Если весь элемент управления необходимо обновить, <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> будет представлять размер всего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="231a8-115">If the entire control needs to be refreshed, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> will represent the size of the entire control.</span></span> <span data-ttu-id="231a8-116">Если только часть элемента управления должен быть обновлен, однако <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> объект будет представлять только область, которая должна быть перерисована.</span><span class="sxs-lookup"><span data-stu-id="231a8-116">If only part of the control needs to be refreshed, however, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object will represent only the region that needs to be redrawn.</span></span> <span data-ttu-id="231a8-117">Примером такого случая может быть, если элемент управления частично закрыт другим элементом управления или формы в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="231a8-117">An example of such a case would be when a control was partially obscured by another control or form in the user interface.</span></span>  
  
 <span data-ttu-id="231a8-118">При наследовании от <xref:System.Windows.Forms.Control> , необходимо переопределить <xref:System.Windows.Forms.Control.OnPaint%2A> метод и предоставить код отрисовки графики в пределах.</span><span class="sxs-lookup"><span data-stu-id="231a8-118">When inheriting from the <xref:System.Windows.Forms.Control> class, you must override the <xref:System.Windows.Forms.Control.OnPaint%2A> method and provide graphics-rendering code within.</span></span> <span data-ttu-id="231a8-119">Если вы хотите предоставить пользовательский графический интерфейс для пользовательского элемента управления или наследуемого элемента управления, это можно также сделать путем переопределения <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="231a8-119">If you want to provide a custom graphical interface to a user control or an inherited control, you can also do so by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="231a8-120">Ниже приведен пример:</span><span class="sxs-lookup"><span data-stu-id="231a8-120">An example is shown below:</span></span>  
  
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
  
 <span data-ttu-id="231a8-121">Предыдущий пример демонстрирует отрисовки элемента управления с очень простой графическое представление.</span><span class="sxs-lookup"><span data-stu-id="231a8-121">The preceding example demonstrates how to render a control with a very simple graphical representation.</span></span> <span data-ttu-id="231a8-122">Он вызывает <xref:System.Windows.Forms.Control.OnPaint%2A> метод базового класса, он создает <xref:System.Drawing.Pen> объекта для рисования, и наконец рисуется эллипс в прямоугольнике, определяется <xref:System.Windows.Forms.Control.Location%2A> и <xref:System.Windows.Forms.Control.Size%2A> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="231a8-122">It calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class, it creates a <xref:System.Drawing.Pen> object with which to draw, and finally draws an ellipse in the rectangle determined by the <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Size%2A> of the control.</span></span> <span data-ttu-id="231a8-123">Несмотря на то, что большая часть кода отрисовки будет намного более сложным, в этом примере демонстрируется использование <xref:System.Drawing.Graphics> объект, содержащийся в <xref:System.Windows.Forms.PaintEventArgs> объекта.</span><span class="sxs-lookup"><span data-stu-id="231a8-123">Although most rendering code will be significantly more complicated than this, this example demonstrates the use of the <xref:System.Drawing.Graphics> object contained within the <xref:System.Windows.Forms.PaintEventArgs> object.</span></span> <span data-ttu-id="231a8-124">Обратите внимание, что если вы наследуете от класса, который уже имеет графическое представление, например <xref:System.Windows.Forms.UserControl> или <xref:System.Windows.Forms.Button>и не хотите включить это представление в рендеринг, не следует вызывать базовый класс <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="231a8-124">Note that if you are inheriting from a class that already has a graphical representation, such as <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Button>, and you do not wish to incorporate that representation into your rendering, you should not call your base class's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
 <span data-ttu-id="231a8-125">Код в <xref:System.Windows.Forms.Control.OnPaint%2A> метод вашего элемента управления будет выполняться при первом рисовании элемента управления, и каждый раз, когда произойдет его обновление.</span><span class="sxs-lookup"><span data-stu-id="231a8-125">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="231a8-126">Чтобы убедиться, что элемент управления перерисовывается при каждом изменении его размера, добавьте следующую строку в конструктор элемента управления:</span><span class="sxs-lookup"><span data-stu-id="231a8-126">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
>  <span data-ttu-id="231a8-127">Используйте <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> свойство для реализации непрямоугольных управления.</span><span class="sxs-lookup"><span data-stu-id="231a8-127">Use the <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> property to implement a non-rectangular control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="231a8-128">См. также</span><span class="sxs-lookup"><span data-stu-id="231a8-128">See also</span></span>

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [<span data-ttu-id="231a8-129">Практическое руководство. Создание объектов Graphics для рисования</span><span class="sxs-lookup"><span data-stu-id="231a8-129">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="231a8-130">Составные элементы управления</span><span class="sxs-lookup"><span data-stu-id="231a8-130">Constituent Controls</span></span>](constituent-controls.md)
- [<span data-ttu-id="231a8-131">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="231a8-131">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
