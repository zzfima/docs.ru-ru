---
title: "Практическое руководство. Накапливание значений анимации в повторяющихся циклах | Microsoft Docs"
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
  - "накапливание значений анимации в повторяющихся циклах"
  - "анимация, накапливание значений в повторяющихся циклах"
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Накапливание значений анимации в повторяющихся циклах
В этом примере показано использование свойства <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> для накапливания значений анимации в повторяющихся циклах.  
  
## Пример  
 Свойство <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> используется для накапливания базовых значений анимации в повторяющихся циклах.  Например, если задан повтор анимации 9 раз \(<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> \= "9x"\) и значение свойства для анимации определено в диапазоне между 10 и 15 \(From \= 10, To \= 15\), то свойство анимируется от 10 до 15 во время первого цикла, от 15 до 20 во время второго цикла, от 20 до 25 во время третьего цикла и т.д.  Следовательно, каждый цикл анимации использует конечное значение анимации из предыдущего цикла анимации в качестве базового значения.  
  
 Свойство `IsCumulative` можно использовать с большинством базовых анимаций и с большинством анимаций по полным кадрам.  Дополнительные сведения см. в разделах [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) и [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 В следующем примере показывается это поведение при анимации ширины четырех прямоугольников.  Пример:  
  
-   Анимируется первый прямоугольник с <xref:System.Windows.Media.Animation.DoubleAnimation>, и свойство <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> устанавливается в значение `true`.  
  
-   Анимируется второй прямоугольник с <xref:System.Windows.Media.Animation.DoubleAnimation>, и свойство <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> устанавливается в значение по умолчанию `false`.  
  
-   Анимируется третий прямоугольник с <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>, и свойство <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> устанавливается в значение `true`.  
  
-   Анимируется последний прямоугольник с <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>, и свойство <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> устанавливается в значение `false`.  
  
 [!code-xml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## См. также  
 [Добавление выходного значения анимации к начальному значению анимации](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)   
 [Повторение анимации](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)