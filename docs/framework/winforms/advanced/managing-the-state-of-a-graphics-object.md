---
title: Управление состоянием объекта Graphics
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
ms.openlocfilehash: 5e9e75876862a73be7ace08c09610923d007de4b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540862"
---
# <a name="managing-the-state-of-a-graphics-object"></a><span data-ttu-id="9fc40-102">Управление состоянием объекта Graphics</span><span class="sxs-lookup"><span data-stu-id="9fc40-102">Managing the State of a Graphics Object</span></span>
<span data-ttu-id="9fc40-103"><xref:System.Drawing.Graphics> Класс является сердцем [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9fc40-103">The <xref:System.Drawing.Graphics> class is at the heart of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="9fc40-104">Чтобы нарисовать что-либо, необходимо получить <xref:System.Drawing.Graphics> , задать его свойства и вызывать его методы <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>и ей подобные).</span><span class="sxs-lookup"><span data-stu-id="9fc40-104">To draw anything, you obtain a <xref:System.Drawing.Graphics> object, set its properties, and call its methods <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, and the like).</span></span>  
  
 <span data-ttu-id="9fc40-105">В следующем примере вызывается <xref:System.Drawing.Graphics.DrawRectangle%2A> метод <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="9fc40-105">The following example calls the <xref:System.Drawing.Graphics.DrawRectangle%2A> method of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="9fc40-106">Первый аргумент, переданный <xref:System.Drawing.Graphics.DrawRectangle%2A> метод <xref:System.Drawing.Pen> объекта.</span><span class="sxs-lookup"><span data-stu-id="9fc40-106">The first argument passed to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method is a <xref:System.Drawing.Pen> object.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a><span data-ttu-id="9fc40-107">Состояние графики</span><span class="sxs-lookup"><span data-stu-id="9fc40-107">Graphics State</span></span>  
 <span data-ttu-id="9fc40-108">Объект <xref:System.Drawing.Graphics> объекта более чем функции рисования, такие как <xref:System.Drawing.Graphics.DrawLine%2A> и <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span><span class="sxs-lookup"><span data-stu-id="9fc40-108">A <xref:System.Drawing.Graphics> object does more than provide drawing methods, such as <xref:System.Drawing.Graphics.DrawLine%2A> and <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span></span> <span data-ttu-id="9fc40-109">Объект <xref:System.Drawing.Graphics> объект также хранит состояние графики, которое можно разделить на следующие категории:</span><span class="sxs-lookup"><span data-stu-id="9fc40-109">A <xref:System.Drawing.Graphics> object also maintains graphics state, which can be divided into the following categories:</span></span>  
  
-   <span data-ttu-id="9fc40-110">Параметры качества</span><span class="sxs-lookup"><span data-stu-id="9fc40-110">Quality settings</span></span>  
  
-   <span data-ttu-id="9fc40-111">Преобразования</span><span class="sxs-lookup"><span data-stu-id="9fc40-111">Transformations</span></span>  
  
-   <span data-ttu-id="9fc40-112">Отсеченная область</span><span class="sxs-lookup"><span data-stu-id="9fc40-112">Clipping region</span></span>  
  
### <a name="quality-settings"></a><span data-ttu-id="9fc40-113">Параметры качества</span><span class="sxs-lookup"><span data-stu-id="9fc40-113">Quality Settings</span></span>  
 <span data-ttu-id="9fc40-114">Объект <xref:System.Drawing.Graphics> имеет несколько свойств, которые влияют на качество рисуемых объектов.</span><span class="sxs-lookup"><span data-stu-id="9fc40-114">A <xref:System.Drawing.Graphics> object has several properties that influence the quality of the items that are drawn.</span></span> <span data-ttu-id="9fc40-115">Например, можно задать <xref:System.Drawing.Graphics.TextRenderingHint%2A> свойство, чтобы указать тип сглаживания (если таковые имеются), примененный к тексту.</span><span class="sxs-lookup"><span data-stu-id="9fc40-115">For example, you can set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property to specify the type of antialiasing (if any) applied to text.</span></span> <span data-ttu-id="9fc40-116">Другие свойства, которые влияют на качество являются <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, и <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="9fc40-116">Other properties that influence quality are <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, and <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span></span>  
  
 <span data-ttu-id="9fc40-117">В следующем примере рисуется два эллипса, один с режимом сглаживания <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> и один с режимом сглаживания <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span><span class="sxs-lookup"><span data-stu-id="9fc40-117">The following example draws two ellipses, one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> and one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a><span data-ttu-id="9fc40-118">Преобразования</span><span class="sxs-lookup"><span data-stu-id="9fc40-118">Transformations</span></span>  
 <span data-ttu-id="9fc40-119">Объект <xref:System.Drawing.Graphics> поддерживает два преобразования (мировое и страничное), которые применяются ко всем элементам, отображаемым <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="9fc40-119">A <xref:System.Drawing.Graphics> object maintains two transformations (world and page) that are applied to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="9fc40-120">Любой аффинного преобразования могут храниться в мировое преобразование.</span><span class="sxs-lookup"><span data-stu-id="9fc40-120">Any affine transformation can be stored in the world transformation.</span></span> <span data-ttu-id="9fc40-121">Аффинные преобразования включают масштабирование, поворот, отражение, наклон и преобразования.</span><span class="sxs-lookup"><span data-stu-id="9fc40-121">Affine transformations include scaling, rotating, reflecting, skewing, and translating.</span></span> <span data-ttu-id="9fc40-122">Преобразование страницы может использоваться для масштабирования и преобразования единиц измерения (например, точек в дюймах).</span><span class="sxs-lookup"><span data-stu-id="9fc40-122">The page transformation can be used for scaling and for changing units (for example, pixels to inches).</span></span> <span data-ttu-id="9fc40-123">Дополнительные сведения см. в разделе [системы координат и преобразования](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="9fc40-123">For more information, see [Coordinate Systems and Transformations](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).</span></span>  
  
 <span data-ttu-id="9fc40-124">В следующем примере задается мировое и страничное преобразования из <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="9fc40-124">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="9fc40-125">Мировое преобразование присваивается поворот на 30 градусов.</span><span class="sxs-lookup"><span data-stu-id="9fc40-125">The world transformation is set to a 30-degree rotation.</span></span> <span data-ttu-id="9fc40-126">Преобразование страницы устанавливается таким образом, координаты передать второй <xref:System.Drawing.Graphics.DrawEllipse%2A> будет рассматриваться как миллиметрах вместо пикселей.</span><span class="sxs-lookup"><span data-stu-id="9fc40-126">The page transformation is set so that the coordinates passed to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> will be treated as millimeters instead of pixels.</span></span> <span data-ttu-id="9fc40-127">Код вызывает два идентичных <xref:System.Drawing.Graphics.DrawEllipse%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="9fc40-127">The code makes two identical calls to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="9fc40-128">Мировое преобразование применяется к первому <xref:System.Drawing.Graphics.DrawEllipse%2A> вызов и оба вида преобразований (мировое и страничное) применяются к второй <xref:System.Drawing.Graphics.DrawEllipse%2A> вызова.</span><span class="sxs-lookup"><span data-stu-id="9fc40-128">The world transformation is applied to the first <xref:System.Drawing.Graphics.DrawEllipse%2A> call, and both transformations (world and page) are applied to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> call.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);   
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 <span data-ttu-id="9fc40-129">На следующем рисунке двух эллипсов.</span><span class="sxs-lookup"><span data-stu-id="9fc40-129">The following illustration shows the two ellipses.</span></span> <span data-ttu-id="9fc40-130">Обратите внимание, что поворот на 30 градусов относительно начала координат (в левом верхнем углу клиентской области), не о центров эллипсов.</span><span class="sxs-lookup"><span data-stu-id="9fc40-130">Note that the 30-degree rotation is about the origin of the coordinate system (upper-left corner of the client area), not about the centers of the ellipses.</span></span> <span data-ttu-id="9fc40-131">Обратите внимание на то, что толщина пера, равная 1, означает 1 пиксель для первого эллипса и 1 миллиметр второго эллипса.</span><span class="sxs-lookup"><span data-stu-id="9fc40-131">Also note that the pen width of 1 means 1 pixel for the first ellipse and 1 millimeter for the second ellipse.</span></span>  
  
 <span data-ttu-id="9fc40-132">![Овалы](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")</span><span class="sxs-lookup"><span data-stu-id="9fc40-132">![Ovals](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")</span></span>  
  
### <a name="clipping-region"></a><span data-ttu-id="9fc40-133">Отсеченная область</span><span class="sxs-lookup"><span data-stu-id="9fc40-133">Clipping Region</span></span>  
 <span data-ttu-id="9fc40-134">Объект <xref:System.Drawing.Graphics> объект поддерживает область обрезки, применяются ко всем элементам, отображаемым <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="9fc40-134">A <xref:System.Drawing.Graphics> object maintains a clipping region that applies to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="9fc40-135">Можно задать области обрезки, вызвав <xref:System.Drawing.Graphics.SetClip%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="9fc40-135">You can set the clipping region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
 <span data-ttu-id="9fc40-136">В следующем примере создается область креста, являющаяся объединением двух прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="9fc40-136">The following example creates a plus-shaped region by forming the union of two rectangles.</span></span> <span data-ttu-id="9fc40-137">Этот регион используется в качестве отсеченной области объекта <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="9fc40-137">That region is designated as the clipping region of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="9fc40-138">Затем код выводит две строки, которые ограничены внутренней области отсечения.</span><span class="sxs-lookup"><span data-stu-id="9fc40-138">Then the code draws two lines that are restricted to the interior of the clipping region.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);    
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));    
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 <span data-ttu-id="9fc40-139">На следующем рисунке усеченные строки.</span><span class="sxs-lookup"><span data-stu-id="9fc40-139">The following illustration shows the clipped lines.</span></span>  
  
 <span data-ttu-id="9fc40-140">![Ограниченная область отсечения](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")</span><span class="sxs-lookup"><span data-stu-id="9fc40-140">![Limited Clip Region](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fc40-141">См. также</span><span class="sxs-lookup"><span data-stu-id="9fc40-141">See also</span></span>
- [<span data-ttu-id="9fc40-142">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9fc40-142">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="9fc40-143">Использование вложенных графических контейнеров</span><span class="sxs-lookup"><span data-stu-id="9fc40-143">Using Nested Graphics Containers</span></span>](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)
