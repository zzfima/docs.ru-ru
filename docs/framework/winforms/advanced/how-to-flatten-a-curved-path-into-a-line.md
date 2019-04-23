---
title: Практическое руководство. Спрямление участков кривой
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: a151b4244e14d3704fd5fa1c55de92211981232f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215161"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="d741f-102">Практическое руководство. Спрямление участков кривой</span><span class="sxs-lookup"><span data-stu-id="d741f-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="d741f-103">Объект <xref:System.Drawing.Drawing2D.GraphicsPath> объект хранит последовательность, линий и сплайнов Безье.</span><span class="sxs-lookup"><span data-stu-id="d741f-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="d741f-104">Различные типы кривых (эллипсы, дуги, фундаментальные сплайны) можно добавить в путь, но каждую кривую преобразуется в кривую Безье, перед его сохранением в пути.</span><span class="sxs-lookup"><span data-stu-id="d741f-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="d741f-105">Спрямление путь заключается в преобразовании всех сплайнов Безье в пути в последовательность прямых линий.</span><span class="sxs-lookup"><span data-stu-id="d741f-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="d741f-106">Ниже показан путь до и после выравнивания.</span><span class="sxs-lookup"><span data-stu-id="d741f-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="d741f-107">![Прямые линии и кривые](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="d741f-107">![Straight Lines and Curves](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="d741f-108">Спрямление контура</span><span class="sxs-lookup"><span data-stu-id="d741f-108">To Flatten a Path</span></span>  
  
-   <span data-ttu-id="d741f-109">Вызовите <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> метод <xref:System.Drawing.Drawing2D.GraphicsPath> объекта.</span><span class="sxs-lookup"><span data-stu-id="d741f-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="d741f-110"><xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> Метод получает аргумент спрямления, который указывает максимальное расстояние между уплощенный путь и исходный путь.</span><span class="sxs-lookup"><span data-stu-id="d741f-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d741f-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d741f-111">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [<span data-ttu-id="d741f-112">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="d741f-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="d741f-113">Построение и рисование контуров</span><span class="sxs-lookup"><span data-stu-id="d741f-113">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
