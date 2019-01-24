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
# <a name="managing-the-state-of-a-graphics-object"></a>Управление состоянием объекта Graphics
<xref:System.Drawing.Graphics> Класс является сердцем [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Чтобы нарисовать что-либо, необходимо получить <xref:System.Drawing.Graphics> , задать его свойства и вызывать его методы <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>и ей подобные).  
  
 В следующем примере вызывается <xref:System.Drawing.Graphics.DrawRectangle%2A> метод <xref:System.Drawing.Graphics> объекта. Первый аргумент, переданный <xref:System.Drawing.Graphics.DrawRectangle%2A> метод <xref:System.Drawing.Pen> объекта.  
  
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
  
## <a name="graphics-state"></a>Состояние графики  
 Объект <xref:System.Drawing.Graphics> объекта более чем функции рисования, такие как <xref:System.Drawing.Graphics.DrawLine%2A> и <xref:System.Drawing.Graphics.DrawRectangle%2A>. Объект <xref:System.Drawing.Graphics> объект также хранит состояние графики, которое можно разделить на следующие категории:  
  
-   Параметры качества  
  
-   Преобразования  
  
-   Отсеченная область  
  
### <a name="quality-settings"></a>Параметры качества  
 Объект <xref:System.Drawing.Graphics> имеет несколько свойств, которые влияют на качество рисуемых объектов. Например, можно задать <xref:System.Drawing.Graphics.TextRenderingHint%2A> свойство, чтобы указать тип сглаживания (если таковые имеются), примененный к тексту. Другие свойства, которые влияют на качество являются <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, и <xref:System.Drawing.Graphics.InterpolationMode%2A>.  
  
 В следующем примере рисуется два эллипса, один с режимом сглаживания <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> и один с режимом сглаживания <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:  
  
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
  
### <a name="transformations"></a>Преобразования  
 Объект <xref:System.Drawing.Graphics> поддерживает два преобразования (мировое и страничное), которые применяются ко всем элементам, отображаемым <xref:System.Drawing.Graphics> объекта. Любой аффинного преобразования могут храниться в мировое преобразование. Аффинные преобразования включают масштабирование, поворот, отражение, наклон и преобразования. Преобразование страницы может использоваться для масштабирования и преобразования единиц измерения (например, точек в дюймах). Дополнительные сведения см. в разделе [системы координат и преобразования](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).  
  
 В следующем примере задается мировое и страничное преобразования из <xref:System.Drawing.Graphics> объекта. Мировое преобразование присваивается поворот на 30 градусов. Преобразование страницы устанавливается таким образом, координаты передать второй <xref:System.Drawing.Graphics.DrawEllipse%2A> будет рассматриваться как миллиметрах вместо пикселей. Код вызывает два идентичных <xref:System.Drawing.Graphics.DrawEllipse%2A> метод. Мировое преобразование применяется к первому <xref:System.Drawing.Graphics.DrawEllipse%2A> вызов и оба вида преобразований (мировое и страничное) применяются к второй <xref:System.Drawing.Graphics.DrawEllipse%2A> вызова.  
  
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
  
 На следующем рисунке двух эллипсов. Обратите внимание, что поворот на 30 градусов относительно начала координат (в левом верхнем углу клиентской области), не о центров эллипсов. Обратите внимание на то, что толщина пера, равная 1, означает 1 пиксель для первого эллипса и 1 миллиметр второго эллипса.  
  
 ![Овалы](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")  
  
### <a name="clipping-region"></a>Отсеченная область  
 Объект <xref:System.Drawing.Graphics> объект поддерживает область обрезки, применяются ко всем элементам, отображаемым <xref:System.Drawing.Graphics> объекта. Можно задать области обрезки, вызвав <xref:System.Drawing.Graphics.SetClip%2A> метод.  
  
 В следующем примере создается область креста, являющаяся объединением двух прямоугольников. Этот регион используется в качестве отсеченной области объекта <xref:System.Drawing.Graphics> объекта. Затем код выводит две строки, которые ограничены внутренней области отсечения.  
  
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
  
 На следующем рисунке усеченные строки.  
  
 ![Ограниченная область отсечения](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")  
  
## <a name="see-also"></a>См. также
- [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [Использование вложенных графических контейнеров](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)
