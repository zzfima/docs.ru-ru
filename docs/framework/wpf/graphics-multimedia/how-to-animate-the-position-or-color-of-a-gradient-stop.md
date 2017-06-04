---
title: "Практическое руководство. Анимация положения или цвета ограничения градиента | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "анимация, цвет объектов GradientStop"
  - "анимация, положение объектов GradientStop"
  - "цвета, анимирование"
  - "GradientStop - объекты, анимация цвета"
  - "GradientStop - объекты, анимация положения"
  - "Положение, анимирование"
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Анимация положения или цвета ограничения градиента
В этом примере демонстрируется анимация свойств <xref:System.Windows.Media.GradientStop.Color%2A> и <xref:System.Windows.Media.GradientStop.Offset%2A> объектов <xref:System.Windows.Media.GradientStop>.  
  
## Пример  
 В следующем примере выполняется анимация трех ограничений градиента внутри объекта <xref:System.Windows.Media.LinearGradientBrush>.  В примере используются три анимации, в каждой из которых анимируется отдельное ограничение градиента.  
  
-   Первая анимация \(<xref:System.Windows.Media.Animation.DoubleAnimation>\) анимирует <xref:System.Windows.Media.GradientStop.Offset%2A> ограничения первого градиента от 0.0 до 1.0 и затем обратно до 0.0.  Таким образом, первый цвет градиента перемещается с левой стороны прямоугольника на правую и затем обратно на левую сторону.  
  
-   Во второй анимации \(<xref:System.Windows.Media.Animation.ColorAnimation>\) анимируется свойство <xref:System.Windows.Media.GradientStop.Color%2A> второго ограничения градиента от <xref:System.Windows.Media.Colors.Purple%2A> к <xref:System.Windows.Media.Colors.Yellow%2A> и затем обратно к <xref:System.Windows.Media.Colors.Purple%2A>.  В результате, средний цвет градиента изменяется от фиолетового до желтого и обратно.  
  
-   Третья анимация \(<xref:System.Windows.Media.Animation.ColorAnimation>\) анимирует прозрачность свойства <xref:System.Windows.Media.GradientStop.Color%2A> третьего ограничения градиента посредством установки значения \-1 и последующего возвращения к первоначальному значению.  В результате, третий цвет в градиенте плавно исчезает и затем снова становится непрозрачным.  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 В этом примере используется объект <xref:System.Windows.Media.LinearGradientBrush>, однако процесс будет тем же для анимации объектов <xref:System.Windows.Media.GradientStop> внутри объекта <xref:System.Windows.Media.RadialGradientBrush>.  
  
 Дополнительные примеры см. в разделе [Пример кистей](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
## См. также  
 <xref:System.Windows.Media.GradientStop>   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)