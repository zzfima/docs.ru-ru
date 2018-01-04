---
title: "Сглаживание прямых и кривых линий"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b8552f185a93b688555dbcfab3da9d28d9bfde6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="antialiasing-with-lines-and-curves"></a>Сглаживание прямых и кривых линий
При использовании [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] для рисования линии, предоставляют начальную и конечную точки линии, но вам не требуется задать любые сведения об отдельных точках в строке. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]работает в сочетании с программным обеспечением драйвера экрана, чтобы определить, какие точек будет включена для отображения в строке для каждого конкретного устройства отображения.  
  
## <a name="aliasing"></a>Совмещение имен  
 Попробуйте прямо красная линия, идущий от точки (4, 2) в точку (16, 10). Предположим системы координат расположен в верхнем левом углу, а единицей измерения является пикселя. Также предположим, на который указывает ось x вправо, а ось y точки вниз. Ниже показано увеличенное изображение красной линии, нарисованной на многоцветном фоне.  
  
 ![Линия, без сглаживания](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.gif "AboutGdip02_Art33")  
  
 Красные пиксели, составляющие линию, непрозрачны. В строке нет отсутствуют частично прозрачные точки. Этот тип отрисовки линии делает массивов оформление и строке похож на лестнице. Этот метод представления линии называется Совмещение имен; лестнице является псевдонимом линия.  
  
## <a name="antialiasing"></a>Сглаживание  
 Более сложные способы отрисовки прямых линий заключаются в использовании частично прозрачных точек наряду с непрозрачными. Задается пикселей чисто красный цвет, либо смешение красного и цвет фона, в зависимости от того, насколько близко эти строки. Этот тип визуализации называется сглаживания и результаты в строке, которая человеческого глаза они выглядели более гладкой. Ниже показано, как несколько точек смешиваются с цветом фона для образования сглаженной линии.  
  
 ![Сглаживание прямой линии](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.gif "AboutGdip02_Art34")  
  
 Сглаживание, также называемый сглаживания, можно также применять для кривых. На следующем рисунке увеличенное изображение сглаженного эллипса.  
  
 ![Сглаживание кривых](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.gif "AboutGdip02_Art35")  
  
 Ниже показан тот же эллипс в натуральную величину, без сглаживания и один раз с помощью сглаживания.  
  
 ![Пример сглаживания](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02_Art36")  
  
 Рисование линий и кривых с использованием сглаживания, создайте экземпляр <xref:System.Drawing.Graphics> и присвоить его <xref:System.Drawing.Graphics.SmoothingMode%2A> свойства <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> или <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>. Затем вызовите один из методов рисования этого же <xref:System.Drawing.Graphics> класса.  
  
 [!code-csharp[LinesCurvesAndShapes#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>  
 [Линии, кривые и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Практическое руководство. Сглаживание текста](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)
