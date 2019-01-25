---
title: Как выполнить Набор толщины и выравнивания пера
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
ms.openlocfilehash: d1a465fb7c1cd6d4064a077e592daefebf590714
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564829"
---
# <a name="how-to-set-pen-width-and-alignment"></a><span data-ttu-id="9288a-102">Как выполнить Набор толщины и выравнивания пера</span><span class="sxs-lookup"><span data-stu-id="9288a-102">How to: Set Pen Width and Alignment</span></span>
<span data-ttu-id="9288a-103">При создании <xref:System.Drawing.Pen>, указать толщину пера в качестве одного из аргументов конструктора.</span><span class="sxs-lookup"><span data-stu-id="9288a-103">When you create a <xref:System.Drawing.Pen>, you can supply the pen width as one of the arguments to the constructor.</span></span> <span data-ttu-id="9288a-104">Можно также изменить ширину пера <xref:System.Drawing.Pen.Width%2A> свойство <xref:System.Drawing.Pen> класса.</span><span class="sxs-lookup"><span data-stu-id="9288a-104">You can also change the pen width with the <xref:System.Drawing.Pen.Width%2A> property of the <xref:System.Drawing.Pen> class.</span></span>  
  
 <span data-ttu-id="9288a-105">Теоретической линии имеет ширину 0.</span><span class="sxs-lookup"><span data-stu-id="9288a-105">A theoretical line has a width of 0.</span></span> <span data-ttu-id="9288a-106">При рисовании линии, одну точку, пиксели центрируются по теоретической линии.</span><span class="sxs-lookup"><span data-stu-id="9288a-106">When you draw a line that is 1 pixel wide, the pixels are centered on the theoretical line.</span></span> <span data-ttu-id="9288a-107">Если нарисовать линию, является более чем одному пикселю, пиксели либо центрируются по теоретической линии появятся или к одной стороне от теоретической линии.</span><span class="sxs-lookup"><span data-stu-id="9288a-107">If you draw a line that is more than one pixel wide, the pixels are either centered on the theoretical line or appear to one side of the theoretical line.</span></span> <span data-ttu-id="9288a-108">Можно задать свойство выравнивания из <xref:System.Drawing.Pen> чтобы определить положение точек, рисуемых при помощи этого пера по отношению к теоретической линии.</span><span class="sxs-lookup"><span data-stu-id="9288a-108">You can set the pen alignment property of a <xref:System.Drawing.Pen> to determine how the pixels drawn with that pen will be positioned relative to theoretical lines.</span></span>  
  
 <span data-ttu-id="9288a-109">Значения <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, и <xref:System.Drawing.Drawing2D.PenAlignment.Inset> , отображаемые в следующих примерах кода являются членами <xref:System.Drawing.Drawing2D.PenAlignment> перечисления.</span><span class="sxs-lookup"><span data-stu-id="9288a-109">The values <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, and <xref:System.Drawing.Drawing2D.PenAlignment.Inset> that appear in the following code examples are members of the <xref:System.Drawing.Drawing2D.PenAlignment> enumeration.</span></span>  
  
 <span data-ttu-id="9288a-110">В следующем примере кода рисует линию дважды: один раз черным пером толщиной в 1 и один раз с помощью зеленого пера шириной 10.</span><span class="sxs-lookup"><span data-stu-id="9288a-110">The following code example draws a line twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
### <a name="to-vary-the-width-of-a-pen"></a><span data-ttu-id="9288a-111">Для изменения ширины пера</span><span class="sxs-lookup"><span data-stu-id="9288a-111">To vary the width of a pen</span></span>  
  
-   <span data-ttu-id="9288a-112">Установите для параметра <xref:System.Drawing.Pen.Alignment%2A> свойства <xref:System.Drawing.Drawing2D.PenAlignment.Center> (по умолчанию) будет что рисование зеленым пером пикселей по теоретической линии.</span><span class="sxs-lookup"><span data-stu-id="9288a-112">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> (the default) to specify that pixels drawn with the green pen will be centered on the theoretical line.</span></span> <span data-ttu-id="9288a-113">Ниже показан итоговый строки.</span><span class="sxs-lookup"><span data-stu-id="9288a-113">The following illustration shows the resulting line.</span></span>  
  
     <span data-ttu-id="9288a-114">![Перья](../../../../docs/framework/winforms/advanced/media/pens1a.gif "pens1A")</span><span class="sxs-lookup"><span data-stu-id="9288a-114">![Pens](../../../../docs/framework/winforms/advanced/media/pens1a.gif "pens1A")</span></span>  
  
     <span data-ttu-id="9288a-115">В следующем примере рисуется прямоугольник дважды: один раз черным пером толщиной в 1 и один раз с помощью зеленого пера шириной 10.</span><span class="sxs-lookup"><span data-stu-id="9288a-115">The following code example draws a rectangle twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a><span data-ttu-id="9288a-116">Изменение выравнивания пера</span><span class="sxs-lookup"><span data-stu-id="9288a-116">To change the alignment of a pen</span></span>  
  
-   <span data-ttu-id="9288a-117">Установите для параметра <xref:System.Drawing.Pen.Alignment%2A> свойства <xref:System.Drawing.Drawing2D.PenAlignment.Center> будет что рисование зеленым пером пикселей по границ прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="9288a-117">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> to specify that the pixels drawn with the green pen will be centered on the boundary of the rectangle.</span></span>  
  
     <span data-ttu-id="9288a-118">На следующем рисунке показан полученный прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="9288a-118">The following illustration shows the resulting rectangle.</span></span>  
  
     <span data-ttu-id="9288a-119">![Перья](../../../../docs/framework/winforms/advanced/media/pens2.gif "pens2")</span><span class="sxs-lookup"><span data-stu-id="9288a-119">![Pens](../../../../docs/framework/winforms/advanced/media/pens2.gif "pens2")</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a><span data-ttu-id="9288a-120">Для создания вложенного пера</span><span class="sxs-lookup"><span data-stu-id="9288a-120">To create an inset pen</span></span>  
  
-   <span data-ttu-id="9288a-121">Измените выравнивание зеленого пера, изменив третья инструкция в предыдущем примере кода следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9288a-121">Change the green pen's alignment by modifying the third statement in the preceding code example as follows:</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     <span data-ttu-id="9288a-122">Теперь пикселов в ширину зеленая линия отображаются внутри прямоугольника, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="9288a-122">Now the pixels in the wide green line appear on the inside of the rectangle as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="9288a-123">![Перья](../../../../docs/framework/winforms/advanced/media/pens3.gif "pens3")</span><span class="sxs-lookup"><span data-stu-id="9288a-123">![Pens](../../../../docs/framework/winforms/advanced/media/pens3.gif "pens3")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9288a-124">См. также</span><span class="sxs-lookup"><span data-stu-id="9288a-124">See also</span></span>
- [<span data-ttu-id="9288a-125">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="9288a-125">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="9288a-126">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9288a-126">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
