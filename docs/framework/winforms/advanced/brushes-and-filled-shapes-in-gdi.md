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
ms.openlocfilehash: 45ef0b5920e43300e047d363149ea10a7833477b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912234"
---
# <a name="brushes-and-filled-shapes-in-gdi"></a>Кисти и закрашенные фигуры в GDI+
Замкнутая фигура, например прямоугольник или эллипс, состоит из контура и внутренней части. Контур рисуется с помощью пера, а внутренняя часть заполняется кистью. Интерфейс GDI+ предоставляет несколько классов кистей для заполнения внутренних областей замкнутых <xref:System.Drawing.SolidBrush>фигур <xref:System.Drawing.Drawing2D.HatchBrush>: <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>,, <xref:System.Drawing.Drawing2D.PathGradientBrush>и. Все эти классы наследуются от <xref:System.Drawing.Brush> класса. На следующем рисунке показан прямоугольник, заполненный сплошной кистью, и эллипс, заполненный штриховым кистью.  
  
 ![Заполненные фигуры](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")  
  
## <a name="solid-brushes"></a>Сплошные кисти  
 Для заполнения замкнутой фигуры необходим экземпляр <xref:System.Drawing.Graphics> класса <xref:System.Drawing.Brush>и. Экземпляр <xref:System.Drawing.Graphics> класса предоставляет методы, такие как <xref:System.Drawing.Graphics.FillRectangle%2A> и <xref:System.Drawing.Graphics.FillEllipse%2A>, и <xref:System.Drawing.Brush> сохраняет атрибуты заливки, такие как цвет и шаблон. <xref:System.Drawing.Brush> Передается в качестве одного из аргументов метода Fill. В следующем примере кода показано, как заполнить эллипс с помощью сплошного красного цвета.  
  
 [!code-csharp[LinesCurvesAndShapes#121](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
> В предыдущем примере кисть имеет тип <xref:System.Drawing.SolidBrush>, который наследует от. <xref:System.Drawing.Brush>  
  
## <a name="hatch-brushes"></a>Штриховые кисти  
 При заполнении фигуры штриховой кистью необходимо указать цвет переднего плана, цвет фона и стиль штриховки. Цвет переднего плана — это цвет штриховки.  
  
 [!code-csharp[LinesCurvesAndShapes#122](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 Интерфейс GDI+ предоставляет более 50 стилей штриховки; на следующем рисунке показаны три стиля: <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>и <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.  
  
 ![Заполненные фигуры](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")  
  
## <a name="texture-brushes"></a>Текстурные кисти  
 Текстурная кисть позволяет заполнить фигуру шаблоном, хранящимся в растровом изображении. Например, предположим, что следующий рисунок хранится в файле на диске с именем `MyTexture.bmp`.  
  
 ![Заполненная фигура](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")  
  
 В следующем примере кода показано, как заполнить эллипс путем повторения изображения, хранящегося в `MyTexture.bmp`.  
  
 [!code-csharp[LinesCurvesAndShapes#123](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 На следующем рисунке показан закрашенный эллипс.  
  
 ![Заполненная фигура](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")  
  
## <a name="gradient-brushes"></a>Градиентные кисти  
 GDI+ предоставляет два вида градиентных кистей: линейную и траекторию. Кисть линейного градиента можно использовать для заливки фигуры цветом, который постепенно меняется при перемещении по горизонтали, по вертикали или по диагонали. В следующем примере кода показано, как заполнить эллипс с помощью горизонтальной градиентной кисти, которая меняется с синего на зеленую при переходе от левого края эллипса к правому краю.  
  
 [!code-csharp[LinesCurvesAndShapes#124](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 На следующем рисунке показан закрашенный эллипс.  
  
 ![Заполненная фигура](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")  
  
 Кисть градиента контура может быть настроена на изменение цвета при перемещении от центра фигуры к границе.  
  
 ![Заполненная фигура](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")  
  
 Кисти градиента вдоль пути являются достаточно гибкими. Градиентная кисть, используемая для заливки треугольника на следующем рисунке, постепенно меняется от красного в центре к каждому из трех различных цветов в вершинах.  
  
 ![Заполненная фигура](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")  
  
## <a name="see-also"></a>См. также

- <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>
- <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [Линии, кривые и фигуры](lines-curves-and-shapes.md)
- [Практическое руководство. Нарисовать закрашенный прямоугольник в форме Windows](how-to-draw-a-filled-rectangle-on-a-windows-form.md)
- [Практическое руководство. Нарисовать закрашенный эллипс в форме Windows](how-to-draw-a-filled-ellipse-on-a-windows-form.md)
