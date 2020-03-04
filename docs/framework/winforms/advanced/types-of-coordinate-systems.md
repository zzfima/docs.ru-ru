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
ms.openlocfilehash: bbb0d4908d4a281499336d262c653d7b72f3ccdc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159810"
---
# <a name="types-of-coordinate-systems"></a><span data-ttu-id="b969a-102">Типы систем координат</span><span class="sxs-lookup"><span data-stu-id="b969a-102">Types of Coordinate Systems</span></span>
<span data-ttu-id="b969a-103">В GDI+ используются три координатных пространства: мир, страница и устройство.</span><span class="sxs-lookup"><span data-stu-id="b969a-103">GDI+ uses three coordinate spaces: world, page, and device.</span></span> <span data-ttu-id="b969a-104">Мировые координаты — это координаты, используемые для моделирования определенного графического мира, а также координаты, передаваемые методам в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b969a-104">World coordinates are the coordinates used to model a particular graphic world and are the coordinates you pass to methods in the .NET Framework.</span></span> <span data-ttu-id="b969a-105">Координаты страницы относятся к системе координат, используемой областью рисования, такой как форма или элемент управления.</span><span class="sxs-lookup"><span data-stu-id="b969a-105">Page coordinates refer to the coordinate system used by a drawing surface, such as a form or control.</span></span> <span data-ttu-id="b969a-106">Координаты устройства — это координаты, используемые физическим устройством, которое рисуется, например экран или лист бумаги.</span><span class="sxs-lookup"><span data-stu-id="b969a-106">Device coordinates are the coordinates used by the physical device being drawn on, such as a screen or sheet of paper.</span></span> <span data-ttu-id="b969a-107">При выполнении `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`вызова точки, передаваемые в метод <xref:System.Drawing.Graphics.DrawLine%2A> (`(0, 0)` и `(160, 80)`), находятся в мировом пространстве координат.</span><span class="sxs-lookup"><span data-stu-id="b969a-107">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, the points that you pass to the <xref:System.Drawing.Graphics.DrawLine%2A> method—`(0, 0)` and `(160, 80)`—are in the world coordinate space.</span></span> <span data-ttu-id="b969a-108">До того, как интерфейс GDI+ может нарисовать линию на экране, координаты проходят через последовательность преобразований.</span><span class="sxs-lookup"><span data-stu-id="b969a-108">Before GDI+ can draw the line on the screen, the coordinates pass through a sequence of transformations.</span></span> <span data-ttu-id="b969a-109">Одно преобразование, которое называется мировым преобразованием, преобразует мировые координаты в координаты страницы, а другое преобразование, называемое преобразованием страницы, преобразует координаты страницы в координаты устройства.</span><span class="sxs-lookup"><span data-stu-id="b969a-109">One transformation, called the world transformation, converts world coordinates to page coordinates, and another transformation, called the page transformation, converts page coordinates to device coordinates.</span></span>  
  
