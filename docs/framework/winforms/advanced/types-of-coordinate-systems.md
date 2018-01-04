---
title: "Типы систем координат"
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 287b1c9eddef882041d9e4eac44a06190f3585a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="types-of-coordinate-systems"></a><span data-ttu-id="3b380-102">Типы систем координат</span><span class="sxs-lookup"><span data-stu-id="3b380-102">Types of Coordinate Systems</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="3b380-103">использует три координатных пространства: мировое, страницы и устройства.</span><span class="sxs-lookup"><span data-stu-id="3b380-103"> uses three coordinate spaces: world, page, and device.</span></span> <span data-ttu-id="3b380-104">Мировых координатах являются координаты, используемые для моделирования определенного графического мира и которые можно передать методу в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3b380-104">World coordinates are the coordinates used to model a particular graphic world and are the coordinates you pass to methods in the .NET Framework.</span></span> <span data-ttu-id="3b380-105">Страничные координаты система координат, используемая на поверхности, таких как формы или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3b380-105">Page coordinates refer to the coordinate system used by a drawing surface, such as a form or control.</span></span> <span data-ttu-id="3b380-106">Координаты устройства — координат, используемая отрисовывается, таких как экран или листе физического устройства.</span><span class="sxs-lookup"><span data-stu-id="3b380-106">Device coordinates are the coordinates used by the physical device being drawn on, such as a screen or sheet of paper.</span></span> <span data-ttu-id="3b380-107">При вызове `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, точки, которые вы передаете в <xref:System.Drawing.Graphics.DrawLine%2A> метод —`(0, 0)` и `(160, 80)`— в мировом пространстве координат.</span><span class="sxs-lookup"><span data-stu-id="3b380-107">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, the points that you pass to the <xref:System.Drawing.Graphics.DrawLine%2A> method—`(0, 0)` and `(160, 80)`—are in the world coordinate space.</span></span> <span data-ttu-id="3b380-108">Прежде чем [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] можно нарисовать линию на экране, координаты подвергнутся последовательности преобразований.</span><span class="sxs-lookup"><span data-stu-id="3b380-108">Before [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can draw the line on the screen, the coordinates pass through a sequence of transformations.</span></span> <span data-ttu-id="3b380-109">Преобразует одно преобразование, вызывается мировое преобразование мировых координатах страничных координат и еще одно преобразование, страничное преобразование переводит страничные координаты в координаты устройства.</span><span class="sxs-lookup"><span data-stu-id="3b380-109">One transformation, called the world transformation, converts world coordinates to page coordinates, and another transformation, called the page transformation, converts page coordinates to device coordinates.</span></span>  
  
## <a name="transforms-and-coordinate-systems"></a><span data-ttu-id="3b380-110">Системы координат и преобразования</span><span class="sxs-lookup"><span data-stu-id="3b380-110">Transforms and Coordinate Systems</span></span>  
 <span data-ttu-id="3b380-111">Предположим, что вы хотите работать с системы координат, который расположен в основной части клиентской области, а не в левом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="3b380-111">Suppose you want to work with a coordinate system that has its origin in the body of the client area rather than the upper-left corner.</span></span> <span data-ttu-id="3b380-112">Пусть, например, требуемый источник равным 100 пикселей от левого края клиентской области и 50 пикселей от верхнего края клиентской области.</span><span class="sxs-lookup"><span data-stu-id="3b380-112">Say, for example, that you want the origin to be 100 pixels from the left edge of the client area and 50 pixels from the top of the client area.</span></span> <span data-ttu-id="3b380-113">Такая система координат на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="3b380-113">The following illustration shows such a coordinate system.</span></span>  
  
 <span data-ttu-id="3b380-114">![Система координат](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art01.gif "AboutGdip05_art01")</span><span class="sxs-lookup"><span data-stu-id="3b380-114">![Coordinate System](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art01.gif "AboutGdip05_art01")</span></span>  
  
 <span data-ttu-id="3b380-115">При вызове `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, линия, показанные на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="3b380-115">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, you get the line shown in the following illustration.</span></span>  
  
 <span data-ttu-id="3b380-116">![Система координат](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art02.gif "AboutGdip05_art02")</span><span class="sxs-lookup"><span data-stu-id="3b380-116">![Coordinate System](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art02.gif "AboutGdip05_art02")</span></span>  
  
 <span data-ttu-id="3b380-117">Ниже приведены координаты конечных точек линии в трех пространствах координат.</span><span class="sxs-lookup"><span data-stu-id="3b380-117">The coordinates of the endpoints of your line in the three coordinate spaces are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3b380-118">World</span><span class="sxs-lookup"><span data-stu-id="3b380-118">World</span></span>|<span data-ttu-id="3b380-119">(0, 0) к (160, 80)</span><span class="sxs-lookup"><span data-stu-id="3b380-119">(0, 0) to (160, 80)</span></span>|  
