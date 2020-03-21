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
ms.openlocfilehash: d1e7e6eac775ca779fb68605adcc9bc2b9915e49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182452"
---
# <a name="managing-the-state-of-a-graphics-object"></a><span data-ttu-id="9bbc2-102">Управление состоянием объекта Graphics</span><span class="sxs-lookup"><span data-stu-id="9bbc2-102">Managing the State of a Graphics Object</span></span>
<span data-ttu-id="9bbc2-103">Класс <xref:System.Drawing.Graphics> находится в центре GDI.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-103">The <xref:System.Drawing.Graphics> class is at the heart of GDI+.</span></span> <span data-ttu-id="9bbc2-104">Чтобы нарисовать что-нибудь, <xref:System.Drawing.Graphics> вы получаете объект, устанавливаете его свойства и называете его методы <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Graphics.DrawImage%2A>и <xref:System.Drawing.Graphics.DrawString%2A>тому подобное).</span><span class="sxs-lookup"><span data-stu-id="9bbc2-104">To draw anything, you obtain a <xref:System.Drawing.Graphics> object, set its properties, and call its methods <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, and the like).</span></span>  
  
 <span data-ttu-id="9bbc2-105">Следующий пример <xref:System.Drawing.Graphics.DrawRectangle%2A> называет метод <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-105">The following example calls the <xref:System.Drawing.Graphics.DrawRectangle%2A> method of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="9bbc2-106">Первым аргументом, <xref:System.Drawing.Graphics.DrawRectangle%2A> передаваемым методу, <xref:System.Drawing.Pen> является объект.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-106">The first argument passed to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method is a <xref:System.Drawing.Pen> object.</span></span>  
  
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
  
## <a name="graphics-state"></a><span data-ttu-id="9bbc2-107">Состояние графики</span><span class="sxs-lookup"><span data-stu-id="9bbc2-107">Graphics State</span></span>  
 <span data-ttu-id="9bbc2-108">Объект <xref:System.Drawing.Graphics> делает больше, чем предоставляет методы рисования, такие как <xref:System.Drawing.Graphics.DrawLine%2A> и <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-108">A <xref:System.Drawing.Graphics> object does more than provide drawing methods, such as <xref:System.Drawing.Graphics.DrawLine%2A> and <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span></span> <span data-ttu-id="9bbc2-109">Объект <xref:System.Drawing.Graphics> также поддерживает графическое состояние, которое можно разделить на следующие категории:</span><span class="sxs-lookup"><span data-stu-id="9bbc2-109">A <xref:System.Drawing.Graphics> object also maintains graphics state, which can be divided into the following categories:</span></span>  
  
- <span data-ttu-id="9bbc2-110">Настройки качества</span><span class="sxs-lookup"><span data-stu-id="9bbc2-110">Quality settings</span></span>  
  
- <span data-ttu-id="9bbc2-111">Преобразования</span><span class="sxs-lookup"><span data-stu-id="9bbc2-111">Transformations</span></span>  
  
- <span data-ttu-id="9bbc2-112">Область отсечения</span><span class="sxs-lookup"><span data-stu-id="9bbc2-112">Clipping region</span></span>  
  
### <a name="quality-settings"></a><span data-ttu-id="9bbc2-113">Настройки качества</span><span class="sxs-lookup"><span data-stu-id="9bbc2-113">Quality Settings</span></span>  
 <span data-ttu-id="9bbc2-114">Объект <xref:System.Drawing.Graphics> имеет несколько свойств, влияющих на качество нарисованных элементов.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-114">A <xref:System.Drawing.Graphics> object has several properties that influence the quality of the items that are drawn.</span></span> <span data-ttu-id="9bbc2-115">Например, можно установить свойство <xref:System.Drawing.Graphics.TextRenderingHint%2A> для указания типа антиалиазинга (если таковой имеется) к тексту.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-115">For example, you can set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property to specify the type of antialiasing (if any) applied to text.</span></span> <span data-ttu-id="9bbc2-116">Другие свойства, <xref:System.Drawing.Graphics.SmoothingMode%2A>которые <xref:System.Drawing.Graphics.CompositingMode%2A> <xref:System.Drawing.Graphics.CompositingQuality%2A>влияют <xref:System.Drawing.Graphics.InterpolationMode%2A>на качество, и .</span><span class="sxs-lookup"><span data-stu-id="9bbc2-116">Other properties that influence quality are <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, and <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span></span>  
  
 <span data-ttu-id="9bbc2-117">Следующий пример рисует два эллипса, один <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> с режимом сглаживания <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>установлен на и один с сглаживающим режимом, установленным на:</span><span class="sxs-lookup"><span data-stu-id="9bbc2-117">The following example draws two ellipses, one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> and one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span></span>  
  
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
  
