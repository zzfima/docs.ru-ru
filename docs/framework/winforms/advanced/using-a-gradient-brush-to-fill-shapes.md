---
title: Заливка фигур с помощью градиентной кисти
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 5771aaabd283d71f5fa6934f86a1c24a57f38dca
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704392"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a><span data-ttu-id="5f0f0-102">Заливка фигур с помощью градиентной кисти</span><span class="sxs-lookup"><span data-stu-id="5f0f0-102">Using a Gradient Brush to Fill Shapes</span></span>
<span data-ttu-id="5f0f0-103">Можно использовать градиентной кисти для заливки фигуры плавно меняющимся цветом.</span><span class="sxs-lookup"><span data-stu-id="5f0f0-103">You can use a gradient brush to fill a shape with a gradually changing color.</span></span> <span data-ttu-id="5f0f0-104">Например можно использовать горизонтальный градиент для заливки фигуры цветом, постепенно переходя от левого края фигуры по правому краю.</span><span class="sxs-lookup"><span data-stu-id="5f0f0-104">For example, you can use a horizontal gradient to fill a shape with color that changes gradually as you move from the left edge of the shape to the right edge.</span></span> <span data-ttu-id="5f0f0-105">Представьте себе прямоугольник с левого края, черный (представленное красного, зеленого и синего компонентов 0, 0, 0) и правым краем red (представленное 255, 0, 0).</span><span class="sxs-lookup"><span data-stu-id="5f0f0-105">Imagine a rectangle with a left edge that is black (represented by red, green, and blue components 0, 0, 0) and a right edge that is red (represented by 255, 0, 0).</span></span> <span data-ttu-id="5f0f0-106">Если прямоугольника равна 256 пикселей в ширину, красный компонент произвольной точки будет больше, чем красный компонент пикселя слева.</span><span class="sxs-lookup"><span data-stu-id="5f0f0-106">If the rectangle is 256 pixels wide, the red component of a given pixel will be one greater than the red component of the pixel to its left.</span></span> <span data-ttu-id="5f0f0-107">Крайнего левого пикселя в строке имеет компонентов цвета (0, 0, 0), вторая — (1, 0, 0), третья — (2, 0, 0) и так далее, пока не дойдете до крайней правой точки, который состоит из компонентов цвета (255, 0, 0).</span><span class="sxs-lookup"><span data-stu-id="5f0f0-107">The leftmost pixel in a row has color components (0, 0, 0), the second pixel has (1, 0, 0), the third pixel has (2, 0, 0), and so on, until you get to the rightmost pixel, which has color components (255, 0, 0).</span></span> <span data-ttu-id="5f0f0-108">Эти интерполированные значения цветовых составляют цветового градиента.</span><span class="sxs-lookup"><span data-stu-id="5f0f0-108">These interpolated color values make up the color gradient.</span></span>  
  
 <span data-ttu-id="5f0f0-109">Линейный градиент изменяет цвет при перемещении по горизонтали, вертикали и параллельно некоторой указанной линии.</span><span class="sxs-lookup"><span data-stu-id="5f0f0-109">A linear gradient changes color as you move horizontally, vertically, or parallel to a specified slanted line.</span></span> <span data-ttu-id="5f0f0-110">Градиента вдоль контура изменяет цвет при перемещении по внутренней части и границы пути.</span><span class="sxs-lookup"><span data-stu-id="5f0f0-110">A path gradient changes color as you move about the interior and boundary of a path.</span></span> <span data-ttu-id="5f0f0-111">Вы можете настроить градиенты контура для достижения разнообразных эффектов.</span><span class="sxs-lookup"><span data-stu-id="5f0f0-111">You can customize path gradients to achieve a wide variety of effects.</span></span>  
  
 <span data-ttu-id="5f0f0-112">Ниже показан прямоугольник заполняется кисти линейного градиента и эллипс, заполненный кисти градиента контура.</span><span class="sxs-lookup"><span data-stu-id="5f0f0-112">The following illustration shows a rectangle filled with a linear gradient brush and an ellipse filled with a path gradient brush.</span></span>  
  
 <span data-ttu-id="5f0f0-113">![Градиента](./media/gradient2.png "gradient2")</span><span class="sxs-lookup"><span data-stu-id="5f0f0-113">![Gradient](./media/gradient2.png "gradient2")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5f0f0-114">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="5f0f0-114">In This Section</span></span>  
 [<span data-ttu-id="5f0f0-115">Практическое руководство. Создание линейного градиента</span><span class="sxs-lookup"><span data-stu-id="5f0f0-115">How to: Create a Linear Gradient</span></span>](how-to-create-a-linear-gradient.md)  
 <span data-ttu-id="5f0f0-116">Показано, как создать линейный градиент с помощью <xref:System.Drawing.Drawing2D.LinearGradientBrush> класса.</span><span class="sxs-lookup"><span data-stu-id="5f0f0-116">Shows how to create a linear gradient using the <xref:System.Drawing.Drawing2D.LinearGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="5f0f0-117">Практическое руководство. Создание градиента вдоль контура</span><span class="sxs-lookup"><span data-stu-id="5f0f0-117">How to: Create a Path Gradient</span></span>](how-to-create-a-path-gradient.md)  
 <span data-ttu-id="5f0f0-118">Описывает создание градиента контура с помощью <xref:System.Drawing.Drawing2D.PathGradientBrush> класса.</span><span class="sxs-lookup"><span data-stu-id="5f0f0-118">Describes how to create a path gradient using the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="5f0f0-119">Практическое руководство. Применение гамма-коррекции к градиенту</span><span class="sxs-lookup"><span data-stu-id="5f0f0-119">How to: Apply Gamma Correction to a Gradient</span></span>](how-to-apply-gamma-correction-to-a-gradient.md)  
 <span data-ttu-id="5f0f0-120">В этой статье описывается использование гамма-коррекция с градиентной кисти.</span><span class="sxs-lookup"><span data-stu-id="5f0f0-120">Explains how to use gamma correction with a gradient brush.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5f0f0-121">Ссылка</span><span class="sxs-lookup"><span data-stu-id="5f0f0-121">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="5f0f0-122">Содержит описание этого класса и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="5f0f0-122">Contains a description of this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="5f0f0-123">Содержит описание этого класса и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="5f0f0-123">Contains a description of this class and has links to all of its members.</span></span>
