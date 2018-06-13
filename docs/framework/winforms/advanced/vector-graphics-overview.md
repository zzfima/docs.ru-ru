---
title: Общие сведения о векторной графике
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
ms.openlocfilehash: 31fec6d0d3769251d21783b4657d00b06431e942
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528353"
---
# <a name="vector-graphics-overview"></a>Общие сведения о векторной графике
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Рисование линии, прямоугольники и других фигур в системе координат. Можно выбрать из различных систем координат, но система координат по умолчанию имеет начала координат в левом верхнем углу ось x вправо, а ось y направлена вниз. Единица измерения, в системе координат по умолчанию является пиксель.  
  
## <a name="the-building-blocks-of-gdi"></a>Стандартные блоки GDI +  
 ![Векторная графика](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.gif "AboutGdip02_Art01")  
  
 Изображение на прямоугольный массив точек, называемых элементами изображения формируется мониторе компьютера. Количество пикселей, которые отображаются на экране, зависит от одного монитора к следующему и количество пикселей, которые отображаются на отдельных монитор обычно следует задавать в некоторой степени пользователем.  
  
 ![Векторная графика](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.gif "AboutGdip02_Art02")  
  
 При использовании [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] для рисования линии, прямоугольника или кривой, предоставляют определенные ключевые данные об элементе для отрисовки. Например можно указать строку, предоставляя две точки и прямоугольника можно указать, предоставляя точку, высотой и шириной. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] работает в сочетании с программным обеспечением драйвера экрана, чтобы определить, какие точек должен быть включен для отображения линии, прямоугольника или кривой. На следующем рисунке пиксели, которые включены для отображения линии с точки (4, 2) в точку ("12", "8").  
  
 ![Векторная графика](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.gif "AboutGdip02_Art03")  
  
 Со временем некоторые основные стандартные блоки оказались наиболее полезен при создании двухмерных изображений. Эти блоки, которые поддерживаются системой [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], приведены в следующем списке:  
  
-   Прямые линии  
  
-   Прямоугольники  
  
-   Многоточие  
  
-   Дуги  
  
-   Многоугольники  
  
-   Фундаментальные сплайны  
  
-   сплайны Безье  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a>Методы для рисования с помощью графических объектов  
 <xref:System.Drawing.Graphics> Класса в [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] предоставляет следующие методы для рисования элементов в списке выше: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (для фундаментальные сплайны) и <xref:System.Drawing.Graphics.DrawBezier%2A>. Каждый из этих методов перегружена; то есть каждый метод поддерживает несколько различными списками параметров. Например, один из вариантов <xref:System.Drawing.Graphics.DrawLine%2A> метод получает <xref:System.Drawing.Pen> объекта и четырех целых чисел, а другой вариант <xref:System.Drawing.Graphics.DrawLine%2A> метод получает <xref:System.Drawing.Pen> и два <xref:System.Drawing.Point> объектов.  
  
 Методы для рисования линии, прямоугольники и сплайнов Безье существуют вспомогательные методы, выполняющие рисование нескольких элементов за один вызов: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, и <xref:System.Drawing.Graphics.DrawBeziers%2A>. Кроме того <xref:System.Drawing.Graphics.DrawCurve%2A> метод имеет вспомогательный метод, <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, что указывают закрывает кривую путем соединения с первой конечной точки кривой.  
  
 Все методы для рисования <xref:System.Drawing.Graphics> класса работы в сочетании с <xref:System.Drawing.Pen> объекта. Чтобы нарисовать любой элемент, необходимо создать по крайней мере два объекта: <xref:System.Drawing.Graphics> объекта и <xref:System.Drawing.Pen> объекта. <xref:System.Drawing.Pen> Объект хранит атрибуты, такие как толщины и цвета для отображения элемента. <xref:System.Drawing.Pen> Объекта передается в качестве одного из аргументов метод рисования. Например, один из вариантов <xref:System.Drawing.Graphics.DrawLine%2A> метод получает <xref:System.Drawing.Pen> объекта и четырех целых чисел, как показано в следующем примере рисование прямоугольника с шириной 100, высотой 50 и координатами верхнего левого угла (20, 10):  
  
 [!code-csharp[LinesCurvesAndShapes#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [Линии, кривые и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Практическое руководство. Создание графических объектов для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
