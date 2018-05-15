---
title: Построение и рисование контуров
ms.date: 03/30/2017
helpviewer_keywords:
- paths [Windows Forms], drawing
- drawing paths [Windows Forms]
- graphics paths [Windows Forms], creating
- graphics paths [Windows Forms], drawing
- examples [Windows Forms], drawing paths
ms.assetid: f16ec921-56cf-46d1-9741-d7316ad06b23
ms.openlocfilehash: 120bb3edcf8e35feca37f02dda5148ba4eebd0ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="constructing-and-drawing-paths"></a><span data-ttu-id="5c4d9-102">Построение и рисование контуров</span><span class="sxs-lookup"><span data-stu-id="5c4d9-102">Constructing and Drawing Paths</span></span>
<span data-ttu-id="5c4d9-103">Путь — это последовательность графических примитивов (линии, прямоугольники, кривых, текста и т. д.), которые обрабатываются и отображаются как один объект.</span><span class="sxs-lookup"><span data-stu-id="5c4d9-103">A path is a sequence of graphics primitives (lines, rectangles, curves, text, and the like) that can be manipulated and drawn as a single unit.</span></span> <span data-ttu-id="5c4d9-104">Путь можно разделить на *фигур* , открытые или закрытые.</span><span class="sxs-lookup"><span data-stu-id="5c4d9-104">A path can be divided into *figures* that are either open or closed.</span></span> <span data-ttu-id="5c4d9-105">Фигура может содержать несколько примитивов.</span><span class="sxs-lookup"><span data-stu-id="5c4d9-105">A figure can contain several primitives.</span></span>  
  
 <span data-ttu-id="5c4d9-106">Контур можно нарисовать путем вызова <xref:System.Drawing.Graphics.DrawPath%2A> метод <xref:System.Drawing.Graphics> класса и Заливка контура, вызвав <xref:System.Drawing.Graphics.FillPath%2A> метод <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="5c4d9-106">You can draw a path by calling the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class, and you can fill a path by calling the <xref:System.Drawing.Graphics.FillPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5c4d9-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="5c4d9-107">In This Section</span></span>  
 [<span data-ttu-id="5c4d9-108">Практическое руководство. Создание изображений из прямых и кривых линий и геометрических фигур</span><span class="sxs-lookup"><span data-stu-id="5c4d9-108">How to: Create Figures from Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-figures-from-lines-curves-and-shapes.md)  
 <span data-ttu-id="5c4d9-109">Показано, как использовать <xref:System.Drawing.Drawing2D.GraphicsPath> для создания фигур.</span><span class="sxs-lookup"><span data-stu-id="5c4d9-109">Shows how to use a <xref:System.Drawing.Drawing2D.GraphicsPath> to create figures.</span></span>  
  
 [<span data-ttu-id="5c4d9-110">Практическое руководство. Заливка открытых фигур</span><span class="sxs-lookup"><span data-stu-id="5c4d9-110">How to: Fill Open Figures</span></span>](../../../../docs/framework/winforms/advanced/how-to-fill-open-figures.md)  
 <span data-ttu-id="5c4d9-111">Заливка <xref:System.Drawing.Drawing2D.GraphicsPath>.</span><span class="sxs-lookup"><span data-stu-id="5c4d9-111">Explains how to fill a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
 [<span data-ttu-id="5c4d9-112">Практическое руководство. Спрямление участков кривой</span><span class="sxs-lookup"><span data-stu-id="5c4d9-112">How to: Flatten a Curved Path into a Line</span></span>](../../../../docs/framework/winforms/advanced/how-to-flatten-a-curved-path-into-a-line.md)  
 <span data-ttu-id="5c4d9-113">Спрямление <xref:System.Drawing.Drawing2D.GraphicsPath>.</span><span class="sxs-lookup"><span data-stu-id="5c4d9-113">Shows how to flatten a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5c4d9-114">Ссылка</span><span class="sxs-lookup"><span data-stu-id="5c4d9-114">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 <span data-ttu-id="5c4d9-115">Описывает данный класс и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="5c4d9-115">Describes this class and contains links to all of its members.</span></span>
