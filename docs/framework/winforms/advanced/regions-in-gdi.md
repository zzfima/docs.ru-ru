---
title: Области в GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
ms.openlocfilehash: 33d4f4ecca7b9d777fa4eab5b6d031de10f03ccc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956808"
---
# <a name="regions-in-gdi"></a><span data-ttu-id="46129-102">Области в GDI+</span><span class="sxs-lookup"><span data-stu-id="46129-102">Regions in GDI+</span></span>
<span data-ttu-id="46129-103">Регион – часть области отображения устройства вывода.</span><span class="sxs-lookup"><span data-stu-id="46129-103">A region is a portion of the display area of an output device.</span></span> <span data-ttu-id="46129-104">Регионах может быть простое (один прямоугольник) или сложными (набор многоугольников и замкнутых кривых).</span><span class="sxs-lookup"><span data-stu-id="46129-104">Regions can be simple (a single rectangle) or complex (a combination of polygons and closed curves).</span></span> <span data-ttu-id="46129-105">На следующем рисунке показано два региона: один создан на основе прямоугольника, а другой создан на основе пути.</span><span class="sxs-lookup"><span data-stu-id="46129-105">The following illustration shows two regions: one constructed from a rectangle, and the other constructed from a path.</span></span>  
  
 <span data-ttu-id="46129-106">![Регионы](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span><span class="sxs-lookup"><span data-stu-id="46129-106">![Regions](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span></span>  
  
## <a name="using-regions"></a><span data-ttu-id="46129-107">Использование областей</span><span class="sxs-lookup"><span data-stu-id="46129-107">Using Regions</span></span>  
 <span data-ttu-id="46129-108">Области часто используются для обрезки и проверка нажатия.</span><span class="sxs-lookup"><span data-stu-id="46129-108">Regions are often used for clipping and hit testing.</span></span> <span data-ttu-id="46129-109">Обрезка заключается ограничение Рисование определенной области отображаемой области, обычно это область, необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="46129-109">Clipping involves restricting drawing to a certain region of the display area, usually the portion that needs to be updated.</span></span> <span data-ttu-id="46129-110">Проверка попадания включает в себя проверку, чтобы определить, находится ли курсор в определенной области экрана при нажатии кнопки мыши.</span><span class="sxs-lookup"><span data-stu-id="46129-110">Hit testing involves checking to determine whether the cursor is in a certain region of the screen when a mouse button is pressed.</span></span>  
  
 <span data-ttu-id="46129-111">Можно создать область от прямоугольника или путь.</span><span class="sxs-lookup"><span data-stu-id="46129-111">You can construct a region from a rectangle or a path.</span></span> <span data-ttu-id="46129-112">Можно также создавать сложные области путем объединения существующих областей.</span><span class="sxs-lookup"><span data-stu-id="46129-112">You can also create complex regions by combining existing regions.</span></span> <span data-ttu-id="46129-113"><xref:System.Drawing.Region> Класс предоставляет следующие методы для объединения областей: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, и <xref:System.Drawing.Region.Complement%2A>.</span><span class="sxs-lookup"><span data-stu-id="46129-113">The <xref:System.Drawing.Region> class provides the following methods for combining regions: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, and <xref:System.Drawing.Region.Complement%2A>.</span></span>  
  
 <span data-ttu-id="46129-114">Пересечение двух областей — набор всех точек, которые находятся в обоих регионах.</span><span class="sxs-lookup"><span data-stu-id="46129-114">The intersection of two regions is the set of all points belonging to both regions.</span></span> <span data-ttu-id="46129-115">Объединение — это набор всех точек, принадлежащих одной или другой или обоих регионах.</span><span class="sxs-lookup"><span data-stu-id="46129-115">The union is the set of all points belonging to one or the other or both regions.</span></span> <span data-ttu-id="46129-116">Дополнение области — это набор всех точек, которые не находятся в регионе.</span><span class="sxs-lookup"><span data-stu-id="46129-116">The complement of a region is the set of all points that are not in the region.</span></span> <span data-ttu-id="46129-117">На следующем рисунке пересечение и объединение двух областей, показанный на предыдущем рисунке.</span><span class="sxs-lookup"><span data-stu-id="46129-117">The following illustration shows the intersection and union of the two regions shown in the preceding illustration.</span></span>  
  
 <span data-ttu-id="46129-118">![Регионы](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span><span class="sxs-lookup"><span data-stu-id="46129-118">![Regions](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span></span>  
  
 <span data-ttu-id="46129-119"><xref:System.Drawing.Region.Xor%2A> , Примененный к паре регионов, создается область, содержащую все точки, принадлежащие к одной области или другой, но не оба.</span><span class="sxs-lookup"><span data-stu-id="46129-119">The <xref:System.Drawing.Region.Xor%2A> method, applied to a pair of regions, produces a region that contains all points that belong to one region or the other, but not both.</span></span> <span data-ttu-id="46129-120"><xref:System.Drawing.Region.Exclude%2A> Метод, примененный к паре областей, выдает область, содержащую все точки в первом регионе, которые не являются второго региона.</span><span class="sxs-lookup"><span data-stu-id="46129-120">The <xref:System.Drawing.Region.Exclude%2A> method, applied to a pair of regions, produces a region that contains all points in the first region that are not in the second region.</span></span> <span data-ttu-id="46129-121">На следующем рисунке показан регионов, возникающие в результате применения <xref:System.Drawing.Region.Xor%2A> и <xref:System.Drawing.Region.Exclude%2A> методы в двух регионах, приведенном в начале этого раздела.</span><span class="sxs-lookup"><span data-stu-id="46129-121">The following illustration shows the regions that result from applying the <xref:System.Drawing.Region.Xor%2A> and <xref:System.Drawing.Region.Exclude%2A> methods to the two regions shown at the beginning of this topic.</span></span>  
  
 <span data-ttu-id="46129-122">![Регионы](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span><span class="sxs-lookup"><span data-stu-id="46129-122">![Regions](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span></span>  
  
 <span data-ttu-id="46129-123">Для заполнения области, вам потребуется <xref:System.Drawing.Graphics> объекта, <xref:System.Drawing.Brush> объекта и <xref:System.Drawing.Region> объекта.</span><span class="sxs-lookup"><span data-stu-id="46129-123">To fill a region, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Brush> object, and a <xref:System.Drawing.Region> object.</span></span> <span data-ttu-id="46129-124"><xref:System.Drawing.Graphics> Предоставляет <xref:System.Drawing.Graphics.FillRegion%2A> метод и <xref:System.Drawing.Brush> объект сохраняет атрибуты, такие как цвета или узора заливки.</span><span class="sxs-lookup"><span data-stu-id="46129-124">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.FillRegion%2A> method, and the <xref:System.Drawing.Brush> object stores attributes of the fill, such as color or pattern.</span></span> <span data-ttu-id="46129-125">Следующий пример заполняет область сплошным цветом.</span><span class="sxs-lookup"><span data-stu-id="46129-125">The following example fills a region with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#61](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="46129-126">См. также</span><span class="sxs-lookup"><span data-stu-id="46129-126">See also</span></span>

- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [<span data-ttu-id="46129-127">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="46129-127">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="46129-128">Использование областей</span><span class="sxs-lookup"><span data-stu-id="46129-128">Using Regions</span></span>](using-regions.md)
