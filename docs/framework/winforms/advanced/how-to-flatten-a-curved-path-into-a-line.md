---
title: "Практическое руководство. Спрямление участков кривой"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 334fc0fee7166f8f8c5c1db61d3b9e370da72f87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="5ce0c-102">Практическое руководство. Спрямление участков кривой</span><span class="sxs-lookup"><span data-stu-id="5ce0c-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="5ce0c-103">Объект <xref:System.Drawing.Drawing2D.GraphicsPath> объект хранит последовательности линий и сплайнов Безье.</span><span class="sxs-lookup"><span data-stu-id="5ce0c-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="5ce0c-104">Можно добавить различные типы кривых (эллипсы, дуги, фундаментальные сплайны) с путем, но каждая кривая преобразуется в сплайн Безье перед сохранением в пути.</span><span class="sxs-lookup"><span data-stu-id="5ce0c-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="5ce0c-105">Спрямление контура заключается в преобразовании всех сплайнов Безье в пути в последовательность прямых линий.</span><span class="sxs-lookup"><span data-stu-id="5ce0c-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="5ce0c-106">На следующем рисунке путь до и после выравнивания.</span><span class="sxs-lookup"><span data-stu-id="5ce0c-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="5ce0c-107">![Прямые линии и кривые](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="5ce0c-107">![Straight Lines and Curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="5ce0c-108">Спрямление контура</span><span class="sxs-lookup"><span data-stu-id="5ce0c-108">To Flatten a Path</span></span>  
  
-   <span data-ttu-id="5ce0c-109">Вызовите <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> метод <xref:System.Drawing.Drawing2D.GraphicsPath> объекта.</span><span class="sxs-lookup"><span data-stu-id="5ce0c-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="5ce0c-110"><xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> Метод получает спрямления аргумент, который указывает максимальное расстояние между плоский пути и исходный путь.</span><span class="sxs-lookup"><span data-stu-id="5ce0c-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ce0c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="5ce0c-111">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 [<span data-ttu-id="5ce0c-112">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="5ce0c-112">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="5ce0c-113">Построение и рисование контуров</span><span class="sxs-lookup"><span data-stu-id="5ce0c-113">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
