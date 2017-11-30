---
title: "Практическое руководство. Задание толщины и выравнивания пера"
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
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6ed2a28c49554c686abb5e2635ab35b746b83465
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-pen-width-and-alignment"></a><span data-ttu-id="b8906-102">Практическое руководство. Задание толщины и выравнивания пера</span><span class="sxs-lookup"><span data-stu-id="b8906-102">How to: Set Pen Width and Alignment</span></span>
<span data-ttu-id="b8906-103">При создании <xref:System.Drawing.Pen>, указать толщину пера в качестве одного из аргументов конструктора.</span><span class="sxs-lookup"><span data-stu-id="b8906-103">When you create a <xref:System.Drawing.Pen>, you can supply the pen width as one of the arguments to the constructor.</span></span> <span data-ttu-id="b8906-104">Можно также изменить ширину пера <xref:System.Drawing.Pen.Width%2A> свойство <xref:System.Drawing.Pen> класса.</span><span class="sxs-lookup"><span data-stu-id="b8906-104">You can also change the pen width with the <xref:System.Drawing.Pen.Width%2A> property of the <xref:System.Drawing.Pen> class.</span></span>  
  
 <span data-ttu-id="b8906-105">Абстрактная линия имеет ширину 0.</span><span class="sxs-lookup"><span data-stu-id="b8906-105">A theoretical line has a width of 0.</span></span> <span data-ttu-id="b8906-106">При рисовании линии толщиной в одну точку точки центрируются по абстрактной линии.</span><span class="sxs-lookup"><span data-stu-id="b8906-106">When you draw a line that is 1 pixel wide, the pixels are centered on the theoretical line.</span></span> <span data-ttu-id="b8906-107">Если нарисовать линии более чем одному пикселю пиксели либо центрируются по абстрактной линии или отображаться к одной стороне абстрактной линии.</span><span class="sxs-lookup"><span data-stu-id="b8906-107">If you draw a line that is more than one pixel wide, the pixels are either centered on the theoretical line or appear to one side of the theoretical line.</span></span> <span data-ttu-id="b8906-108">Можно установить свойство выравнивания пера <xref:System.Drawing.Pen> для определяют расположение точек, рисуемых пером, относительно абстрактной линии.</span><span class="sxs-lookup"><span data-stu-id="b8906-108">You can set the pen alignment property of a <xref:System.Drawing.Pen> to determine how the pixels drawn with that pen will be positioned relative to theoretical lines.</span></span>  
  
 <span data-ttu-id="b8906-109">Значения <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, и <xref:System.Drawing.Drawing2D.PenAlignment.Inset> , отображаемые в следующих примерах кода являются членами <xref:System.Drawing.Drawing2D.PenAlignment> перечисления.</span><span class="sxs-lookup"><span data-stu-id="b8906-109">The values <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, and <xref:System.Drawing.Drawing2D.PenAlignment.Inset> that appear in the following code examples are members of the <xref:System.Drawing.Drawing2D.PenAlignment> enumeration.</span></span>  
  
 <span data-ttu-id="b8906-110">В следующем примере кода проводит линию дважды: один раз черным пером толщиной в 1 и один раз с помощью зеленого пера шириной 10.</span><span class="sxs-lookup"><span data-stu-id="b8906-110">The following code example draws a line twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
### <a name="to-vary-the-width-of-a-pen"></a><span data-ttu-id="b8906-111">Чтобы изменять ширину пера</span><span class="sxs-lookup"><span data-stu-id="b8906-111">To vary the width of a pen</span></span>  
  
-   <span data-ttu-id="b8906-112">Установите для параметра <xref:System.Drawing.Pen.Alignment%2A> свойства <xref:System.Drawing.Drawing2D.PenAlignment.Center> (по умолчанию) для указания, что будет по центру точек, рисуемых зеленым пером, по абстрактной линии.</span><span class="sxs-lookup"><span data-stu-id="b8906-112">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> (the default) to specify that pixels drawn with the green pen will be centered on the theoretical line.</span></span> <span data-ttu-id="b8906-113">На следующем рисунке результирующей строки.</span><span class="sxs-lookup"><span data-stu-id="b8906-113">The following illustration shows the resulting line.</span></span>  
  
     <span data-ttu-id="b8906-114">![Перья](../../../../docs/framework/winforms/advanced/media/pens1a.gif "pens1A")</span><span class="sxs-lookup"><span data-stu-id="b8906-114">![Pens](../../../../docs/framework/winforms/advanced/media/pens1a.gif "pens1A")</span></span>  
  
     <span data-ttu-id="b8906-115">В следующем примере рисуется прямоугольник дважды: один раз черным пером толщиной в 1 и один раз с помощью зеленого пера шириной 10.</span><span class="sxs-lookup"><span data-stu-id="b8906-115">The following code example draws a rectangle twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a><span data-ttu-id="b8906-116">Изменение выравнивания пера</span><span class="sxs-lookup"><span data-stu-id="b8906-116">To change the alignment of a pen</span></span>  
  
-   <span data-ttu-id="b8906-117">Установите для параметра <xref:System.Drawing.Pen.Alignment%2A> свойства <xref:System.Drawing.Drawing2D.PenAlignment.Center> , рисуемые зеленым пером пиксели будет по границе прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="b8906-117">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> to specify that the pixels drawn with the green pen will be centered on the boundary of the rectangle.</span></span>  
  
     <span data-ttu-id="b8906-118">На следующем рисунке полученный прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="b8906-118">The following illustration shows the resulting rectangle.</span></span>  
  
     <span data-ttu-id="b8906-119">![Перья](../../../../docs/framework/winforms/advanced/media/pens2.gif "pens2")</span><span class="sxs-lookup"><span data-stu-id="b8906-119">![Pens](../../../../docs/framework/winforms/advanced/media/pens2.gif "pens2")</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a><span data-ttu-id="b8906-120">Для создания вложенного пера</span><span class="sxs-lookup"><span data-stu-id="b8906-120">To create an inset pen</span></span>  
  
-   <span data-ttu-id="b8906-121">Измените выравнивание зеленого пера, изменив третья инструкция в предыдущем примере кода следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b8906-121">Change the green pen's alignment by modifying the third statement in the preceding code example as follows:</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     <span data-ttu-id="b8906-122">Теперь пикселей в ширину зеленая линия отображаются внутри прямоугольника, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="b8906-122">Now the pixels in the wide green line appear on the inside of the rectangle as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="b8906-123">![Перья](../../../../docs/framework/winforms/advanced/media/pens3.gif "pens3")</span><span class="sxs-lookup"><span data-stu-id="b8906-123">![Pens](../../../../docs/framework/winforms/advanced/media/pens3.gif "pens3")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8906-124">См. также</span><span class="sxs-lookup"><span data-stu-id="b8906-124">See Also</span></span>  
 [<span data-ttu-id="b8906-125">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="b8906-125">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="b8906-126">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b8906-126">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
