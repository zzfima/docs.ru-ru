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
# <a name="user-drawn-controls"></a><span data-ttu-id="dacfe-102">Элементы управления, разработанные пользователем</span><span class="sxs-lookup"><span data-stu-id="dacfe-102">User-Drawn Controls</span></span>
<span data-ttu-id="dacfe-103">Платформа .NET Framework предоставляет возможность легко разрабатывать собственные элементы управления.</span><span class="sxs-lookup"><span data-stu-id="dacfe-103">The .NET Framework provides you with the ability to easily develop your own controls.</span></span> <span data-ttu-id="dacfe-104">Можно создать пользовательский элемент управления, который представляет собой набор стандартных элементов управления, связанных с помощью кода, или можно разработать собственный элемент управления с самого начала копирования.</span><span class="sxs-lookup"><span data-stu-id="dacfe-104">You can create a user control, which is a set of standard controls bound together by code, or you can design your own control from the ground up.</span></span> <span data-ttu-id="dacfe-105">Можно даже использовать наследование для создания элемента управления, который наследует от существующего элемента управления и добавить его функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="dacfe-105">You can even use inheritance to create a control that inherits from an existing control and add to its inherent functionality.</span></span> <span data-ttu-id="dacfe-106">Независимо от подхода, .NET Framework обеспечивает возможность создания пользовательского интерфейса для любого элемента управления, создаваемые вами.</span><span class="sxs-lookup"><span data-stu-id="dacfe-106">Whatever approach you use, the .NET Framework provides the functionality to draw a custom graphical interface for any control you create.</span></span>  
  
 <span data-ttu-id="dacfe-107">Рисование элемента управления сопровождается выполнением кода в элементе управления <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="dacfe-107">Painting of a control is accomplished by the execution of code in the control's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="dacfe-108">Единственным аргументом <xref:System.Windows.Forms.Control.OnPaint%2A> метод <xref:System.Windows.Forms.PaintEventArgs> объект, предоставляющий все сведения и функциональные возможности, необходимые для визуализации элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dacfe-108">The single argument of the <xref:System.Windows.Forms.Control.OnPaint%2A> method is a <xref:System.Windows.Forms.PaintEventArgs> object that provides all of the information and functionality required to render your control.</span></span> <span data-ttu-id="dacfe-109"><xref:System.Windows.Forms.PaintEventArgs> Предоставляет два объекта-участника, которые будут использоваться при отрисовке элемента управления в виде свойств:</span><span class="sxs-lookup"><span data-stu-id="dacfe-109">The <xref:System.Windows.Forms.PaintEventArgs> provides as properties two principal objects that will be used in the rendering of your control:</span></span>  
  
-   <span data-ttu-id="dacfe-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>Объект - прямоугольник, представляющий элемент управления, которая будет нарисована.</span><span class="sxs-lookup"><span data-stu-id="dacfe-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object - the rectangle that represents the part of the control that will be drawn.</span></span> <span data-ttu-id="dacfe-111">Это может быть весь элемент управления или элемента управления в зависимости от того, как отображается элемент управления.</span><span class="sxs-lookup"><span data-stu-id="dacfe-111">This can be the entire control, or part of the control depending on how the control is drawn.</span></span>  
  