## <a name="transforms-and-coordinate-systems"></a><span data-ttu-id="b969a-110">Преобразования и системы координат</span><span class="sxs-lookup"><span data-stu-id="b969a-110">Transforms and Coordinate Systems</span></span>  
 <span data-ttu-id="b969a-111">Предположим, что вы хотите работать с системой координат, имеющей свою точку в тексте клиентской области, а не в левом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="b969a-111">Suppose you want to work with a coordinate system that has its origin in the body of the client area rather than the upper-left corner.</span></span> <span data-ttu-id="b969a-112">Предположим, например, что вы хотите, чтобы источник был 100 пикселей от левого края клиентской области и 50 пикселей от верхнего края клиентской области.</span><span class="sxs-lookup"><span data-stu-id="b969a-112">Say, for example, that you want the origin to be 100 pixels from the left edge of the client area and 50 pixels from the top of the client area.</span></span> <span data-ttu-id="b969a-113">На следующем рисунке показана такая система координат.</span><span class="sxs-lookup"><span data-stu-id="b969a-113">The following illustration shows such a coordinate system.</span></span>  
  
 <span data-ttu-id="b969a-114">![Система координат](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span><span class="sxs-lookup"><span data-stu-id="b969a-114">![Coordinate System](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span></span>  
  
 <span data-ttu-id="b969a-115">Выполнив вызов `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, вы получаете строку, показанную на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="b969a-115">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, you get the line shown in the following illustration.</span></span>  
  
 <span data-ttu-id="b969a-116">![Система координат](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span><span class="sxs-lookup"><span data-stu-id="b969a-116">![Coordinate System](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span></span>  
  
 <span data-ttu-id="b969a-117">Ниже приведены координаты конечных точек линии в трех координатных пространствах.</span><span class="sxs-lookup"><span data-stu-id="b969a-117">The coordinates of the endpoints of your line in the three coordinate spaces are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b969a-118">Реального</span><span class="sxs-lookup"><span data-stu-id="b969a-118">World</span></span>|<span data-ttu-id="b969a-119">(от 0 до 0) до (160, 80)</span><span class="sxs-lookup"><span data-stu-id="b969a-119">(0, 0) to (160, 80)</span></span>|  
|<span data-ttu-id="b969a-120">Страница</span><span class="sxs-lookup"><span data-stu-id="b969a-120">Page</span></span>|<span data-ttu-id="b969a-121">(100, 50) в (260, 130)</span><span class="sxs-lookup"><span data-stu-id="b969a-121">(100, 50) to (260, 130)</span></span>|  
|<span data-ttu-id="b969a-122">Устройство</span><span class="sxs-lookup"><span data-stu-id="b969a-122">Device</span></span>|<span data-ttu-id="b969a-123">(100, 50) в (260, 130)</span><span class="sxs-lookup"><span data-stu-id="b969a-123">(100, 50) to (260, 130)</span></span>|  
  
 <span data-ttu-id="b969a-124">Обратите внимание, что координатное пространство страницы имеет свой источник в левом верхнем углу клиентской области. Это всегда будет так.</span><span class="sxs-lookup"><span data-stu-id="b969a-124">Note that the page coordinate space has its origin at the upper-left corner of the client area; this will always be the case.</span></span> <span data-ttu-id="b969a-125">Также обратите внимание, что поскольку единицей измерения является пиксель, координаты устройства совпадают с координатами страницы.</span><span class="sxs-lookup"><span data-stu-id="b969a-125">Also note that because the unit of measure is the pixel, the device coordinates are the same as the page coordinates.</span></span> <span data-ttu-id="b969a-126">Если задать для единицы измерения значение, отличное от пикселей (например, дюймы), то координаты устройства будут отличаться от координат на странице.</span><span class="sxs-lookup"><span data-stu-id="b969a-126">If you set the unit of measure to something other than pixels (for example, inches), then the device coordinates will be different from the page coordinates.</span></span>  
  
 <span data-ttu-id="b969a-127">Преобразование «мир», которое сопоставляет координаты мира с координатами страницы, хранится в свойстве <xref:System.Drawing.Graphics.Transform%2A> класса <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="b969a-127">The world transformation, which maps world coordinates to page coordinates, is held in the <xref:System.Drawing.Graphics.Transform%2A> property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="b969a-128">В предыдущем примере преобразование «мир» представляет собой единицы перевода 100 в направлении x и 50 единиц по оси y.</span><span class="sxs-lookup"><span data-stu-id="b969a-128">In the preceding example, the world transformation is a translation 100 units in the x direction and 50 units in the y direction.</span></span> <span data-ttu-id="b969a-129">В следующем примере задается универсальное преобразование объекта <xref:System.Drawing.Graphics>, а затем используется этот <xref:System.Drawing.Graphics> объект для отрисовки линии, показанной на предыдущем рисунке:</span><span class="sxs-lookup"><span data-stu-id="b969a-129">The following example sets the world transformation of a <xref:System.Drawing.Graphics> object and then uses that <xref:System.Drawing.Graphics> object to draw the line shown in the preceding figure:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 <span data-ttu-id="b969a-130">Преобразование страницы сопоставляет координаты страницы с координатами устройства.</span><span class="sxs-lookup"><span data-stu-id="b969a-130">The page transformation maps page coordinates to device coordinates.</span></span> <span data-ttu-id="b969a-131">Класс <xref:System.Drawing.Graphics> предоставляет свойства <xref:System.Drawing.Graphics.PageUnit%2A> и <xref:System.Drawing.Graphics.PageScale%2A> для управления преобразованием страницы.</span><span class="sxs-lookup"><span data-stu-id="b969a-131">The <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.PageUnit%2A> and <xref:System.Drawing.Graphics.PageScale%2A> properties for manipulating the page transformation.</span></span> <span data-ttu-id="b969a-132">Класс <xref:System.Drawing.Graphics> также предоставляет два свойства только для чтения, <xref:System.Drawing.Graphics.DpiX%2A> и <xref:System.Drawing.Graphics.DpiY%2A>, для проверки горизонтальной и вертикальной точек на дюйм устройства дисплея.</span><span class="sxs-lookup"><span data-stu-id="b969a-132">The <xref:System.Drawing.Graphics> class also provides two read-only properties, <xref:System.Drawing.Graphics.DpiX%2A> and <xref:System.Drawing.Graphics.DpiY%2A>, for examining the horizontal and vertical dots per inch of the display device.</span></span>  
  
 <span data-ttu-id="b969a-133">Можно использовать свойство <xref:System.Drawing.Graphics.PageUnit%2A> класса <xref:System.Drawing.Graphics>, чтобы указать единицу измерения, отличную от пикселя.</span><span class="sxs-lookup"><span data-stu-id="b969a-133">You can use the <xref:System.Drawing.Graphics.PageUnit%2A> property of the <xref:System.Drawing.Graphics> class to specify a unit of measure other than the pixel.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b969a-134">Нельзя задать для свойства <xref:System.Drawing.Graphics.PageUnit%2A> значение <xref:System.Drawing.GraphicsUnit.World>, так как это не физическое устройство и вызовет исключение.</span><span class="sxs-lookup"><span data-stu-id="b969a-134">You cannot set the <xref:System.Drawing.Graphics.PageUnit%2A> property to <xref:System.Drawing.GraphicsUnit.World>, as this is not a physical unit and will cause an exception.</span></span>  
  
 <span data-ttu-id="b969a-135">В следующем примере рисуется линия от (0, 0) до (2, 1), где точка (2, 1) — 2 дюйма справа и 1 дюйм вниз от точки (0, 0):</span><span class="sxs-lookup"><span data-stu-id="b969a-135">The following example draws a line from (0, 0) to (2, 1), where the point (2, 1) is 2 inches to the right and 1 inch down from the point (0, 0):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
> <span data-ttu-id="b969a-136">Если вы не укажете толщину пера при создании пера, в предыдущем примере будет нарисована линия шириной в один дюйм.</span><span class="sxs-lookup"><span data-stu-id="b969a-136">If you don't specify a pen width when you construct your pen, the preceding example will draw a line that is one inch wide.</span></span> <span data-ttu-id="b969a-137">Можно указать ширину пера во втором аргументе в конструкторе <xref:System.Drawing.Pen>:</span><span class="sxs-lookup"><span data-stu-id="b969a-137">You can specify the pen width in the second argument to the <xref:System.Drawing.Pen> constructor:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 <span data-ttu-id="b969a-138">Если предполагается, что устройство вывода имеет 96 точек на дюйм в горизонтальном направлении и 96 точек на дюйм в вертикальном направлении, конечные точки строки в предыдущем примере имеют следующие координаты в трех координатных пространствах:</span><span class="sxs-lookup"><span data-stu-id="b969a-138">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b969a-139">Реального</span><span class="sxs-lookup"><span data-stu-id="b969a-139">World</span></span>|<span data-ttu-id="b969a-140">(0, 0) на (2, 1)</span><span class="sxs-lookup"><span data-stu-id="b969a-140">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="b969a-141">Страница</span><span class="sxs-lookup"><span data-stu-id="b969a-141">Page</span></span>|<span data-ttu-id="b969a-142">(0, 0) на (2, 1)</span><span class="sxs-lookup"><span data-stu-id="b969a-142">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="b969a-143">Устройство</span><span class="sxs-lookup"><span data-stu-id="b969a-143">Device</span></span>|<span data-ttu-id="b969a-144">(от 0 до 0) до (192, 96)</span><span class="sxs-lookup"><span data-stu-id="b969a-144">(0, 0) to (192, 96)</span></span>|  
  
 <span data-ttu-id="b969a-145">Обратите внимание, что поскольку источник пространства координат мира находится в левом верхнем углу клиентской области, координаты страницы совпадают с координатами мира.</span><span class="sxs-lookup"><span data-stu-id="b969a-145">Note that because the origin of the world coordinate space is at the upper-left corner of the client area, the page coordinates are the same as the world coordinates.</span></span>  
  
 <span data-ttu-id="b969a-146">Для получения различных эффектов можно сочетать преобразования «мир» и «страница».</span><span class="sxs-lookup"><span data-stu-id="b969a-146">You can combine the world and page transformations to achieve a variety of effects.</span></span> <span data-ttu-id="b969a-147">Например, предположим, что вы хотите использовать дюйма в качестве единицы измерения и хотите, чтобы источник координат был 2 дюйма от левого края клиентской области и 1/2 дюйма от верхней части клиентской области.</span><span class="sxs-lookup"><span data-stu-id="b969a-147">For example, suppose you want to use inches as the unit of measure and you want the origin of your coordinate system to be 2 inches from the left edge of the client area and 1/2 inch from the top of the client area.</span></span> <span data-ttu-id="b969a-148">В следующем примере задаются преобразование «мир» и «страница» <xref:System.Drawing.Graphics> объекта, после чего рисуется строка от (0, 0) до (2, 1):</span><span class="sxs-lookup"><span data-stu-id="b969a-148">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object and then draws a line from (0, 0) to (2, 1):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 <span data-ttu-id="b969a-149">На следующем рисунке показана линия и система координат.</span><span class="sxs-lookup"><span data-stu-id="b969a-149">The following illustration shows the line and coordinate system.</span></span>  
  
 <span data-ttu-id="b969a-150">![Система координат](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span><span class="sxs-lookup"><span data-stu-id="b969a-150">![Coordinate System](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span></span>  
  
 <span data-ttu-id="b969a-151">Если предполагается, что устройство вывода имеет 96 точек на дюйм в горизонтальном направлении и 96 точек на дюйм в вертикальном направлении, конечные точки строки в предыдущем примере имеют следующие координаты в трех координатных пространствах:</span><span class="sxs-lookup"><span data-stu-id="b969a-151">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b969a-152">Реального</span><span class="sxs-lookup"><span data-stu-id="b969a-152">World</span></span>|<span data-ttu-id="b969a-153">(0, 0) на (2, 1)</span><span class="sxs-lookup"><span data-stu-id="b969a-153">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="b969a-154">Страница</span><span class="sxs-lookup"><span data-stu-id="b969a-154">Page</span></span>|<span data-ttu-id="b969a-155">(от 2, 0,5) до (4, 1,5)</span><span class="sxs-lookup"><span data-stu-id="b969a-155">(2, 0.5) to (4, 1.5)</span></span>|  
|<span data-ttu-id="b969a-156">Устройство</span><span class="sxs-lookup"><span data-stu-id="b969a-156">Device</span></span>|<span data-ttu-id="b969a-157">(192, 48) в (384, 144)</span><span class="sxs-lookup"><span data-stu-id="b969a-157">(192, 48) to (384, 144)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b969a-158">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b969a-158">See also</span></span>

- [<span data-ttu-id="b969a-159">Системы координат и преобразования</span><span class="sxs-lookup"><span data-stu-id="b969a-159">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="b969a-160">Матричное представление преобразований</span><span class="sxs-lookup"><span data-stu-id="b969a-160">Matrix Representation of Transformations</span></span>](matrix-representation-of-transformations.md)