### <a name="transformations"></a><span data-ttu-id="9bbc2-118">Преобразования</span><span class="sxs-lookup"><span data-stu-id="9bbc2-118">Transformations</span></span>  
 <span data-ttu-id="9bbc2-119">Объект <xref:System.Drawing.Graphics> поддерживает два преобразования (мир и страница), которые применяются <xref:System.Drawing.Graphics> ко всем элементам, нарисованным этим объектом.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-119">A <xref:System.Drawing.Graphics> object maintains two transformations (world and page) that are applied to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="9bbc2-120">Любая трансформация аффин может храниться в мировой трансформации.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-120">Any affine transformation can be stored in the world transformation.</span></span> <span data-ttu-id="9bbc2-121">Преобразований Affine включают масштабирование, вращание, отражение, перекос и перевод.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-121">Affine transformations include scaling, rotating, reflecting, skewing, and translating.</span></span> <span data-ttu-id="9bbc2-122">Преобразование страницы может быть использовано для масштабирования и для изменения единиц (например, пикселей на дюймы).</span><span class="sxs-lookup"><span data-stu-id="9bbc2-122">The page transformation can be used for scaling and for changing units (for example, pixels to inches).</span></span> <span data-ttu-id="9bbc2-123">Для получения дополнительной [информации см.](coordinate-systems-and-transformations.md)</span><span class="sxs-lookup"><span data-stu-id="9bbc2-123">For more information, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
 <span data-ttu-id="9bbc2-124">Следующий пример устанавливает преобразования мира и <xref:System.Drawing.Graphics> страницы объекта.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-124">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="9bbc2-125">Преобразование мира настроено на 30-градусную ротацию.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-125">The world transformation is set to a 30-degree rotation.</span></span> <span data-ttu-id="9bbc2-126">Преобразование страницы настроено таким образом, <xref:System.Drawing.Graphics.DrawEllipse%2A> что координаты, передаваемые второй, будут рассматриваться как миллиметры вместо пикселей.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-126">The page transformation is set so that the coordinates passed to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> will be treated as millimeters instead of pixels.</span></span> <span data-ttu-id="9bbc2-127">Код делает два одинаковых <xref:System.Drawing.Graphics.DrawEllipse%2A> вызова метода.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-127">The code makes two identical calls to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="9bbc2-128">Преобразование мира применяется <xref:System.Drawing.Graphics.DrawEllipse%2A> к первому вызову, и оба преобразования <xref:System.Drawing.Graphics.DrawEllipse%2A> (мир и страница) применяются ко второму вызову.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-128">The world transformation is applied to the first <xref:System.Drawing.Graphics.DrawEllipse%2A> call, and both transformations (world and page) are applied to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> call.</span></span>  
  
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
  
 <span data-ttu-id="9bbc2-129">На следующей иллюстрации показаны два эллипса.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-129">The following illustration shows the two ellipses.</span></span> <span data-ttu-id="9bbc2-130">Отметим, что 30-градусное вращение связано с происхождением системы координат (вверху-левом углу клиентской зоны), а не о центрах эллипсов.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-130">Note that the 30-degree rotation is about the origin of the coordinate system (upper-left corner of the client area), not about the centers of the ellipses.</span></span> <span data-ttu-id="9bbc2-131">Также обратите внимание, что ширина пера 1 означает 1 пиксель для первого эллипса и 1 миллиметр для второго эллипса.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-131">Also note that the pen width of 1 means 1 pixel for the first ellipse and 1 millimeter for the second ellipse.</span></span>  
  
 ![Иллюстрация, на рисунке два эллипса: вращение и ширина пера.](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a><span data-ttu-id="9bbc2-133">Область отсечения</span><span class="sxs-lookup"><span data-stu-id="9bbc2-133">Clipping Region</span></span>  
 <span data-ttu-id="9bbc2-134">Объект <xref:System.Drawing.Graphics> поддерживает область отсечения, которая применяется ко всем элементам, нарисованным этим <xref:System.Drawing.Graphics> объектом.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-134">A <xref:System.Drawing.Graphics> object maintains a clipping region that applies to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="9bbc2-135">Можно настроить область отсечения, позвонив по методу. <xref:System.Drawing.Graphics.SetClip%2A></span><span class="sxs-lookup"><span data-stu-id="9bbc2-135">You can set the clipping region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
 <span data-ttu-id="9bbc2-136">Следующий пример создает область плюс-образной, образуя объединение двух прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-136">The following example creates a plus-shaped region by forming the union of two rectangles.</span></span> <span data-ttu-id="9bbc2-137">Этот регион обозначен как область отсечения <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-137">That region is designated as the clipping region of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="9bbc2-138">Затем код рисует две линии, которые ограничены внутренней частью области отсечения.</span><span class="sxs-lookup"><span data-stu-id="9bbc2-138">Then the code draws two lines that are restricted to the interior of the clipping region.</span></span>  
  
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
  
 <span data-ttu-id="9bbc2-139">На следующей иллюстрации показаны обрезанные строки:</span><span class="sxs-lookup"><span data-stu-id="9bbc2-139">The following illustration shows the clipped lines:</span></span>  
  
 ![Диаграмма, отображая область ограниченного клипа.](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a><span data-ttu-id="9bbc2-141">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9bbc2-141">See also</span></span>

- [<span data-ttu-id="9bbc2-142">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9bbc2-142">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="9bbc2-143">Использование вложенных графических контейнеров</span><span class="sxs-lookup"><span data-stu-id="9bbc2-143">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)
