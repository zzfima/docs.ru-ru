---
title: Практическое руководство. Создание градиента вдоль контура
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- path gradients [Windows Forms], creating
- gradients [Windows Forms], creating path
- graphics paths [Windows Forms], creating gradient
ms.assetid: 1948e834-e104-481c-b71d-d8aa9e4d106e
ms.openlocfilehash: 8399a56fca87704e10456a4cf8109d7c80d4db45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964404"
---
# <a name="how-to-create-a-path-gradient"></a>Практическое руководство. Создание градиента вдоль контура
<xref:System.Drawing.Drawing2D.PathGradientBrush> Класс позволяет настроить способ заливки фигуры с постепенно изменяющимися цветами. Например, можно указать один цвет для центра контура и другой цвет для границы пути. Можно также указать отдельные цвета для каждой из нескольких точек вдоль границы пути.  
  
> [!NOTE]
> В GDI+ путь представляет собой последовательность линий и кривых, <xref:System.Drawing.Drawing2D.GraphicsPath> обслуживаемых объектом. Дополнительные сведения о путях GDI+ см. [в разделе графические пути в GDI+](graphics-paths-in-gdi.md) , [Создание и рисование контуров](constructing-and-drawing-paths.md).  

Примеры в этой статье — это методы, которые вызываются из обработчика <xref:System.Windows.Forms.Control.Paint> событий элемента управления.  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>Заливка эллипса с помощью градиента контура  
  