-   <span data-ttu-id="dacfe-112"><xref:System.Drawing.Graphics>объект - инкапсулирует несколько графических объектов и методов, которые предоставляют функциональные возможности, необходимые для рисования элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dacfe-112"><xref:System.Drawing.Graphics> object - encapsulates several graphics-oriented objects and methods that provide the functionality necessary to draw your control.</span></span>  
  
 <span data-ttu-id="dacfe-113">Дополнительные сведения о <xref:System.Drawing.Graphics> объекта и способах ее использования см. в разделе [как: Создание графических объектов для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="dacfe-113">For more information on the <xref:System.Drawing.Graphics> object and how to use it, see [How to: Create Graphics Objects for Drawing](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
 <span data-ttu-id="dacfe-114"><xref:System.Windows.Forms.Control.OnPaint%2A> Событие каждый раз, когда элемент управления рисуется или обновляется на экране и <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> объект представляет прямоугольник, в котором рисования будет иметь место.</span><span class="sxs-lookup"><span data-stu-id="dacfe-114">The <xref:System.Windows.Forms.Control.OnPaint%2A> event is fired whenever the control is drawn or refreshed on the screen, and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object represents the rectangle in which painting will take place.</span></span> <span data-ttu-id="dacfe-115">Если весь элемент управления должен быть обновлен, <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> будет представлять размер всего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dacfe-115">If the entire control needs to be refreshed, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> will represent the size of the entire control.</span></span> <span data-ttu-id="dacfe-116">Если только часть элемента управления необходимо обновить, однако <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> будет представлять только область, которая должна быть перерисованы.</span><span class="sxs-lookup"><span data-stu-id="dacfe-116">If only part of the control needs to be refreshed, however, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object will represent only the region that needs to be redrawn.</span></span> <span data-ttu-id="dacfe-117">Пример в этом случае может быть, если элемент управления частично закрыт другим элементом управления или формы в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="dacfe-117">An example of such a case would be when a control was partially obscured by another control or form in the user interface.</span></span>  
  
 <span data-ttu-id="dacfe-118">При наследовании от <xref:System.Windows.Forms.Control> , необходимо переопределить <xref:System.Windows.Forms.Control.OnPaint%2A> метод и предоставить код отрисовки графики в пределах.</span><span class="sxs-lookup"><span data-stu-id="dacfe-118">When inheriting from the <xref:System.Windows.Forms.Control> class, you must override the <xref:System.Windows.Forms.Control.OnPaint%2A> method and provide graphics-rendering code within.</span></span> <span data-ttu-id="dacfe-119">Если вы хотите предоставить пользовательский элемент управления или элемент управления пользовательского интерфейса, это можно также сделать путем переопределения <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="dacfe-119">If you want to provide a custom graphical interface to a user control or an inherited control, you can also do so by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="dacfe-120">Ниже показан пример:</span><span class="sxs-lookup"><span data-stu-id="dacfe-120">An example is shown below:</span></span>  
  
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
  
 <span data-ttu-id="dacfe-121">В предыдущем примере показано, как для отображения элемента управления с очень простым графическим представлением.</span><span class="sxs-lookup"><span data-stu-id="dacfe-121">The preceding example demonstrates how to render a control with a very simple graphical representation.</span></span> <span data-ttu-id="dacfe-122">Он вызывает <xref:System.Windows.Forms.Control.OnPaint%2A> метод базового класса, он создает <xref:System.Drawing.Pen> для рисования объектов, и наконец определяется рисуется эллипс в прямоугольнике <xref:System.Windows.Forms.Control.Location%2A> и <xref:System.Windows.Forms.Control.Size%2A> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dacfe-122">It calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class, it creates a <xref:System.Drawing.Pen> object with which to draw, and finally draws an ellipse in the rectangle determined by the <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Size%2A> of the control.</span></span> <span data-ttu-id="dacfe-123">Несмотря на то, что большая часть кода отрисовки будет намного более сложным, в этом примере показано использование функции <xref:System.Drawing.Graphics> объект, содержащийся в <xref:System.Windows.Forms.PaintEventArgs> объекта.</span><span class="sxs-lookup"><span data-stu-id="dacfe-123">Although most rendering code will be significantly more complicated than this, this example demonstrates the use of the <xref:System.Drawing.Graphics> object contained within the <xref:System.Windows.Forms.PaintEventArgs> object.</span></span> <span data-ttu-id="dacfe-124">Обратите внимание, что если наследуются от класса, который уже имеет графическое представление, например <xref:System.Windows.Forms.UserControl> или <xref:System.Windows.Forms.Button>и необходимо включить это представление в отрисовку, не следует вызывать базовый класс <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="dacfe-124">Note that if you are inheriting from a class that already has a graphical representation, such as <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Button>, and you do not wish to incorporate that representation into your rendering, you should not call your base class's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
 <span data-ttu-id="dacfe-125">Код в <xref:System.Windows.Forms.Control.OnPaint%2A> метод элемента управления будет выполняться при первом рисовании элемента управления, и при его обновлении.</span><span class="sxs-lookup"><span data-stu-id="dacfe-125">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="dacfe-126">Чтобы убедиться, что элемент управления перерисовывается при каждом изменении его размера, конструктор элемента управления добавьте следующую строку:</span><span class="sxs-lookup"><span data-stu-id="dacfe-126">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
>  <span data-ttu-id="dacfe-127">Используйте <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> свойство для реализации нестандартной управления.</span><span class="sxs-lookup"><span data-stu-id="dacfe-127">Use the <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> property to implement a non-rectangular control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dacfe-128">См. также</span><span class="sxs-lookup"><span data-stu-id="dacfe-128">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Region%2A>  
 <xref:System.Windows.Forms.ControlStyles>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Windows.Forms.PaintEventArgs>  
 [<span data-ttu-id="dacfe-129">Практическое руководство. Создание графических объектов для рисования</span><span class="sxs-lookup"><span data-stu-id="dacfe-129">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="dacfe-130">Составные элементы управления</span><span class="sxs-lookup"><span data-stu-id="dacfe-130">Constituent Controls</span></span>](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 [<span data-ttu-id="dacfe-131">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="dacfe-131">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
