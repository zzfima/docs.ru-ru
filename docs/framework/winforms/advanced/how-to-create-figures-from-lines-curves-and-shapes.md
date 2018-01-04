---
title: "Практическое руководство. Создание изображений из прямых и кривых линий и геометрических фигур"
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
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 40520f566beafc83075d0563148b5d0f9bd4fe85
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a><span data-ttu-id="0acf3-102">Практическое руководство. Создание изображений из прямых и кривых линий и геометрических фигур</span><span class="sxs-lookup"><span data-stu-id="0acf3-102">How to: Create Figures from Lines, Curves, and Shapes</span></span>
<span data-ttu-id="0acf3-103">Чтобы создать изображение, построить <xref:System.Drawing.Drawing2D.GraphicsPath>и затем вызывать методы, такие как <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> и <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, для добавления в путь примитивов.</span><span class="sxs-lookup"><span data-stu-id="0acf3-103">To create a figure, construct a <xref:System.Drawing.Drawing2D.GraphicsPath>, and then call methods, such as <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, to add primitives to the path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0acf3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0acf3-104">Example</span></span>  
 <span data-ttu-id="0acf3-105">В следующем примере кода создается контур, фигуры:</span><span class="sxs-lookup"><span data-stu-id="0acf3-105">The following code examples create paths that have figures:</span></span>  
  
-   <span data-ttu-id="0acf3-106">В первом примере создается путь, состоящий из одной фигуры.</span><span class="sxs-lookup"><span data-stu-id="0acf3-106">The first example creates a path that has a single figure.</span></span> <span data-ttu-id="0acf3-107">На рисунке состоит из одного дуги. Дуга имеет угол поворота-180 градусов против часовой стрелки в системе координат по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0acf3-107">The figure consists of a single arc. The arc has a sweep angle of –180 degrees, which is counterclockwise in the default coordinate system.</span></span>  
  
-   <span data-ttu-id="0acf3-108">Во втором примере создается путь, состоящий из двух фигур.</span><span class="sxs-lookup"><span data-stu-id="0acf3-108">The second example creates a path that has two figures.</span></span> <span data-ttu-id="0acf3-109">Первая фигура имеет дугу, за которым следует строка.</span><span class="sxs-lookup"><span data-stu-id="0acf3-109">The first figure is an arc followed by a line.</span></span> <span data-ttu-id="0acf3-110">Вторая фигура представляет собой строку, следуют за строка кривой.</span><span class="sxs-lookup"><span data-stu-id="0acf3-110">The second figure is a line followed by a curve followed by a line.</span></span> <span data-ttu-id="0acf3-111">Первая фигура остается открытым, и второй рисунок закрывается.</span><span class="sxs-lookup"><span data-stu-id="0acf3-111">The first figure is left open, and the second figure is closed.</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0acf3-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0acf3-112">Compiling the Code</span></span>  
 <span data-ttu-id="0acf3-113">Предыдущий пример предназначен для работы с Windows Forms, и требуют <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="0acf3-113">The previous examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0acf3-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0acf3-114">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [<span data-ttu-id="0acf3-115">Построение и рисование контуров</span><span class="sxs-lookup"><span data-stu-id="0acf3-115">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)  
 [<span data-ttu-id="0acf3-116">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="0acf3-116">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
