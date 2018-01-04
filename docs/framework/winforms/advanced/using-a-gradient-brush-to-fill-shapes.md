---
title: "Заливка фигур с помощью градиентной кисти"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a84a68f9082d00559938c2710b6574690fa6ab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a><span data-ttu-id="3b9c0-102">Заливка фигур с помощью градиентной кисти</span><span class="sxs-lookup"><span data-stu-id="3b9c0-102">Using a Gradient Brush to Fill Shapes</span></span>
<span data-ttu-id="3b9c0-103">Можно использовать градиентной кисти для заливки фигуры плавно меняющимся цветом.</span><span class="sxs-lookup"><span data-stu-id="3b9c0-103">You can use a gradient brush to fill a shape with a gradually changing color.</span></span> <span data-ttu-id="3b9c0-104">Например можно использовать горизонтальный градиент для заливки фигуры цвет, который постепенно при переходе от левого края фигуры по правому краю.</span><span class="sxs-lookup"><span data-stu-id="3b9c0-104">For example, you can use a horizontal gradient to fill a shape with color that changes gradually as you move from the left edge of the shape to the right edge.</span></span> <span data-ttu-id="3b9c0-105">Примером может послужить прямоугольник с черным левым краем (представленным красного, зеленого и синего компонентов 0, 0, 0) и правым краем красный (представленным 255, 0, 0).</span><span class="sxs-lookup"><span data-stu-id="3b9c0-105">Imagine a rectangle with a left edge that is black (represented by red, green, and blue components 0, 0, 0) and a right edge that is red (represented by 255, 0, 0).</span></span> <span data-ttu-id="3b9c0-106">Если прямоугольника равна 256 пикселей в ширину, красный компонент произвольной точки будет больше, чем красный компонент пикселя слева от него.</span><span class="sxs-lookup"><span data-stu-id="3b9c0-106">If the rectangle is 256 pixels wide, the red component of a given pixel will be one greater than the red component of the pixel to its left.</span></span> <span data-ttu-id="3b9c0-107">Самый левый пиксель в строке имеет компоненты цвета (0, 0, 0), вторая (1, 0, 0), либо третья — (2, 0, 0) и т. д., пока не дойдете до крайней правой точки, который имеет компоненты цвета (255, 0, 0).</span><span class="sxs-lookup"><span data-stu-id="3b9c0-107">The leftmost pixel in a row has color components (0, 0, 0), the second pixel has (1, 0, 0), the third pixel has (2, 0, 0), and so on, until you get to the rightmost pixel, which has color components (255, 0, 0).</span></span> <span data-ttu-id="3b9c0-108">Эти интерполированные значения цветовых составляют цветового градиента.</span><span class="sxs-lookup"><span data-stu-id="3b9c0-108">These interpolated color values make up the color gradient.</span></span>  
  
 <span data-ttu-id="3b9c0-109">Линейный градиент меняет цвет по мере перемещения по горизонтали, по вертикали или параллельно некоторой указанной линии.</span><span class="sxs-lookup"><span data-stu-id="3b9c0-109">A linear gradient changes color as you move horizontally, vertically, or parallel to a specified slanted line.</span></span> <span data-ttu-id="3b9c0-110">Градиент контура меняет цвет при перемещении по внутренней части и границы пути.</span><span class="sxs-lookup"><span data-stu-id="3b9c0-110">A path gradient changes color as you move about the interior and boundary of a path.</span></span> <span data-ttu-id="3b9c0-111">Вы можете настроить градиенты контура для достижения разнообразных эффектов.</span><span class="sxs-lookup"><span data-stu-id="3b9c0-111">You can customize path gradients to achieve a wide variety of effects.</span></span>  
  
 <span data-ttu-id="3b9c0-112">На следующем рисунке прямоугольник с кисти линейного градиента эллипса заливке а кисти градиента вдоль пути.</span><span class="sxs-lookup"><span data-stu-id="3b9c0-112">The following illustration shows a rectangle filled with a linear gradient brush and an ellipse filled with a path gradient brush.</span></span>  
  
 <span data-ttu-id="3b9c0-113">![Градиент](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")</span><span class="sxs-lookup"><span data-stu-id="3b9c0-113">![Gradient](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3b9c0-114">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="3b9c0-114">In This Section</span></span>  
 [<span data-ttu-id="3b9c0-115">Практическое руководство. Создание линейного градиента</span><span class="sxs-lookup"><span data-stu-id="3b9c0-115">How to: Create a Linear Gradient</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-linear-gradient.md)  
 <span data-ttu-id="3b9c0-116">Показано, как создать линейный градиент с помощью <xref:System.Drawing.Drawing2D.LinearGradientBrush> класса.</span><span class="sxs-lookup"><span data-stu-id="3b9c0-116">Shows how to create a linear gradient using the <xref:System.Drawing.Drawing2D.LinearGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="3b9c0-117">Практическое руководство. Создание градиента вдоль контура</span><span class="sxs-lookup"><span data-stu-id="3b9c0-117">How to: Create a Path Gradient</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-path-gradient.md)  
 <span data-ttu-id="3b9c0-118">Описывает, как создать градиента пути с помощью <xref:System.Drawing.Drawing2D.PathGradientBrush> класса.</span><span class="sxs-lookup"><span data-stu-id="3b9c0-118">Describes how to create a path gradient using the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="3b9c0-119">Практическое руководство. Применение гамма-коррекции к градиенту</span><span class="sxs-lookup"><span data-stu-id="3b9c0-119">How to: Apply Gamma Correction to a Gradient</span></span>](../../../../docs/framework/winforms/advanced/how-to-apply-gamma-correction-to-a-gradient.md)  
 <span data-ttu-id="3b9c0-120">Описание способов использования гамма-коррекция с градиентной кисти.</span><span class="sxs-lookup"><span data-stu-id="3b9c0-120">Explains how to use gamma correction with a gradient brush.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3b9c0-121">Ссылка</span><span class="sxs-lookup"><span data-stu-id="3b9c0-121">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="3b9c0-122">Содержит описание этого класса и ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="3b9c0-122">Contains a description of this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="3b9c0-123">Содержит описание этого класса и ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="3b9c0-123">Contains a description of this class and has links to all of its members.</span></span>
