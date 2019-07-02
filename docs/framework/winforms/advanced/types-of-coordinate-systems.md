---
title: Типы систем координат
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
ms.openlocfilehash: 24079f24bdae5fefd785a20dda9b29a190fb4068
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505264"
---
# <a name="types-of-coordinate-systems"></a><span data-ttu-id="05221-102">Типы систем координат</span><span class="sxs-lookup"><span data-stu-id="05221-102">Types of Coordinate Systems</span></span>
<span data-ttu-id="05221-103">GDI + используется три координатных пространства: world, страницы и устройства.</span><span class="sxs-lookup"><span data-stu-id="05221-103">GDI+ uses three coordinate spaces: world, page, and device.</span></span> <span data-ttu-id="05221-104">Мировые координаты — это координаты, используемые для моделирования определенного графического мира и которые можно передать методу в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="05221-104">World coordinates are the coordinates used to model a particular graphic world and are the coordinates you pass to methods in the .NET Framework.</span></span> <span data-ttu-id="05221-105">Страничные координаты система координат, используемая области рисования, например формы или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="05221-105">Page coordinates refer to the coordinate system used by a drawing surface, such as a form or control.</span></span> <span data-ttu-id="05221-106">Координаты устройства — это координаты, используемые физического устройства, на котором производится рисование, будь то экран или лист бумаги.</span><span class="sxs-lookup"><span data-stu-id="05221-106">Device coordinates are the coordinates used by the physical device being drawn on, such as a screen or sheet of paper.</span></span> <span data-ttu-id="05221-107">При выполнении вызова `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, точки, которые передаются <xref:System.Drawing.Graphics.DrawLine%2A> метод —`(0, 0)` и `(160, 80)`— находятся в мировом пространстве координат.</span><span class="sxs-lookup"><span data-stu-id="05221-107">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, the points that you pass to the <xref:System.Drawing.Graphics.DrawLine%2A> method—`(0, 0)` and `(160, 80)`—are in the world coordinate space.</span></span> <span data-ttu-id="05221-108">Прежде чем GDI + можно нарисовать линию на экране, координаты проходит через последовательность преобразований.</span><span class="sxs-lookup"><span data-stu-id="05221-108">Before GDI+ can draw the line on the screen, the coordinates pass through a sequence of transformations.</span></span> <span data-ttu-id="05221-109">Одно из преобразований, вызывается мировое преобразование, конвертирующее мировые координаты в координаты страницы и еще одно преобразование, страничное преобразование преобразует координаты в координаты устройства.</span><span class="sxs-lookup"><span data-stu-id="05221-109">One transformation, called the world transformation, converts world coordinates to page coordinates, and another transformation, called the page transformation, converts page coordinates to device coordinates.</span></span>  
  
## <a name="transforms-and-coordinate-systems"></a><span data-ttu-id="05221-110">Системы координат и преобразования</span><span class="sxs-lookup"><span data-stu-id="05221-110">Transforms and Coordinate Systems</span></span>  
 <span data-ttu-id="05221-111">Предположим, что вы хотите работать с системой координат его началом координат в тексте клиентской области, а не в левом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="05221-111">Suppose you want to work with a coordinate system that has its origin in the body of the client area rather than the upper-left corner.</span></span> <span data-ttu-id="05221-112">Предположим, например, возникает необходимость начало координат будет находиться 100 пикселей от левого края клиентской области и 50 пикселей от верхнего края клиентской области.</span><span class="sxs-lookup"><span data-stu-id="05221-112">Say, for example, that you want the origin to be 100 pixels from the left edge of the client area and 50 pixels from the top of the client area.</span></span> <span data-ttu-id="05221-113">На следующем рисунке такая система координат.</span><span class="sxs-lookup"><span data-stu-id="05221-113">The following illustration shows such a coordinate system.</span></span>  
  
 <span data-ttu-id="05221-114">![Система координат](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span><span class="sxs-lookup"><span data-stu-id="05221-114">![Coordinate System](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span></span>  
  
 <span data-ttu-id="05221-115">При выполнении вызова `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, линия, показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="05221-115">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, you get the line shown in the following illustration.</span></span>  
  
 <span data-ttu-id="05221-116">![Система координат](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span><span class="sxs-lookup"><span data-stu-id="05221-116">![Coordinate System](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span></span>  
  
 <span data-ttu-id="05221-117">Ниже приведены координаты конечных точек линии в трех пространствах координат.</span><span class="sxs-lookup"><span data-stu-id="05221-117">The coordinates of the endpoints of your line in the three coordinate spaces are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05221-118">мир</span><span class="sxs-lookup"><span data-stu-id="05221-118">World</span></span>|<span data-ttu-id="05221-119">(0, 0) к (160, 80)</span><span class="sxs-lookup"><span data-stu-id="05221-119">(0, 0) to (160, 80)</span></span>|  
|<span data-ttu-id="05221-120">Страница</span><span class="sxs-lookup"><span data-stu-id="05221-120">Page</span></span>|<span data-ttu-id="05221-121">(100, 50) к (260, 130)</span><span class="sxs-lookup"><span data-stu-id="05221-121">(100, 50) to (260, 130)</span></span>|  
|<span data-ttu-id="05221-122">Устройство</span><span class="sxs-lookup"><span data-stu-id="05221-122">Device</span></span>|<span data-ttu-id="05221-123">(100, 50) к (260, 130)</span><span class="sxs-lookup"><span data-stu-id="05221-123">(100, 50) to (260, 130)</span></span>|  
  
 <span data-ttu-id="05221-124">Обратите внимание, что пространство координат страницы начала координат в левом верхнем углу области клиента. Это всегда будет так.</span><span class="sxs-lookup"><span data-stu-id="05221-124">Note that the page coordinate space has its origin at the upper-left corner of the client area; this will always be the case.</span></span> <span data-ttu-id="05221-125">Также Обратите внимание, что так как единицы измерения пиксель, координаты устройства так же, как координаты страницы.</span><span class="sxs-lookup"><span data-stu-id="05221-125">Also note that because the unit of measure is the pixel, the device coordinates are the same as the page coordinates.</span></span> <span data-ttu-id="05221-126">Значение единицы измерения отличные от точек (например, дюймов), координаты устройства будет отличаться от страничных координат.</span><span class="sxs-lookup"><span data-stu-id="05221-126">If you set the unit of measure to something other than pixels (for example, inches), then the device coordinates will be different from the page coordinates.</span></span>  
  
 <span data-ttu-id="05221-127">Мировое преобразование, которая сопоставляет мировых координатах в координаты страницы, хранится в <xref:System.Drawing.Graphics.Transform%2A> свойство <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="05221-127">The world transformation, which maps world coordinates to page coordinates, is held in the <xref:System.Drawing.Graphics.Transform%2A> property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="05221-128">В приведенном выше примере мировое преобразование является сдвиг на 100 единиц по оси x и 50 единиц по оси y.</span><span class="sxs-lookup"><span data-stu-id="05221-128">In the preceding example, the world transformation is a translation 100 units in the x direction and 50 units in the y direction.</span></span> <span data-ttu-id="05221-129">В следующем примере задается мировое преобразование объекта <xref:System.Drawing.Graphics> объекта, а затем использует, <xref:System.Drawing.Graphics> объекта, чтобы нарисовать линию, показанный на предыдущем рисунке:</span><span class="sxs-lookup"><span data-stu-id="05221-129">The following example sets the world transformation of a <xref:System.Drawing.Graphics> object and then uses that <xref:System.Drawing.Graphics> object to draw the line shown in the preceding figure:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 <span data-ttu-id="05221-130">Преобразование страницы сопоставляет координаты в координаты устройства.</span><span class="sxs-lookup"><span data-stu-id="05221-130">The page transformation maps page coordinates to device coordinates.</span></span> <span data-ttu-id="05221-131"><xref:System.Drawing.Graphics> Класс предоставляет <xref:System.Drawing.Graphics.PageUnit%2A> и <xref:System.Drawing.Graphics.PageScale%2A> свойства для управления преобразование страницы.</span><span class="sxs-lookup"><span data-stu-id="05221-131">The <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.PageUnit%2A> and <xref:System.Drawing.Graphics.PageScale%2A> properties for manipulating the page transformation.</span></span> <span data-ttu-id="05221-132"><xref:System.Drawing.Graphics> Класс также предоставляет два свойства только для чтения, <xref:System.Drawing.Graphics.DpiX%2A> и <xref:System.Drawing.Graphics.DpiY%2A>, для проверки горизонтальных и вертикальных точек на дюйм дисплея.</span><span class="sxs-lookup"><span data-stu-id="05221-132">The <xref:System.Drawing.Graphics> class also provides two read-only properties, <xref:System.Drawing.Graphics.DpiX%2A> and <xref:System.Drawing.Graphics.DpiY%2A>, for examining the horizontal and vertical dots per inch of the display device.</span></span>  
  
 <span data-ttu-id="05221-133">Можно использовать <xref:System.Drawing.Graphics.PageUnit%2A> свойство <xref:System.Drawing.Graphics> класса для указания единицы измерения, отличного от точки.</span><span class="sxs-lookup"><span data-stu-id="05221-133">You can use the <xref:System.Drawing.Graphics.PageUnit%2A> property of the <xref:System.Drawing.Graphics> class to specify a unit of measure other than the pixel.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05221-134">Невозможно задать <xref:System.Drawing.Graphics.PageUnit%2A> свойства <xref:System.Drawing.GraphicsUnit.World>, как это не физическую единицу и вызовет исключение.</span><span class="sxs-lookup"><span data-stu-id="05221-134">You cannot set the <xref:System.Drawing.Graphics.PageUnit%2A> property to <xref:System.Drawing.GraphicsUnit.World>, as this is not a physical unit and will cause an exception.</span></span>  
  
 <span data-ttu-id="05221-135">В следующем примере рисуется строки из (0, 0) на (2, 1), где точка (2, 1) — 2 дюйма вправо и 1 дюйм вниз от точки (0, 0):</span><span class="sxs-lookup"><span data-stu-id="05221-135">The following example draws a line from (0, 0) to (2, 1), where the point (2, 1) is 2 inches to the right and 1 inch down from the point (0, 0):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  <span data-ttu-id="05221-136">Если не указать ширину пера, когда пера, приведенном выше примере будет нарисовать линию, один дюйм.</span><span class="sxs-lookup"><span data-stu-id="05221-136">If you don't specify a pen width when you construct your pen, the preceding example will draw a line that is one inch wide.</span></span> <span data-ttu-id="05221-137">Можно указать ширину пера в качестве второго аргумента <xref:System.Drawing.Pen> конструктор:</span><span class="sxs-lookup"><span data-stu-id="05221-137">You can specify the pen width in the second argument to the <xref:System.Drawing.Pen> constructor:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 <span data-ttu-id="05221-138">Если предположить, что устройство отображения содержит 96 точек на дюйм по горизонтали и 96 точек на дюйм по вертикали, конечные точки линии в предыдущем примере имеют следующие координаты в три координатных пространства:</span><span class="sxs-lookup"><span data-stu-id="05221-138">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05221-139">мир</span><span class="sxs-lookup"><span data-stu-id="05221-139">World</span></span>|<span data-ttu-id="05221-140">(0, 0) на (2, 1)</span><span class="sxs-lookup"><span data-stu-id="05221-140">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="05221-141">Страница</span><span class="sxs-lookup"><span data-stu-id="05221-141">Page</span></span>|<span data-ttu-id="05221-142">(0, 0) на (2, 1)</span><span class="sxs-lookup"><span data-stu-id="05221-142">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="05221-143">Устройство</span><span class="sxs-lookup"><span data-stu-id="05221-143">Device</span></span>|<span data-ttu-id="05221-144">(0, 0, чтобы (192, 96)</span><span class="sxs-lookup"><span data-stu-id="05221-144">(0, 0, to (192, 96)</span></span>|  
  
 <span data-ttu-id="05221-145">Обратите внимание, что поскольку происхождение мировых координат в левом верхнем углу клиентской области, координаты страницы так же, как мировых координатах.</span><span class="sxs-lookup"><span data-stu-id="05221-145">Note that because the origin of the world coordinate space is at the upper-left corner of the client area, the page coordinates are the same as the world coordinates.</span></span>  
  
 <span data-ttu-id="05221-146">Можно объединить мировое и страничное преобразования для получения различных эффектов.</span><span class="sxs-lookup"><span data-stu-id="05221-146">You can combine the world and page transformations to achieve a variety of effects.</span></span> <span data-ttu-id="05221-147">Например предположим, вы хотите использовать в качестве единицы измерения дюймов и начало координат должно быть 2 дюйма от левого края клиентской области и 1/2 дюйма от верхнего края клиентской области.</span><span class="sxs-lookup"><span data-stu-id="05221-147">For example, suppose you want to use inches as the unit of measure and you want the origin of your coordinate system to be 2 inches from the left edge of the client area and 1/2 inch from the top of the client area.</span></span> <span data-ttu-id="05221-148">В следующем примере задается мировое и страничное преобразования из <xref:System.Drawing.Graphics> и затем рисует линию от (0, 0) на (2, 1):</span><span class="sxs-lookup"><span data-stu-id="05221-148">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object and then draws a line from (0, 0) to (2, 1):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 <span data-ttu-id="05221-149">Ниже показан строки и системы координат.</span><span class="sxs-lookup"><span data-stu-id="05221-149">The following illustration shows the line and coordinate system.</span></span>  
  
 <span data-ttu-id="05221-150">![Система координат](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span><span class="sxs-lookup"><span data-stu-id="05221-150">![Coordinate System](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span></span>  
  
 <span data-ttu-id="05221-151">Если предположить, что устройство отображения содержит 96 точек на дюйм по горизонтали и 96 точек на дюйм по вертикали, конечные точки линии в предыдущем примере имеют следующие координаты в три координатных пространства:</span><span class="sxs-lookup"><span data-stu-id="05221-151">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05221-152">мир</span><span class="sxs-lookup"><span data-stu-id="05221-152">World</span></span>|<span data-ttu-id="05221-153">(0, 0) на (2, 1)</span><span class="sxs-lookup"><span data-stu-id="05221-153">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="05221-154">Страница</span><span class="sxs-lookup"><span data-stu-id="05221-154">Page</span></span>|<span data-ttu-id="05221-155">(2, 0,5) к (4, 1.5)</span><span class="sxs-lookup"><span data-stu-id="05221-155">(2, 0.5) to (4, 1.5)</span></span>|  
|<span data-ttu-id="05221-156">Устройство</span><span class="sxs-lookup"><span data-stu-id="05221-156">Device</span></span>|<span data-ttu-id="05221-157">(192, 48) к (384, 144)</span><span class="sxs-lookup"><span data-stu-id="05221-157">(192, 48) to (384, 144)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05221-158">См. также</span><span class="sxs-lookup"><span data-stu-id="05221-158">See also</span></span>

- [<span data-ttu-id="05221-159">Системы координат и преобразования</span><span class="sxs-lookup"><span data-stu-id="05221-159">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="05221-160">Матричное представление преобразований</span><span class="sxs-lookup"><span data-stu-id="05221-160">Matrix Representation of Transformations</span></span>](matrix-representation-of-transformations.md)
