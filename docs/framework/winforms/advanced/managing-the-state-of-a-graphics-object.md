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
# <a name="managing-the-state-of-a-graphics-object"></a>Управление состоянием объекта Graphics
Класс <xref:System.Drawing.Graphics> находится в центре GDI. Чтобы нарисовать что-нибудь, <xref:System.Drawing.Graphics> вы получаете объект, устанавливаете его свойства и называете его методы <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Graphics.DrawImage%2A>и <xref:System.Drawing.Graphics.DrawString%2A>тому подобное).  
  
 Следующий пример <xref:System.Drawing.Graphics.DrawRectangle%2A> называет метод <xref:System.Drawing.Graphics> объекта. Первым аргументом, <xref:System.Drawing.Graphics.DrawRectangle%2A> передаваемым методу, <xref:System.Drawing.Pen> является объект.  
  
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
 Объект <xref:System.Drawing.Graphics> делает больше, чем предоставляет методы рисования, такие как <xref:System.Drawing.Graphics.DrawLine%2A> и <xref:System.Drawing.Graphics.DrawRectangle%2A>. Объект <xref:System.Drawing.Graphics> также поддерживает графическое состояние, которое можно разделить на следующие категории:  
  
- Настройки качества  
  
- Преобразования  
  
- Область отсечения  
  
### <a name="quality-settings"></a>Настройки качества  
 Объект <xref:System.Drawing.Graphics> имеет несколько свойств, влияющих на качество нарисованных элементов. Например, можно установить свойство <xref:System.Drawing.Graphics.TextRenderingHint%2A> для указания типа антиалиазинга (если таковой имеется) к тексту. Другие свойства, <xref:System.Drawing.Graphics.SmoothingMode%2A>которые <xref:System.Drawing.Graphics.CompositingMode%2A> <xref:System.Drawing.Graphics.CompositingQuality%2A>влияют <xref:System.Drawing.Graphics.InterpolationMode%2A>на качество, и .  
  
 Следующий пример рисует два эллипса, один <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> с режимом сглаживания <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>установлен на и один с сглаживающим режимом, установленным на:  
  
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
 Объект <xref:System.Drawing.Graphics> поддерживает два преобразования (мир и страница), которые применяются <xref:System.Drawing.Graphics> ко всем элементам, нарисованным этим объектом. Любая трансформация аффин может храниться в мировой трансформации. Преобразований Affine включают масштабирование, вращание, отражение, перекос и перевод. Преобразование страницы может быть использовано для масштабирования и для изменения единиц (например, пикселей на дюймы). Для получения дополнительной [информации см.](coordinate-systems-and-transformations.md)  
  
 Следующий пример устанавливает преобразования мира и <xref:System.Drawing.Graphics> страницы объекта. Преобразование мира настроено на 30-градусную ротацию. Преобразование страницы настроено таким образом, <xref:System.Drawing.Graphics.DrawEllipse%2A> что координаты, передаваемые второй, будут рассматриваться как миллиметры вместо пикселей. Код делает два одинаковых <xref:System.Drawing.Graphics.DrawEllipse%2A> вызова метода. Преобразование мира применяется <xref:System.Drawing.Graphics.DrawEllipse%2A> к первому вызову, и оба преобразования <xref:System.Drawing.Graphics.DrawEllipse%2A> (мир и страница) применяются ко второму вызову.  
  
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
  
 На следующей иллюстрации показаны два эллипса. Отметим, что 30-градусное вращение связано с происхождением системы координат (вверху-левом углу клиентской зоны), а не о центрах эллипсов. Также обратите внимание, что ширина пера 1 означает 1 пиксель для первого эллипса и 1 миллиметр для второго эллипса.  
  
 ![Иллюстрация, на рисунке два эллипса: вращение и ширина пера.](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a>Область отсечения  
 Объект <xref:System.Drawing.Graphics> поддерживает область отсечения, которая применяется ко всем элементам, нарисованным этим <xref:System.Drawing.Graphics> объектом. Можно настроить область отсечения, позвонив по методу. <xref:System.Drawing.Graphics.SetClip%2A>  
  
 Следующий пример создает область плюс-образной, образуя объединение двух прямоугольников. Этот регион обозначен как область отсечения <xref:System.Drawing.Graphics> объекта. Затем код рисует две линии, которые ограничены внутренней частью области отсечения.  
  
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
  
 На следующей иллюстрации показаны обрезанные строки:  
  
 ![Диаграмма, отображая область ограниченного клипа.](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a>См. также раздел

- [Объекты Graphics и Drawing в Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Использование вложенных графических контейнеров](using-nested-graphics-containers.md)
