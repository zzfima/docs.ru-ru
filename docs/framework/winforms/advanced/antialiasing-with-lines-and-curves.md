---
title: "Сглаживание прямых и кривых линий | Microsoft Docs"
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
  - "сглаживание"
  - "сглаживание, режимы сглаживания"
  - "GDI+, сглаживание"
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Сглаживание прямых и кривых линий
При рисовании линии с помощью интерфейса [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] для задания положения линии нужно указывать только начальную и конечную точку, а предоставлять данные о промежуточных пикселях линии не нужно.  Интерфейс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] взаимодействует с программным обеспечением драйвера экрана, чтобы определить, какие пиксели экрана должны быть высвечены, чтобы на конкретном устройстве возникло изображение линии.  
  
## Неровности  
 Рассмотрим рисование прямой линии красного цвета из точки с координатами \(4, 2\) в точку с координатами \(16, 10\).  Предположим, что начало координат расположено в верхнем левом углу экрана, а единицей измерения является пиксель.  Также предположим, что ось X направлена вправо, а ось Y — вниз.  На приведенном ниже рисунке представлено увеличенное изображение красной линии, нарисованной на многоцветном фоне.  
  
 ![Прямая линия, без сглаживания](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.png "AboutGdip02\_Art33")  
  
 Красные пиксели, составляющие линию, непрозрачны.  В линии отсутствуют частично прозрачные пиксели.  Такой тип отрисовки линии делает ее неровной на вид, при определенном увеличении линия становится ступенчатой.  При таком подходе к представлению линии теоретическая линия приближается ступенчатой последовательностью точек.  
  
## Сглаживание  
 Более сложные способы отрисовки прямых линий заключаются в использовании частично прозрачных пикселей наряду с абсолютно непрозрачными.  Для пикселей линии задается либо чистый красный цвет, либо смешение красного с цветом фона, в зависимости от того, насколько близки эти пиксели к линии.  Такой тип отрисовки линий называется сглаживанием, он позволяет отображать линии так, чтобы для человеческого глаза они выглядели более гладкими.  На приведенном ниже рисунке изображены несколько пикселей в, цвет которых смешивается с цветом фона для образования сглаженной линии.  
  
 ![Сглаживание прямой линии](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.png "AboutGdip02\_Art34")  
  
 Сглаживание можно также применять для кривых.  На приведенном ниже рисунке показано увеличенное изображение сглаженного эллипса.  
  
 ![Сглаживание кривых](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.png "AboutGdip02\_Art35")  
  
 На приведенном ниже рисунке тот же эллипс изображен в натуральную величину в двух вариантах — с применением и без применения сглаживания.  
  
 ![Пример сглаживания](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02\_Art36")  
  
 Чтобы рисовать прямые и кривые линии с использованием сглаживания, создайте экземпляр класса <xref:System.Drawing.Graphics> и присвойте его свойству <xref:System.Drawing.Graphics.SmoothingMode%2A> значение <xref:System.Drawing.Drawing2D.SmoothingMode> или <xref:System.Drawing.Drawing2D.SmoothingMode>.  После этого вызовите один из методов рисования этого же класса <xref:System.Drawing.Graphics>.  
  
 [!code-csharp[LinesCurvesAndShapes#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## См. также  
 <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=fullName>   
 [Прямые и кривые линии и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Практическое руководство. Сглаживание текста](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)