- В следующем примере заливка эллипса осуществляется с помощью кисти градиента вдоль пути. Центральная цвет устанавливается синим цветом, а цвет границы — голубым. На следующем рисунке показан закрашенный эллипс.  
  
     ![Градиентный контур заполняет эллипс.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     По умолчанию кисть градиента контура не выходит за границы пути. При использовании кисти градиента вдоль пути для заливки фигуры, выходящей за пределы контура, область экрана за пределами контура не будет заполнена.  
  
     На следующем рисунке показано, что происходит при изменении <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> вызова в следующем коде на: `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`  
  
     ![Градиентный путь, превышающий границу пути.](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     Предыдущий пример кода предназначен для использования с Windows Forms, и для него требуется <xref:System.Windows.Forms.PaintEventArgs> e, который является <xref:System.Windows.Forms.PaintEventHandler>параметром.  
  
### <a name="to-specify-points-on-the-boundary"></a>Указание точек на границе  
  
- В следующем примере кисть градиента контура строится на основе траектории в форме звезды. В коде задается <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> свойство, которое устанавливает красный цвет в центроид звезды. Затем в коде задается <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> свойство для указания различных цветов (хранящихся `colors` в массиве) в отдельных точках `points` массива. Окончательный оператор Code заполняет траекторию в форме звезды с помощью кисти градиента вдоль пути.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- В следующем примере градиент контура рисуется без <xref:System.Drawing.Drawing2D.GraphicsPath> объекта в коде. Определенный <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> конструктор в примере получает массив точек, но не <xref:System.Drawing.Drawing2D.GraphicsPath> требует объекта. Кроме того, обратите <xref:System.Drawing.Drawing2D.PathGradientBrush> внимание, что объект используется для заполнения прямоугольника, а не контура. Прямоугольник больше, чем замкнутый контур, используемый для определения кисти, поэтому часть прямоугольника не закрашивается кистью. На следующем рисунке показан прямоугольник (пунктирная линия) и часть прямоугольника, закрашенная кистью градиента вдоль пути: 
  
     ![Часть градиента, закрашенная кистью градиента вдоль пути.](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>Настройка градиента контура  
  
- Одним из способов настройки кисти градиента контура является установка ее <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> свойства. Масштабирование фокуса определяет внутренний путь, который находится внутри основного пути. Центральный цвет отображается везде внутри этого внутреннего пути, а не только в центральной точке.  
  
     В следующем примере создается кисть градиента контура на основе эллиптического пути. Код устанавливает синий цвет границы, устанавливает цвет центрального цвета в голубой, а затем использует кисть градиента вдоль пути для заполнения эллиптического контура.  
  
     Затем код задает масштабное масштабирование кисти градиента вдоль пути. Масштаб фокуса x устанавливается равным 0,3, а масштаб фокуса по оси y устанавливается равным 0,8. Код вызывает <xref:System.Drawing.Graphics.TranslateTransform%2A> метод <xref:System.Drawing.Graphics> объекта <xref:System.Drawing.Graphics.FillPath%2A> , чтобы последующий вызов заполнил эллипс, расположенный справа от первого эллипса.  
  
     Чтобы увидеть результат масштабирования фокуса, представьте себе маленький эллипс, который использует его центр с основным эллипсом. Маленький (внутренний) эллипс — это основной эллипс (по центру) по горизонтали на 0,3 и вертикальный коэффициент, равный 0,8. При переходе от границы внешнего эллипса к границе внутреннего эллипса цвет постепенно меняется от синего к голубому. При переходе от границы внутреннего эллипса к общему центру цвет остается голубым.  
  
     На рисунке ниже показан результат выполнения кода. Эллипс слева имеет голубой цвет только в центральной точке. Эллипс справа — это голубой цвет везде внутри внутреннего пути.  
  
 ![Градиентный эффекты шкалы фокуса](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>Настройка с интерполяцией  
  
- Другой способ настройки кисти градиента контура заключается в том, чтобы указать массив цветов интерполяции и массив позиций интерполяции.  
  
     В следующем примере создается кисть градиента контура на основе треугольника. Код задает <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> свойство кисти градиента контура, чтобы указать массив цветов интерполяции (темно-зеленый, голубой, синий) и массив позиций интерполяции (0, 0,25, 1). При переходе от границы треугольника к центральной точке цвет меняется постепенно с темно-зеленого на голубой, а затем с голубого на синий. Изменение с темно-зеленого на голубой происходит в 25% от темно-зеленого до синего.  
  
     На следующем рисунке показан треугольник, закрашенный с помощью настраиваемой кисти градиента пути.  
  
     ![Треугольник заполняется настраиваемой градиентной кистью пути.](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>Задание центральной точки  
  
- По умолчанию Центральная точка кисти градиента контура находится в центроид пути, используемого для создания кисти. Расположение центральной точки можно изменить, задав <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> свойство <xref:System.Drawing.Drawing2D.PathGradientBrush> класса.  
  
     В следующем примере создается кисть градиента контура на основе эллипса. Центр эллипса находится в точке (70, 35), но Центральная точка кисти градиента контура имеет значение (120, 40).  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     На следующем рисунке показан закрашенный эллипс и Центральная точка кисти градиента вдоль пути:  
  
     ![Градиентный контур с закрашенным эллипсом и Центральной точкой.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- Можно задать центральную точку кисти градиента контура, расположенную за пределами пути, который использовался для создания кисти. В следующем примере вызывается замена вызова для задания <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> свойства в предыдущем коде.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     На следующем рисунке показаны выходные данные с этим изменением:  
  
     ![Градиентный путь с центральной точкой за пределами пути.](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     На предыдущем рисунке точки в дальней правой части эллипса не являются чисто синими (хотя они очень близки). Цвета в градиенте размещаются, как если бы заливка достигла точки (145, 35), где цвет будет чистым синим (0, 0, 255). Но заливка никогда не достигает (145, 35), так как кисть градиента контура рисует только внутри ее контура.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Приведенные выше примеры предназначены для использования с Windows Forms и им требуется <xref:System.Windows.Forms.PaintEventArgs> `e`, который <xref:System.Windows.Forms.Control.Paint> является параметром обработчика событий.  
  
## <a name="see-also"></a>См. также

- [Заливка фигур с помощью градиентной кисти](using-a-gradient-brush-to-fill-shapes.md)
