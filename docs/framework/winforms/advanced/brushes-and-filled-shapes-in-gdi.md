---
title: Кисти и закрашенные фигуры в GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [Windows Forms], GDI+
- filled shapes [Windows Forms], GDI+
- shapes [Windows Forms], GDI+
- GDI+, brushes
- GDI+, filled shapes
- gradient brushes
- brushes [Windows Forms], gradient
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
ms.openlocfilehash: 9475518a5f0422e0eac1ec521088071bb4d1c885
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="brushes-and-filled-shapes-in-gdi"></a>Кисти и закрашенные фигуры в GDI+
Замкнутые фигуры, например прямоугольник или эллипса, состоит из структуры и внутренний. Контур рисуется с помощью пера и внутренняя область заполняется с использованием кисти. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] предоставляет несколько классов кисти для заливки замкнутых фигур: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, и <xref:System.Drawing.Drawing2D.PathGradientBrush>. Эти классы наследуются от <xref:System.Drawing.Brush> класса. На следующем рисунке прямоугольник с помощью сплошной кисти эллипса заливке а кистей штриховки.  
  
 ![Заполнить фигуры](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.gif "Aboutgdip02_art17")  
  
## <a name="solid-brushes"></a>Сплошной кисти  
 Чтобы залить замкнутую фигуру, требуется экземпляр <xref:System.Drawing.Graphics> класса и <xref:System.Drawing.Brush>. Экземпляр <xref:System.Drawing.Graphics> класс предоставляет методы, такие как <xref:System.Drawing.Graphics.FillRectangle%2A> и <xref:System.Drawing.Graphics.FillEllipse%2A>и <xref:System.Drawing.Brush> для хранения атрибутов, таких как цвета или узора заливки. <xref:System.Drawing.Brush> Передается в качестве одного из аргументов метода fill. В следующем примере кода показано, как заливка эллипса сплошным красным цветом.  
  
 [!code-csharp[LinesCurvesAndShapes#121](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  В приведенном выше примере кисть, которая принадлежит к типу <xref:System.Drawing.SolidBrush>, который наследует от <xref:System.Drawing.Brush>.  
  
## <a name="hatch-brushes"></a>Кистей штриховки  
 При заливке формы штриховой кистью указываются основной цвет, цвет фона и стиль штриховки. Цвет переднего плана — это цвет штриховки.  
  
 [!code-csharp[LinesCurvesAndShapes#122](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] предоставляет более 50 стилей штриховки. на следующем рисунке изображены три стиля, <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, и <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.  
  
 ![Заполнить фигуры](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.gif "Aboutgdip02_art18")  
  
## <a name="texture-brushes"></a>Текстурные кисти  
 С помощью кисти текстуры можно заливка фигуры с шаблоном, хранящихся в растровое изображение. Предположим, например, приведенный ниже рисунок хранится на диске в файле с именем `MyTexture.bmp`.  
  
 ![Заполнить форму](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.gif "Aboutgdip02_Art19")  
  
 В следующем примере кода показано, как заливка эллипса, повторив рисунка, сохраненного в `MyTexture.bmp`.  
  
 [!code-csharp[LinesCurvesAndShapes#123](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 На следующем рисунке закрашенный эллипс.  
  
 ![Заполнить форму](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.gif "AboutGdip02_Art20")  
  
## <a name="gradient-brushes"></a>Градиентные кисти  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] имеется два типа градиентных кистей: линейный и путь. Можно использовать линейной градиентной кисти для заливки фигуры цвет, который постепенно перемещении фигуры по горизонтали, по вертикали или по диагонали. В следующем примере кода показано, как заливка эллипса с использованием горизонтальной градиентной кисти, изменение от синего до зеленого при переходе от левого края эллипса по правому краю.  
  
 [!code-csharp[LinesCurvesAndShapes#124](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 На следующем рисунке закрашенный эллипс.  
  
 ![Заполнить форму](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.gif "AboutGdip02_Art21")  
  
 Кисти градиента вдоль пути можно настроить для изменения цвета при переходе от центра фигуры к ее границам.  
  
 ![Заполнить форму](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.gif "AboutGdip02_Art22")  
  
 Градиентные кисти пути обеспечивают высокую степень гибкости. Демонстрируется использование градиентной кисти для заливки треугольника в приведенном ниже рисунке, изменяющимся от красного в центре для каждого из трех различных цветов в вершинах.  
  
 ![Заполнить форму](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.gif "AboutGdip02_Art23")  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 [Линии, кривые и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Практическое руководство. Рисование заполненного прямоугольника в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-rectangle-on-a-windows-form.md)  
 [Практическое руководство. Рисование заполненного эллипса в Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-ellipse-on-a-windows-form.md)
