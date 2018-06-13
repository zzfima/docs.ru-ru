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
ms.openlocfilehash: a3a23d382e199b7ec70a8605041f7e464d1bffe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529170"
---
# <a name="how-to-create-a-path-gradient"></a>Практическое руководство. Создание градиента вдоль контура
<xref:System.Drawing.Drawing2D.PathGradientBrush> Позволяет настроить способ заливки фигуры плавно меняющимися цветами. Например можно указать один цвет для центра пути, а другой — для границы пути. Можно также определить отдельные цвета для каждой из нескольких точек на границе пути.  
  
> [!NOTE]
>  В [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], путь представляет собой последовательность линий и кривых, поддерживаемых <xref:System.Drawing.Drawing2D.GraphicsPath> объекта. Дополнительные сведения о [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] . в разделе пути, [контуры в GDI +](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md) и [Constructing и рисование контуров](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md).  
  
### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>Чтобы заполнить градиента вдоль контура эллипса  
  
-   В следующем примере заполняется эллипса с градиента вдоль пути. Центра установлен синий и имеет значение голубой цвет границ. На следующем рисунке закрашенный эллипс.  
  
     ![Градиент контура](../../../../docs/framework/winforms/advanced/media/pathgradient1.png "pathgradient1")  
  
     По умолчанию кисти градиента вдоль пути не расширяет за пределами границы пути. При использовании пути градиентной кисти для заливки фигуры, который выходит за границы пути области экрана за пределами контура не заполняется.  
  
     На следующем рисунке показано, что происходит при изменении <xref:System.Drawing.Graphics.FillEllipse%2A> вызов в следующий код в `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`.  
  
     ![Градиент контура](../../../../docs/framework/winforms/advanced/media/pathgradient2.png "pathgradient2")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     Предыдущий пример кода предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> e, который является параметром для <xref:System.Windows.Forms.PaintEventHandler>.  
  
### <a name="to-specify-points-on-the-boundary"></a>Указание точек на границе  
  
-   В следующем примере создается Градиентная кисть путь из пути форме звезды. В коде устанавливается <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> свойства, которое задает цвет в центре звезды как красный. Затем устанавливается <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> свойство для задания различных цветов (хранятся в `colors` массива) для отдельных точек в `points` массива. Последняя инструкция кода заливку пути в форме звезды с градиента вдоль пути.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
-   В следующем примере рисуется градиента вдоль контура без <xref:System.Drawing.Drawing2D.GraphicsPath> объекта в коде. Конкретный <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> конструктор в примере получает массив точек, но не требует <xref:System.Drawing.Drawing2D.GraphicsPath> объекта. Кроме того, обратите внимание, что <xref:System.Drawing.Drawing2D.PathGradientBrush> используется для заливки прямоугольника, а не путь. Прямоугольник больше, чем замкнутый путь, используемый для задания кисти, поэтому часть прямоугольника не закрашивается кисти. На следующем рисунке прямоугольник (пунктирная линия) и часть прямоугольника, созданный при помощи кисти градиента вдоль пути.  
  
     ![Градиент](../../../../docs/framework/winforms/advanced/media/gradient4.png "gradient4")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>Чтобы настроить градиента вдоль контура  
  
-   Один из способов настройки кисти градиента контура является установка его <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> свойство. Это свойство определяет внутренний путь, находящаяся внутри основного пути. Для центра используется везде в пределах этого внутреннего пути, а не только в центральной точке.  
  
     В следующем примере создается градиентной кисти путь на основе эллиптических пути. Код задает границу цвет на синий, задает голубой цвет центра и затем использует путь градиентной кисти для заливки голубой.  
  
     Далее в коде устанавливаются коэффициенты масштабирования кисти градиента вдоль пути. Коэффициент масштабирования по x равно 0,3, а коэффициент масштабирования по y имеет значение 0,8. Этот код вызывает <xref:System.Drawing.Graphics.TranslateTransform%2A> метод <xref:System.Drawing.Graphics> объекта, чтобы в последующий вызов для <xref:System.Drawing.Graphics.FillPath%2A> осуществляется заливка эллипса, который располагается справа от первого эллипса.  
  
     Чтобы увидеть эффект применения коэффициентов масштабирования, представьте небольшой эллипса, который совпадает с основной эллипс центром. Маленький (внутренний) эллипс представляет собой основной эллипс, горизонтально масштабировать (относительно своего центра) с коэффициентом 0,3 и по вертикали с коэффициентом 0,8. При перемещении от границы внешнего эллипса к границе внутреннего эллипса цвет плавно меняется от синего голубой. При перемещении от границы внутреннего эллипса к общему центру голубой цвет сохраняется.  
  
     На рисунке ниже показан результат выполнения следующего кода. Эллипс в левой части — голубой цвет только в центральной точки. Эллипс в правой — голубой цвет везде в пределах внутреннего пути.  
  
 ![Градиент](../../../../docs/framework/winforms/advanced/media/focusscales1nogamma.png "focusscales1NoGamma")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>Настройка с интерполяцией  
  
-   Другим способом настройки кисти градиента вдоль пути является указание массива цветов интерполяции и массива позиций интерполяции.  
  
     В следующем примере создается на треугольник основе кисти градиента контура. В коде устанавливается <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> свойство кисти градиента контура для определения массива цветов интерполяции (темно-зеленый, голубой, синий) и массива позиций интерполяции (0, 0,25, 1). При перемещении от границы треугольника к центральной точке цвет плавно меняется от темно-зеленый голубой цвет, а затем из голубой цвет на синий. Изменение темно-зеленого цвета голубой происходит на 25 процентов расстояние от темно-зеленого на синий.  
  
     На следующем рисунке треугольник, заполненный с градиентной кисти пользовательский путь.  
  
     ![Градиент контура](../../../../docs/framework/winforms/advanced/media/pathgradient4.png "pathgradient4")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>Чтобы задать центральную точку  
  
-   По умолчанию центральной точки кисти градиента контура является центр контура, используемого для создания кисти. Расположение центральной точки можно изменить, задав <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> свойство <xref:System.Drawing.Drawing2D.PathGradientBrush> класса.  
  
     В следующем примере создается на основе эллиптического кисти градиента контура. Центром эллипса является точка (70, 35), но центральной точки кисти градиента вдоль пути устанавливается (120, 40).  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     На следующем рисунке закрашенный эллипс и центральная точка кисти градиента вдоль пути.  
  
     ![Градиент контура](../../../../docs/framework/winforms/advanced/media/pathgradient5.png "pathgradient5")  
  
-   Центральная точка кисти градиента вдоль пути можно задать расположение за пределами пути, который использовался для создания кисти. В следующем примере заменяется вызов для установки <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> свойство в предыдущем примере кода.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     Ниже показан результат этого изменения.  
  
     ![Градиент контура](../../../../docs/framework/winforms/advanced/media/pathgradient6.png "pathgradient6")  
  
     На предыдущем рисунке в крайней правой точки эллипса не являются чисто синими (хотя они очень близкие). Цвета в градиенте располагаются, как если бы заливки достиг точки (145, 35), где цвет является чисто синим (0, 0, 255). Никогда не дойти до точки (145, 35) потому что градиентной кисти путь заливку только в пределах заданного пути.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и требуют <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий.  
  
## <a name="see-also"></a>См. также  
 [Заливка фигур с помощью градиентной кисти](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
