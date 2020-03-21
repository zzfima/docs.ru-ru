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
ms.openlocfilehash: cf4dc558c008fb8adfc327a6a894a428e985df03
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182633"
---
# <a name="how-to-create-a-path-gradient"></a>Практическое руководство. Создание градиента вдоль контура
Класс <xref:System.Drawing.Drawing2D.PathGradientBrush> позволяет настроить способ заполнения формы с постепенным изменением цветов. Например, можно указать один цвет для центра пути и другой цвет для границы пути. Вы также можете указать отдельные цвета для каждой из нескольких точек вдоль границы пути.  
  
> [!NOTE]
> В GDI, путь представляет собой последовательность линий <xref:System.Drawing.Drawing2D.GraphicsPath> и кривых, поддерживаемых объектом. Для получения более подробной информации о путях GDI, см [Графика Пути в GDI](graphics-paths-in-gdi.md) и [построения и рисования Пути](constructing-and-drawing-paths.md).  

Примерами этой статьи являются методы, которые <xref:System.Windows.Forms.Control.Paint> вызываются из обработчика событий элемента управления.  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>Заполнить эллипс градиентом пути  
  
- Следующий пример заполняет эллипс аттестации кистью градиента пути. Центральный цвет установлен на синий и пограничный цвет установлен на аква. На следующей иллюстрации показан заполненный эллипс.  
  
     ![Путь градиента заполняет эллипс.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     По умолчанию кисть градиента пути не выходит за пределы пути. Если вы используете кисть градиента пути для заполнения фигуры, которая выходит за пределы пути, область экрана за пределами пути не будет заполнена.  
  
     Следующая иллюстрация показывает, что <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> произойдет, если `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`вы измените вызов в следующем коде на:  
  
     ![Путь градиента простирался за пределы пути.](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     Предыдущий пример кода предназначен для использования с формами Windows, и он требует <xref:System.Windows.Forms.PaintEventArgs> e, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
### <a name="to-specify-points-on-the-boundary"></a>Указать точки на границе  
  
- Следующий пример строит кисть градиента пути из звездообразного пути. Код устанавливает <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> свойство, которое устанавливает цвет на центроид звезды на красный цвет. Затем код устанавливает <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> свойство для указания различных цветов (хранящихся в массиве) `colors` в отдельных точках массива. `points` Окончательное кодовое заявление заполняет звездообразный путь кистью градиента пути.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- Следующий пример рисует градиент <xref:System.Drawing.Drawing2D.GraphicsPath> пути без объекта в коде. Конкретный <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> конструктор в примере получает массив точек, <xref:System.Drawing.Drawing2D.GraphicsPath> но не требует объекта. Кроме того, <xref:System.Drawing.Drawing2D.PathGradientBrush> обратите внимание, что используется для заполнения прямоугольника, а не путь. Прямоугольник больше, чем замкнутый путь, используемый для определения кисти, поэтому некоторые прямоугольники не окрашены кистью. На следующей иллюстрации показан прямоугольник (пунктирная линия) и часть прямоугольника, окрашенная кистью градиента пути:
  
     ![Градиентная часть окрашена кистью градиента пути.](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>Настройка градиента пути  
  
- Один из способов настройки кисти <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> градиента пути — установить ее свойство. Шкалы фокуса указывают внутренний путь, который находится внутри основного пути. Цвет центра отображается повсюду внутри этого внутреннего пути, а не только в центральной точке.  
  
     Следующий пример создает кисть градиента пути на основе эллиптической траектории. Код устанавливает цвет границы до синего, устанавливает центральный цвет аква, а затем использует кисть градиента пути для заполнения эллиптической траектории.  
  
     Далее код устанавливает шкалы фокуса кисти градиента пути. Шкала фокусировки x установлена на уровне 0,3, а шкала фокусировки y - 0,8. Код вызывает <xref:System.Drawing.Graphics.TranslateTransform%2A> метод <xref:System.Drawing.Graphics> объекта так, чтобы <xref:System.Drawing.Graphics.FillPath%2A> последующий вызов заполнял эллипс, который находится справа от первого эллипса.  
  
     Чтобы увидеть эффект фокус-шкалы, представьте себе небольшой эллипс, который разделяет его центр с основным эллипсом. Небольшой (внутренний) эллипс является основным эллипсом, масштабированным (о его центре) горизонтально в 0,3 и вертикально в 0,8. При переходе от границы внешнего эллипса к границе внутреннего эллипса цвет постепенно меняется от синего к аква. При перемещении от границы внутреннего эллипса к общему центру цвет остается аква.  
  
     На рисунке ниже показан результат выполнения кода. Эллипс слева аква только в центральной точке. Эллипс справа - это аква повсюду внутри внутреннего пути.  
  
 ![Градиентный эффект масштабов фокусировки](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>Настройка с интерполяцией  
  
- Другой способ настройки кисти градиента пути — это указать массив цветов интерполяции и массив позиций интерполяции.  
  
     Следующий пример создает кисть градиента пути на основе треугольника. Код устанавливает <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> свойство кисти градиента пути для определения массива цветов интерполяции (темно-зеленый, аква, синий) и массива позиций интерполяции (0, 0,25, 1). При переходе от границы треугольника к центральной точке цвет постепенно меняется от темно-зеленого к аква, а затем от аква к синему. Переход от темно-зеленого к аква происходит в 25 процентах расстояния от темно-зеленого до синего.  
  
     На следующей иллюстрации показан треугольник, заполненный кистью градиента пользовательского пути.  
  
     ![Треугольник, наполненный пользовательской кистью градиента пути.](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>Установить центральную точку  
  
- По умолчанию центральная точка кисти градиента пути находится в центроида пути, используемого для построения кисти. Вы можете изменить расположение центральной точки, установив свойство <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> <xref:System.Drawing.Drawing2D.PathGradientBrush> класса.  
  
     Следующий пример создает кисть градиента пути на основе эллипса. Центр эллипса находится на уровне (70, 35), но центральная точка кисти градиента пути установлена на (120, 40).  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     На следующей иллюстрации показан заполненный эллипс и центральная точка градиентной кисти пути:  
  
     ![Путь градиента с заполненным эллипсом и центральной точкой.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- Можно установить центральную точку кисти градиента пути в место за пределами пути, которое использовалось для построения кисти. Следующий пример заменяет вызов <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> для установки свойства в предыдущем коде.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     Следующая иллюстрация показывает выход с этим изменением:  
  
     ![Путь градиента с центральной точкой за пределами пути.](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     На предыдущей иллюстрации точки в крайнем правом направлении эллипса не являются чисто синими (хотя они очень близки). Цвета в градиенте расположены так, как если бы заливка достигла точки (145, 35), где цвет был бы чисто синим (0, 0, 255). Но заливка никогда не достигает (145, 35), потому что градиент пути кисти краски только внутри его пути.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущие примеры предназначены для использования с <xref:System.Windows.Forms.PaintEventArgs> `e`формами Windows, и <xref:System.Windows.Forms.Control.Paint> они требуют, который является параметром обработчика событий.  
  
## <a name="see-also"></a>См. также раздел

- [Заливка фигур с помощью градиентной кисти](using-a-gradient-brush-to-fill-shapes.md)
