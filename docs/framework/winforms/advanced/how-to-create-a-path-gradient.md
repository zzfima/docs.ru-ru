---
title: "Практическое руководство. Создание градиента вдоль контура | Microsoft Docs"
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
  - "градиенты, создание контура"
  - "контуры, создание градиента"
  - "градиенты контура, создание"
ms.assetid: 1948e834-e104-481c-b71d-d8aa9e4d106e
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Практическое руководство. Создание градиента вдоль контура
Класс <xref:System.Drawing.Drawing2D.PathGradientBrush> позволяет настраивать способ заливки фигуры плавно меняющимися цветами.  Например, можно указать один цвет для центра контура, а другой — для границы контура.  Можно также определить отдельные цвета для каждой из нескольких точек на границе контура.  
  
> [!NOTE]
>  В интерфейсе [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] контур представляет собой последовательность линий и кривых, поддерживаемых объектом <xref:System.Drawing.Drawing2D.GraphicsPath>.  Дополнительные сведения о контурах [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] см. в разделах [Контуры в GDI\+](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md) и [Построение и рисование контуров](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md).  
  
### Заливка эллипса с использованием градиента контура  
  
-   В следующем примере осуществляется заливка эллипса с помощью кисти градиента контура.  Для центра установлен синий цвет, а для границы — голубой.  Эллипс после заливки представлен на следующем рисунке.  
  
     ![Градиент контура](../../../../docs/framework/winforms/advanced/media/pathgradient1.png "pathgradient1")  
  
     По умолчанию кисть градиента контура не расширяется на области вне границы этого контура.  Если кисть градиента контура используется для заливки фигуры, которая заходит за границу данного контура, области вне границы контура не заливаются.  
  
     На следующей иллюстрации показано, что происходит при изменении вызова <xref:System.Drawing.Graphics.FillEllipse%2A> в следующем коде на `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`.  
  
     ![Градиент контура](../../../../docs/framework/winforms/advanced/media/pathgradient2.png "pathgradient2")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     Предыдущий пример кода предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs>, являющийся параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
### Указание точек на границе  
  
-   В следующем примере кисть градиента контура строится на основе контура в форме звезды.  В коде устанавливается свойство <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A>, что определяет цвет в центре звезды как красный.  Затем устанавливается свойство <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A>, чтобы определить различные цвета \(представленные в массиве `colors`\) для отдельных точек, которые хранятся в массиве `points`.  Последняя инструкция кода осуществляет заливку контура в форме звезды с помощью кисти градиента контура.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
-   В следующем примере выполняется рисование градиента контура без использования в коде объекта <xref:System.Drawing.Drawing2D.GraphicsPath>.  Используемый в примере конструктор <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> получает массив точек и не нуждается в объекте <xref:System.Drawing.Drawing2D.GraphicsPath>.  Кроме того, следует обратить внимание, что кисть <xref:System.Drawing.Drawing2D.PathGradientBrush> используется для заливки прямоугольника, а не контура.  Прямоугольник больше, чем замкнутый контур, используемый для задания кисти, поэтому часть прямоугольника не закрашивается этой кистью.  На следующем рисунке показаны прямоугольник \(пунктирная линия\) и его часть, закрашенная с помощью кисти градиента контура.  
  
     ![Градиент](../../../../docs/framework/winforms/advanced/media/gradient4.png "gradient4")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### Настройка градиента контура  
  
-   Одним из способов настройки кисти градиента контура является установка ее свойства <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A>.  Это свойство определяет внутренний контур, лежащий внутри основного контура.  Цвет центра используется везде в пределах этого внутреннего контура, а не только в центральной точке.  
  
     В следующем примере кисть градиента контура строится на основе эллипса.  В коде в качестве цвета границы устанавливается синий, центрального цвета — голубой; затем кисть градиента контура используется для заливки эллиптического контура.  
  
     Далее в коде устанавливаются коэффициенты масштабирования кисти градиента контура.  Коэффициент масштабирования по шкале x устанавливается равным 0,3, а коэффициент масштабирования по шкале y — 0,8.  Код вызывает метод <xref:System.Drawing.Graphics.TranslateTransform%2A> объекта <xref:System.Drawing.Graphics>, чтобы при последующем вызове метода <xref:System.Drawing.Graphics.FillPath%2A> заполнился эллипс, расположенный справа от первого эллипса.  
  
     Чтобы увидеть эффект применения коэффициентов масштабирования, представьте маленький эллипс, центр которого совпадает с центром основного эллипса.  Маленький \(внутренний\) эллипс представляет собой основной эллипс, масштабированный \(относительно своего центра\) с коэффициентом 0,3 по горизонтали и с коэффициентом 0,8 по вертикали.  По мере движения от границы внешнего эллипса к границе внутреннего эллипса цвет плавно меняется от синего к голубому.  При перемещении от границы внутреннего эллипса к общему центру эллипсов цвет остается тем же \(голубым\).  
  
     На следующем рисунке показан результат выполнения приведенного ниже кода.  Эллипс в левой части рисунка имеет голубой цвет только в своем центре.  Эллипс в правой части рисунка содержит голубой цвет везде в пределах внутреннего контура.  
  
 ![Градиент](../../../../docs/framework/winforms/advanced/media/focusscales1nogamma.png "focusscales1NoGamma")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### Настройка с интерполяцией  
  
-   Другим способом настройки кисти градиента контура является указание массива цветов интерполяции и массива положений интерполяции.  
  
     В следующем примере кисть градиента контура строится на основе контура треугольной формы.  В коде устанавливается свойство <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> кисти градиента контура для определения массива цветов интерполяции \(темно\-зеленый, голубой, синий\) и массива положений интерполяции \(0, 0,25, 1\).  По мере движения от границы треугольника к его центру цвет плавно меняется от темно\-зеленого к голубому, а затем от голубого к синему.  Изменение темно\-зеленого цвета на голубой происходит на 25 процентах расстояния между точками с темно\-зеленым и синим цветами.  
  
     На следующем рисунке представлен треугольник, залитый с помощью специально настроенной кисти градиента контура.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### Задание центральной точки  
  
-   По умолчанию центральной точкой кисти градиента контура является центр контура, используемого при создании этой кисти.  Положение центральной точки можно изменить, установив значение свойства <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> класса <xref:System.Drawing.Drawing2D.PathGradientBrush>.  
  
     В следующем примере кисть градиента контура строится на основе эллиптического контура.  Центром эллипса является точка \(70, 35\), но в качестве центральной точки кисти градиента контура устанавливается \(120, 40\).  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     На следующем рисунке представлены залитый эллипс и центральная точка кисти градиента контура.  
  
     ![Градиент контура](../../../../docs/framework/winforms/advanced/media/pathgradient5.png "pathgradient5")  
  
-   В качестве центральной точки кисти градиента контура можно установить точку, которая лежит вне контура, который использовался для создания кисти.  В следующем примере показан код, заменяющий участок предыдущего кода, в котором устанавливается свойство <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A>.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     На следующем рисунке представлен результат выполнения кода, измененного указанным образом.  
  
     ![Градиент контура](../../../../docs/framework/winforms/advanced/media/pathgradient6.png "pathgradient6")  
  
     На приведенном выше рисунке точки в правой части эллипса не являются чисто синими \(хотя они очень близки к этому\).  Цвета в градиенте располагаются так, как будто процесс заливки дошел до точки \(145, 35\), цвет которой является чисто синим \(0, 0, 255\).  В действительности же этот процесс не может дойти до точки \(145, 35\), потому что кисть градиента контура осуществляет заливку только в пределах заданного контура.  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 [Заливка фигур с помощью градиентной кисти](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)