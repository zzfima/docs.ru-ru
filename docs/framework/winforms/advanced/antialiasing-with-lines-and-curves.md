---
title: Сглаживание прямых и кривых линий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
ms.openlocfilehash: 364dffe3b4b63e3a369f87dd851ab54a975f881a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496248"
---
# <a name="antialiasing-with-lines-and-curves"></a>Сглаживание прямых и кривых линий
При использовании [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Чтобы нарисовать линию, предоставляют начальную и конечную точку линии, но нет необходимости предоставлять данные об отдельных пикселях в строке. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] работает в сочетании с программным обеспечением драйвера экрана, чтобы определить, какие точек будет включена для отображения в строке на устройстве отображения.  
  
## <a name="aliasing"></a>Присвоение псевдонима  
 Рассмотрите возможность непосредственно красная линия, идущий от точки (4, 2) в точку (16, 10). Предположим, система координат расположен в левом верхнем углу и означает что единицы измерения пиксель. Также предполагается, что ось x обращена вправо, а ось y точек вниз. На следующем рисунке увеличенное изображение красной линии, рисуемой на многоцветном фоне.  
  
 ![Строка, без сглаживания](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.gif "AboutGdip02_Art33")  
  
 Красные пиксели, используемый для отображения линии, непрозрачный. В строке есть не частично прозрачных точек. Этот тип отрисовки линии делает зубчатой и строке похож на лестница. Этот метод представления линии называется Совмещение имен; лестница является псевдонимом для теоретической линии.  
  
## <a name="antialiasing"></a>Сглаживание  
 Более сложный прием для подготовки к просмотру строки заключаются в использовании частично прозрачных точек вместе с непрозрачными. Пиксели задаются чистый красный цвет, либо смешение красного и цвет фона, зависимости от того, насколько близко эти строки. Этот тип визуализации называется сглаживания и результаты в строке, которая человеческим глазом они выглядели более smooth. Ниже показано, как несколько точек смешиваются с цветом фона для образования сглаженной линии.  
  
 ![Сглаживание прямой линии](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.gif "AboutGdip02_Art34")  
  
 Сглаживание, также называемый сглаживание, могут также применяться к кривым. На следующем рисунке увеличенное изображение сглаженного эллипса.  
  
 ![Сглаживание кривых](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.gif "AboutGdip02_Art35")  
  
 Ниже показан тот же эллипс в натуральную величину, без применения и один раз с помощью сглаживания.  
  
 ![Пример сглаживания](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02_Art36")  
  
 Для рисования линий и кривых, использующих сглаживания, создайте экземпляр <xref:System.Drawing.Graphics> и присвоить его <xref:System.Drawing.Graphics.SmoothingMode%2A> свойства <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> или <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>. Затем вызовите один из методов рисования этого же <xref:System.Drawing.Graphics> класса.  
  
 [!code-csharp[LinesCurvesAndShapes#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>
- [Линии, кривые и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [Практическое руководство. Сглаживание текста](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)
