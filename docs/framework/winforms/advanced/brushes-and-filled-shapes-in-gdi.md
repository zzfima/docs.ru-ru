---
title: "Кисти и закрашенные фигуры в GDI+ | Microsoft Docs"
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
  - "кисти, GDI+"
  - "кисти, градиент"
  - "закрашенные фигуры, GDI+"
  - "GDI+, кисти"
  - "GDI+, закрашенные фигуры"
  - "градиентные кисти"
  - "фигуры, GDI+"
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Кисти и закрашенные фигуры в GDI+
Замкнутые фигуры, такие как прямоугольники или эллипсы, состоят из двух частей — из контура и из внутренней области.  Контур рисуется с помощью пера, а внутренняя область заливается с помощью кисти.  В [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] имеется несколько классов кистей для заливки замкнутых фигур: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush> и <xref:System.Drawing.Drawing2D.PathGradientBrush>.  Все эти классы являются производными от класса <xref:System.Drawing.Brush>.  На приведенном ниже рисунке изображен прямоугольник, залитый сплошной кистью, и эллипс, залитый штриховой кистью.  
  
 ![Закрашенные фигуры](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.png "Aboutgdip02\_art17")  
  
## Сплошные кисти  
 Чтобы залить замкнутую фигуру, необходимы объекты <xref:System.Drawing.Graphics> и <xref:System.Drawing.Brush>.  Объект <xref:System.Drawing.Graphics> предоставляет такие методы, как <xref:System.Drawing.Graphics.FillRectangle%2A> и <xref:System.Drawing.Graphics.FillEllipse%2A>, а в объекте <xref:System.Drawing.Brush> хранятся параметры заливки, такие как цвет и шаблон.  Объект <xref:System.Drawing.Brush> передается методу заливки в качестве одного из аргументов.  В следующем примере кода демонстрируется заливка эллипса сплошным красным цветом.  
  
 [!code-csharp[LinesCurvesAndShapes#121](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  В предыдущем примере используется кисть класса <xref:System.Drawing.SolidBrush>, унаследованного у класса <xref:System.Drawing.Brush>.  
  
## Штриховые кисти  
 При заливке формы штриховой кистью необходимо задать основной цвет, цвет фона и стиль штриховки.  Основной цвет определяет цвет штриховки.  
  
 [!code-csharp[LinesCurvesAndShapes#122](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 В [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] имеется более 50 стилей штриховки; на следующем рисунке показаны стили <xref:System.Drawing.Drawing2D.HatchStyle>, <xref:System.Drawing.Drawing2D.HatchStyle> и <xref:System.Drawing.Drawing2D.HatchStyle>.  
  
 ![Закрашенные фигуры](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.png "Aboutgdip02\_art18")  
  
## Текстурные кисти  
 Текстурная кисть позволяет заливать фигуру с использованием узора, сохраненного в виде растрового изображения.  Например, предположим, что приведенный ниже рисунок сохранен на диске в файле под названием `MyTexture.bmp`.  
  
 ![Закрашенная фигура](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.png "Aboutgdip02\_Art19")  
  
 В приведенном ниже примере демонстрируется заливка эллипса путем повторения в его внутренней области рисунка, сохраненного в файле `MyTexture.bmp`.  
  
 [!code-csharp[LinesCurvesAndShapes#123](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 Эллипс после заливки представлен на следующем рисунке.  
  
 ![Закрашенная фигура](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.png "AboutGdip02\_Art20")  
  
## Градиентные кисти  
 В [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] имеется два типа градиентных кистей: кисти линейного градиента и кисти градиента контура.  Кисти линейного градиента можно использовать для заливки фигуры цветом, постепенно меняющимся от одного края фигуры до другого по горизонтали, по вертикали или по диагонали.  В приведенном ниже примере кода демонстрируется заливка эллипса с использованием горизонтальной градиентной кисти, обеспечивающей изменение цвета от синего до зеленого при движении от левой границы эллипса до его правой границы.  
  
 [!code-csharp[LinesCurvesAndShapes#124](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 Эллипс после заливки представлен на следующем рисунке.  
  
 ![Закрашенная фигура](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.png "AboutGdip02\_Art21")  
  
 Кисть градиента контура может быть настроена так, чтобы цвет менялся от центра фигуры к ее границам.  
  
 ![Закрашенная фигура](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.png "AboutGdip02\_Art22")  
  
 Кисти градиента контура обеспечивают высокую степень гибкости.  В приведенном ниже примере демонстрируется использование градиентной кисти для заливки треугольника цветом, изменяющимся от красного в центре до трех различных цветов в каждой из трех вершин.  
  
 ![Закрашенная фигура](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.png "AboutGdip02\_Art23")  
  
## См. также  
 <xref:System.Drawing.SolidBrush?displayProperty=fullName>   
 <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=fullName>   
 <xref:System.Drawing.TextureBrush?displayProperty=fullName>   
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=fullName>   
 [Прямые и кривые линии и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Практическое руководство. Рисование заполненного прямоугольника в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-rectangle-on-a-windows-form.md)   
 [Практическое руководство. Рисование заполненного эллипса в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-ellipse-on-a-windows-form.md)