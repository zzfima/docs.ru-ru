---
title: "Области в GDI+"
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
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d3805c2d67f5241425ef72d3802aba996d33cfb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="regions-in-gdi"></a><span data-ttu-id="a3b00-102">Области в GDI+</span><span class="sxs-lookup"><span data-stu-id="a3b00-102">Regions in GDI+</span></span>
<span data-ttu-id="a3b00-103">Область — это часть области отображения устройство вывода.</span><span class="sxs-lookup"><span data-stu-id="a3b00-103">A region is a portion of the display area of an output device.</span></span> <span data-ttu-id="a3b00-104">Области могут быть простой (один прямоугольник) или сложными (набор многоугольников и замкнутых кривых).</span><span class="sxs-lookup"><span data-stu-id="a3b00-104">Regions can be simple (a single rectangle) or complex (a combination of polygons and closed curves).</span></span> <span data-ttu-id="a3b00-105">На следующем рисунке показано две области: один из них образована прямоугольником, а другая образована путь.</span><span class="sxs-lookup"><span data-stu-id="a3b00-105">The following illustration shows two regions: one constructed from a rectangle, and the other constructed from a path.</span></span>  
  
 <span data-ttu-id="a3b00-106">![Регионы](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span><span class="sxs-lookup"><span data-stu-id="a3b00-106">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span></span>  
  
## <a name="using-regions"></a><span data-ttu-id="a3b00-107">Использование областей</span><span class="sxs-lookup"><span data-stu-id="a3b00-107">Using Regions</span></span>  
 <span data-ttu-id="a3b00-108">Области часто используются для обрезки и проверка нажатия.</span><span class="sxs-lookup"><span data-stu-id="a3b00-108">Regions are often used for clipping and hit testing.</span></span> <span data-ttu-id="a3b00-109">Отсечение заключается в запрете на рисование определенной области отображения, обычно это область, необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="a3b00-109">Clipping involves restricting drawing to a certain region of the display area, usually the portion that needs to be updated.</span></span> <span data-ttu-id="a3b00-110">Проверка на наличие данных включает в себя проверку, чтобы определить, находится ли курсор в области экрана при нажатии кнопки мыши.</span><span class="sxs-lookup"><span data-stu-id="a3b00-110">Hit testing involves checking to determine whether the cursor is in a certain region of the screen when a mouse button is pressed.</span></span>  
  
 <span data-ttu-id="a3b00-111">Можно создать регион из прямоугольника или путь.</span><span class="sxs-lookup"><span data-stu-id="a3b00-111">You can construct a region from a rectangle or a path.</span></span> <span data-ttu-id="a3b00-112">Можно также создавать сложные области путем объединения существующих областей.</span><span class="sxs-lookup"><span data-stu-id="a3b00-112">You can also create complex regions by combining existing regions.</span></span> <span data-ttu-id="a3b00-113"><xref:System.Drawing.Region> Класс предоставляет следующие методы для объединения областей: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, и <xref:System.Drawing.Region.Complement%2A>.</span><span class="sxs-lookup"><span data-stu-id="a3b00-113">The <xref:System.Drawing.Region> class provides the following methods for combining regions: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, and <xref:System.Drawing.Region.Complement%2A>.</span></span>  
  
 <span data-ttu-id="a3b00-114">Пересечение двух областей — это совокупность всех точек, принадлежащих обоих регионах.</span><span class="sxs-lookup"><span data-stu-id="a3b00-114">The intersection of two regions is the set of all points belonging to both regions.</span></span> <span data-ttu-id="a3b00-115">Объединение — это набор всех точек, принадлежащих одной или обеих областей.</span><span class="sxs-lookup"><span data-stu-id="a3b00-115">The union is the set of all points belonging to one or the other or both regions.</span></span> <span data-ttu-id="a3b00-116">Дополнение области — это набор всех точек, которые не находятся в области.</span><span class="sxs-lookup"><span data-stu-id="a3b00-116">The complement of a region is the set of all points that are not in the region.</span></span> <span data-ttu-id="a3b00-117">Пересечение и объединение двух областей, на предыдущем рисунке показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="a3b00-117">The following illustration shows the intersection and union of the two regions shown in the preceding illustration.</span></span>  
  
 <span data-ttu-id="a3b00-118">![Регионы](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span><span class="sxs-lookup"><span data-stu-id="a3b00-118">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span></span>  
  
 <span data-ttu-id="a3b00-119"><xref:System.Drawing.Region.Xor%2A> Метод, примененный к паре областей, выдает область, содержащую все точки, которые принадлежат к одной области или другой, но не оба.</span><span class="sxs-lookup"><span data-stu-id="a3b00-119">The <xref:System.Drawing.Region.Xor%2A> method, applied to a pair of regions, produces a region that contains all points that belong to one region or the other, but not both.</span></span> <span data-ttu-id="a3b00-120"><xref:System.Drawing.Region.Exclude%2A> Метод, примененный к паре областей, выдает область, содержащую все точки первой области, которые не являются второй области.</span><span class="sxs-lookup"><span data-stu-id="a3b00-120">The <xref:System.Drawing.Region.Exclude%2A> method, applied to a pair of regions, produces a region that contains all points in the first region that are not in the second region.</span></span> <span data-ttu-id="a3b00-121">На следующем рисунке показан областей, которые являются результатом применения <xref:System.Drawing.Region.Xor%2A> и <xref:System.Drawing.Region.Exclude%2A> методы для двух регионах, показанный в начале этого раздела.</span><span class="sxs-lookup"><span data-stu-id="a3b00-121">The following illustration shows the regions that result from applying the <xref:System.Drawing.Region.Xor%2A> and <xref:System.Drawing.Region.Exclude%2A> methods to the two regions shown at the beginning of this topic.</span></span>  
  
 <span data-ttu-id="a3b00-122">![Регионы](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span><span class="sxs-lookup"><span data-stu-id="a3b00-122">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span></span>  
  
 <span data-ttu-id="a3b00-123">Чтобы заполнить область, необходимо <xref:System.Drawing.Graphics> объекта, <xref:System.Drawing.Brush> объекта и <xref:System.Drawing.Region> объекта.</span><span class="sxs-lookup"><span data-stu-id="a3b00-123">To fill a region, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Brush> object, and a <xref:System.Drawing.Region> object.</span></span> <span data-ttu-id="a3b00-124"><xref:System.Drawing.Graphics> Объект предоставляет <xref:System.Drawing.Graphics.FillRegion%2A> метода и <xref:System.Drawing.Brush> объект хранилищем атрибутов, таких как цвета или узора заливки.</span><span class="sxs-lookup"><span data-stu-id="a3b00-124">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.FillRegion%2A> method, and the <xref:System.Drawing.Brush> object stores attributes of the fill, such as color or pattern.</span></span> <span data-ttu-id="a3b00-125">Следующий пример заполняет область сплошным цветом.</span><span class="sxs-lookup"><span data-stu-id="a3b00-125">The following example fills a region with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="a3b00-126">См. также</span><span class="sxs-lookup"><span data-stu-id="a3b00-126">See Also</span></span>  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [<span data-ttu-id="a3b00-127">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="a3b00-127">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="a3b00-128">Использование областей</span><span class="sxs-lookup"><span data-stu-id="a3b00-128">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)