|<span data-ttu-id="3b380-120">Страница</span><span class="sxs-lookup"><span data-stu-id="3b380-120">Page</span></span>|<span data-ttu-id="3b380-121">(100, 50) для (260, 130.)</span><span class="sxs-lookup"><span data-stu-id="3b380-121">(100, 50) to (260, 130)</span></span>|  
|<span data-ttu-id="3b380-122">Устройство</span><span class="sxs-lookup"><span data-stu-id="3b380-122">Device</span></span>|<span data-ttu-id="3b380-123">(100, 50) для (260, 130.)</span><span class="sxs-lookup"><span data-stu-id="3b380-123">(100, 50) to (260, 130)</span></span>|  
  
 <span data-ttu-id="3b380-124">Обратите внимание, что пространство координат страницы начала координат в левом верхнем углу области клиента. Это будет всегда так.</span><span class="sxs-lookup"><span data-stu-id="3b380-124">Note that the page coordinate space has its origin at the upper-left corner of the client area; this will always be the case.</span></span> <span data-ttu-id="3b380-125">Также Обратите внимание, что, так как единицей измерения является точка, координаты устройства совпадают страничных координат.</span><span class="sxs-lookup"><span data-stu-id="3b380-125">Also note that because the unit of measure is the pixel, the device coordinates are the same as the page coordinates.</span></span> <span data-ttu-id="3b380-126">Если значение единицы измерения, отличные от точек (например, в дюймах), координаты устройства будут отличаться от страничных координат.</span><span class="sxs-lookup"><span data-stu-id="3b380-126">If you set the unit of measure to something other than pixels (for example, inches), then the device coordinates will be different from the page coordinates.</span></span>  
  
 <span data-ttu-id="3b380-127">Мировое преобразование, которая сопоставляет мировых координатах для страничных координат, хранится в <xref:System.Drawing.Graphics.Transform%2A> свойство <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="3b380-127">The world transformation, which maps world coordinates to page coordinates, is held in the <xref:System.Drawing.Graphics.Transform%2A> property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="3b380-128">В приведенном выше примере мировое преобразование является сдвиг на 100 единиц по оси x и 50 единиц по оси y.</span><span class="sxs-lookup"><span data-stu-id="3b380-128">In the preceding example, the world transformation is a translation 100 units in the x direction and 50 units in the y direction.</span></span> <span data-ttu-id="3b380-129">В следующем примере задается мировое преобразование объекта <xref:System.Drawing.Graphics> объекта и использование этого <xref:System.Drawing.Graphics> объекта, чтобы нарисовать линию, показанный на предыдущем рисунке:</span><span class="sxs-lookup"><span data-stu-id="3b380-129">The following example sets the world transformation of a <xref:System.Drawing.Graphics> object and then uses that <xref:System.Drawing.Graphics> object to draw the line shown in the preceding figure:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 <span data-ttu-id="3b380-130">Преобразование страницы сопоставляет страничных координат координатах устройства.</span><span class="sxs-lookup"><span data-stu-id="3b380-130">The page transformation maps page coordinates to device coordinates.</span></span> <span data-ttu-id="3b380-131"><xref:System.Drawing.Graphics> Класс предоставляет <xref:System.Drawing.Graphics.PageUnit%2A> и <xref:System.Drawing.Graphics.PageScale%2A> свойства для управления преобразование страницы.</span><span class="sxs-lookup"><span data-stu-id="3b380-131">The <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.PageUnit%2A> and <xref:System.Drawing.Graphics.PageScale%2A> properties for manipulating the page transformation.</span></span> <span data-ttu-id="3b380-132"><xref:System.Drawing.Graphics> Класс также предоставляет два свойства только для чтения, <xref:System.Drawing.Graphics.DpiX%2A> и <xref:System.Drawing.Graphics.DpiY%2A>, для обеспечения возможности проверки горизонтальной и вертикальной точек на дюйм дисплея.</span><span class="sxs-lookup"><span data-stu-id="3b380-132">The <xref:System.Drawing.Graphics> class also provides two read-only properties, <xref:System.Drawing.Graphics.DpiX%2A> and <xref:System.Drawing.Graphics.DpiY%2A>, for examining the horizontal and vertical dots per inch of the display device.</span></span>  
  
 <span data-ttu-id="3b380-133">Можно использовать <xref:System.Drawing.Graphics.PageUnit%2A> свойство <xref:System.Drawing.Graphics> класса для указания единицы измерения, отличной от точки.</span><span class="sxs-lookup"><span data-stu-id="3b380-133">You can use the <xref:System.Drawing.Graphics.PageUnit%2A> property of the <xref:System.Drawing.Graphics> class to specify a unit of measure other than the pixel.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b380-134">Не удается задать <xref:System.Drawing.Graphics.PageUnit%2A> свойства <xref:System.Drawing.GraphicsUnit.World>, как это не физическую единицу и вызовет исключение.</span><span class="sxs-lookup"><span data-stu-id="3b380-134">You cannot set the <xref:System.Drawing.Graphics.PageUnit%2A> property to <xref:System.Drawing.GraphicsUnit.World>, as this is not a physical unit and will cause an exception.</span></span>  
  
 <span data-ttu-id="3b380-135">В следующем примере рисуется строку из (0, 0) на (2, 1), где точка (2, 1) — 2 дюйма вправо и 1 дюйм вниз от точки (0, 0):</span><span class="sxs-lookup"><span data-stu-id="3b380-135">The following example draws a line from (0, 0) to (2, 1), where the point (2, 1) is 2 inches to the right and 1 inch down from the point (0, 0):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  <span data-ttu-id="3b380-136">Если не указать ширину пера, когда пера, приведенном выше примере будет нарисуйте линию, шириной 1 дюйм.</span><span class="sxs-lookup"><span data-stu-id="3b380-136">If you don't specify a pen width when you construct your pen, the preceding example will draw a line that is one inch wide.</span></span> <span data-ttu-id="3b380-137">Толщина пера можно указать в качестве второго аргумента <xref:System.Drawing.Pen> конструктор:</span><span class="sxs-lookup"><span data-stu-id="3b380-137">You can specify the pen width in the second argument to the <xref:System.Drawing.Pen> constructor:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 <span data-ttu-id="3b380-138">Если предположить, что устройство отображения содержит 96 точек на дюйм по горизонтали и 96 точек на дюйм по вертикали, строки в предыдущем примере конечные точки имеют следующие координаты в три координатных пространства:</span><span class="sxs-lookup"><span data-stu-id="3b380-138">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3b380-139">World</span><span class="sxs-lookup"><span data-stu-id="3b380-139">World</span></span>|<span data-ttu-id="3b380-140">(0, 0) на (2, 1)</span><span class="sxs-lookup"><span data-stu-id="3b380-140">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="3b380-141">Страница</span><span class="sxs-lookup"><span data-stu-id="3b380-141">Page</span></span>|<span data-ttu-id="3b380-142">(0, 0) на (2, 1)</span><span class="sxs-lookup"><span data-stu-id="3b380-142">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="3b380-143">Устройство</span><span class="sxs-lookup"><span data-stu-id="3b380-143">Device</span></span>|<span data-ttu-id="3b380-144">(0, 0, чтобы (192, 96)</span><span class="sxs-lookup"><span data-stu-id="3b380-144">(0, 0, to (192, 96)</span></span>|  
  
 <span data-ttu-id="3b380-145">Обратите внимание, что поскольку источника объемных координат верхнего левого угла клиентской области, страничные координаты таким же, как мировых координатах.</span><span class="sxs-lookup"><span data-stu-id="3b380-145">Note that because the origin of the world coordinate space is at the upper-left corner of the client area, the page coordinates are the same as the world coordinates.</span></span>  
  
 <span data-ttu-id="3b380-146">Можно объединять мировое и страничное преобразования для получения различных эффектов.</span><span class="sxs-lookup"><span data-stu-id="3b380-146">You can combine the world and page transformations to achieve a variety of effects.</span></span> <span data-ttu-id="3b380-147">Например предположим, вы хотите использовать дюймы в качестве единицы измерения и начало координат должно быть 2 дюйма от левого края клиентской области и 1/2 дюйма от верхнего края клиентской области.</span><span class="sxs-lookup"><span data-stu-id="3b380-147">For example, suppose you want to use inches as the unit of measure and you want the origin of your coordinate system to be 2 inches from the left edge of the client area and 1/2 inch from the top of the client area.</span></span> <span data-ttu-id="3b380-148">В следующем примере задается мировое и страничное преобразования из <xref:System.Drawing.Graphics> объекта, а затем выводит строку из (0, 0) на (2, 1):</span><span class="sxs-lookup"><span data-stu-id="3b380-148">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object and then draws a line from (0, 0) to (2, 1):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 <span data-ttu-id="3b380-149">На следующем рисунке линия и система координат.</span><span class="sxs-lookup"><span data-stu-id="3b380-149">The following illustration shows the line and coordinate system.</span></span>  
  
 <span data-ttu-id="3b380-150">![Система координат](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art03.gif "AboutGdip05_art03")</span><span class="sxs-lookup"><span data-stu-id="3b380-150">![Coordinate System](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art03.gif "AboutGdip05_art03")</span></span>  
  
 <span data-ttu-id="3b380-151">Если предположить, что устройство отображения содержит 96 точек на дюйм по горизонтали и 96 точек на дюйм по вертикали, строки в предыдущем примере конечные точки имеют следующие координаты в три координатных пространства:</span><span class="sxs-lookup"><span data-stu-id="3b380-151">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3b380-152">World</span><span class="sxs-lookup"><span data-stu-id="3b380-152">World</span></span>|<span data-ttu-id="3b380-153">(0, 0) на (2, 1)</span><span class="sxs-lookup"><span data-stu-id="3b380-153">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="3b380-154">Страница</span><span class="sxs-lookup"><span data-stu-id="3b380-154">Page</span></span>|<span data-ttu-id="3b380-155">(2, 0,5) для (4, 1.5)</span><span class="sxs-lookup"><span data-stu-id="3b380-155">(2, 0.5) to (4, 1.5)</span></span>|  
|<span data-ttu-id="3b380-156">Устройство</span><span class="sxs-lookup"><span data-stu-id="3b380-156">Device</span></span>|<span data-ttu-id="3b380-157">(192, 48) для (384, 144)</span><span class="sxs-lookup"><span data-stu-id="3b380-157">(192, 48) to (384, 144)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3b380-158">См. также</span><span class="sxs-lookup"><span data-stu-id="3b380-158">See Also</span></span>  
 [<span data-ttu-id="3b380-159">Системы координат и преобразования</span><span class="sxs-lookup"><span data-stu-id="3b380-159">Coordinate Systems and Transformations</span></span>](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [<span data-ttu-id="3b380-160">Матричное представление преобразований</span><span class="sxs-lookup"><span data-stu-id="3b380-160">Matrix Representation of Transformations</span></span>](../../../../docs/framework/winforms/advanced/matrix-representation-of-transformations.md)
