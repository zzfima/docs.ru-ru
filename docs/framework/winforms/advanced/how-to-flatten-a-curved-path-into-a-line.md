---
title: Как выполнить Сведение изогнутого пути в строку
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: aa47a655417cdf82d79fb222dc6ff6f6d8c3a947
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601822"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="a8799-102">Как выполнить Сведение изогнутого пути в строку</span><span class="sxs-lookup"><span data-stu-id="a8799-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="a8799-103">Объект <xref:System.Drawing.Drawing2D.GraphicsPath> объект хранит последовательность, линий и сплайнов Безье.</span><span class="sxs-lookup"><span data-stu-id="a8799-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="a8799-104">Различные типы кривых (эллипсы, дуги, фундаментальные сплайны) можно добавить в путь, но каждую кривую преобразуется в кривую Безье, перед его сохранением в пути.</span><span class="sxs-lookup"><span data-stu-id="a8799-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="a8799-105">Спрямление путь заключается в преобразовании всех сплайнов Безье в пути в последовательность прямых линий.</span><span class="sxs-lookup"><span data-stu-id="a8799-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="a8799-106">Ниже показан путь до и после выравнивания.</span><span class="sxs-lookup"><span data-stu-id="a8799-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="a8799-107">![Прямые линии и кривые](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="a8799-107">![Straight Lines and Curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="a8799-108">Спрямление контура</span><span class="sxs-lookup"><span data-stu-id="a8799-108">To Flatten a Path</span></span>  
  
-   <span data-ttu-id="a8799-109">Вызовите <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> метод <xref:System.Drawing.Drawing2D.GraphicsPath> объекта.</span><span class="sxs-lookup"><span data-stu-id="a8799-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="a8799-110"><xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> Метод получает аргумент спрямления, который указывает максимальное расстояние между уплощенный путь и исходный путь.</span><span class="sxs-lookup"><span data-stu-id="a8799-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8799-111">См. также</span><span class="sxs-lookup"><span data-stu-id="a8799-111">See also</span></span>
- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [<span data-ttu-id="a8799-112">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="a8799-112">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [<span data-ttu-id="a8799-113">Построение и рисование контуров</span><span class="sxs-lookup"><span data-stu-id="a8799-113">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
