---
title: "Практическое руководство. Распределение времени для анимации с ключевыми кадрами | Microsoft Docs"
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
  - "ключевые кадры [WPF], учет времени"
  - "учет времени при анимации по ключевым кадрам"
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Распределение времени для анимации с ключевыми кадрами
В этом примере описывается порядок распределения времени полных кадров в анимации с полными кадрами.  Как и в других видах анимации, в анимации с полными кадрам используется свойство <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  Помимо определения продолжительности анимации, необходимо определить часть общего времени, выделяемую для каждого полного кадра.  Чтобы выделить время, определите объект <xref:System.Windows.Media.Animation.KeyTime> для каждого полного кадра в анимации.  
  
 Объект <xref:System.Windows.Media.Animation.KeyTime> для каждого полного кадра определяет время завершения полного кадра \(продолжительность воспроизведения полного кадра не указывается\).  Можно определить объект <xref:System.Windows.Media.Animation.KeyTime> в виде значения класса <xref:System.TimeSpan>, в виде процентного соотношения, а также в качестве специального значения свойства <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> или <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>.  
  
## Пример  
 В следующем примере объект <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> используется для анимации движения прямоугольника по экрану.  Для свойств KeyTime полных кадров устанавливаются значения <xref:System.TimeSpan>.  
  
 [!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
 [!code-vb[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
 [!code-xml[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]  
  
 На следующем рисунке показаны моменты достижения значений каждого полного кадра.  
  
 ![Ключевые значения достигаются за 3, 4 и 10 секунд](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm\_keyframe\_keytime1\_timespan")  
  
 В следующем примере описывается аналогичная анимация, в которой для свойств KeyTime полных кадров установлены значения в виде процентного соотношения.  
  
 [!code-csharp[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
 [!code-vb[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
 [!code-xml[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]  
  
 На следующем рисунке показаны моменты достижения значений каждого полного кадра.  
  
 ![Ключевые значения достигаются за 3, 4 и 10 секунд](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm\_keyframe\_keytime2\_percentage")  
  
 В следующем примере используются значения KeyTime <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>.  
  
 [!code-csharp[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
 [!code-vb[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
 [!code-xml[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]  
  
 На следующем рисунке показаны моменты достижения значений каждого полного кадра.  
  
 ![Ключевые значение достигаются за 3,3; 6,6, и 9,9 секунды](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm\_keyframe\_keytime3\_uniform")  
  
 В последнем примере используются значения KeyTime <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>.  
  
 [!code-csharp[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
 [!code-vb[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
 [!code-xml[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]  
  
 На следующем рисунке показаны моменты достижения значений каждого полного кадра.  
  
 ![Ключевые значения достигаются за 0, 5 и 10 секунд](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm\_keyframe\_keytime4\_paced")  
  
 В целях упрощения, в версиях кода этого примера используются локальные анимации, а не раскадровки, поскольку к одному свойству применяется только одна анимация. При необходимости можно изменить примеры для использования раскадровок.  Пример, в котором описывается объявление раскадровки в коде, см. в разделе [Анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).  
  
 Полный пример см. на веб\-странице [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  Дополнительные сведения об анимации с полными кадрами см. в разделе [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
## См. также  
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)