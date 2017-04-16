---
title: "Управление состоянием объекта Graphics | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "графика, усечение"
  - "графика, управление состоянием"
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Управление состоянием объекта Graphics
Класс <xref:System.Drawing.Graphics> является ключевым элементом интерфейса [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  Чтобы нарисовать что\-либо, необходимо получить объект <xref:System.Drawing.Graphics>, задать его свойства и вызвать его методы \(<xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A> и т. д.\).  
  
 В данном примере вызывается метод <xref:System.Drawing.Graphics.DrawRectangle%2A> класса <xref:System.Drawing.Graphics>.  Первым параметром, передаваемым методу <xref:System.Drawing.Graphics.DrawRectangle%2A>, является объект <xref:System.Drawing.Pen>.  
  
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
  
## Состояние объекта Graphics  
 Объект <xref:System.Drawing.Graphics> предоставляет более широкие функции, чем функции рисования, такие как <xref:System.Drawing.Graphics.DrawLine%2A> или <xref:System.Drawing.Graphics.DrawRectangle%2A>.  Объект <xref:System.Drawing.Graphics> также осуществляет поддержку графического состояния, которое можно подразделить на следующие категории:  
  
-   Параметры качества  
  
-   Преобразования  
  
-   Область обрезки  
  
### Параметры качества  
 Объект <xref:System.Drawing.Graphics> содержит некоторые свойства, влияющие на качество отображаемых объектов.  Например, можно установить значение свойства <xref:System.Drawing.Graphics.TextRenderingHint%2A>, чтобы указать способ сглаживания \(если оно нужно\), применяемый к тексту.  К другим свойствам, влияющим на качество, относятся свойства <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A> и <xref:System.Drawing.Graphics.InterpolationMode%2A>.  
  
 В следующем примере рисуются два эллипса, один с режимом сглаживания <xref:System.Drawing.Drawing2D.SmoothingMode>, а второй — с режимом сглаживания <xref:System.Drawing.Drawing2D.SmoothingMode>:  
  
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
  
### Преобразования  
 Объект <xref:System.Drawing.Graphics> поддерживает два преобразования \(объемное и страничное\), которые применяются ко всем объектам, отображаемым объектом <xref:System.Drawing.Graphics>.  Любое аффинное преобразование можно хранить в объемном преобразовании.  Аффинные преобразования — это масштабирование, поворот, отражение, наклон и сдвиг.  Страничное преобразование может использоваться для масштабирования и преобразования единиц измерения \(например, пикселей в дюймы\).  Дополнительные сведения см. в разделе [Системы координат и преобразования](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).  
  
 В приведенном ниже примере устанавливаются объемное и страничное преобразования объекта <xref:System.Drawing.Graphics>.  В качестве объемного преобразования устанавливается поворот на 30 градусов.  Страничное преобразование устанавливается таким образом, чтобы координаты, передаваемые второму методу <xref:System.Drawing.Graphics.DrawEllipse%2A>, измерялись в миллиметрах, а не в пикселях.  В коде осуществляются два одинаковых вызова метода <xref:System.Drawing.Graphics.DrawEllipse%2A>.  При вызове первого метода <xref:System.Drawing.Graphics.DrawEllipse%2A> применяется только объемное преобразование, а при вызове второго метода <xref:System.Drawing.Graphics.DrawEllipse%2A> применяются оба преобразования \(объемное и страничное\).  
  
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
  
 Два нарисованных эллипса показаны на следующем рисунке.  Следует отметить, что поворот на 30 градусов осуществляется относительно начала координат \(верхний левый угол клиентской области\), а не относительно центров эллипсов.  Также обратите внимание, что толщина пера, равная 1, означает 1 пиксель при рисовании первого эллипса, а при рисовании второго эллипса это 1 миллиметр.  
  
 ![Овалы](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")  
  
### Область обрезки  
 Объект <xref:System.Drawing.Graphics> поддерживает область обрезки, которая применяется для всех объектов, отображаемых объектом <xref:System.Drawing.Graphics>.  Для установки границ области обрезки служит метод <xref:System.Drawing.Graphics.SetClip%2A>.  
  
 В следующем примере создается область в форме креста, являющаяся объединением двух прямоугольников.  Эта область назначается областью обрезки для объекта <xref:System.Drawing.Graphics>.  Затем в коде рисуются две линии, ограниченные внутренней частью области обрезки.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](../../../../amples/snippets/visualbasic/VS_Snippets_Wpf/ToolBarOrient_snip/visualbasic/toolbargraphics/new.bmp Rectangle(50, 0, 50, 150))  
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
  
 Обрезанные линии показаны на следующем рисунке.  
  
 ![Ограниченная область обрезки](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")  
  
## См. также  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Использование вложенных графических контейнеров](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)