---
title: "Практическое руководство. Установка свойства после его анимации с помощью раскадровки | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "анимация, изменение значений свойств после"
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Установка свойства после его анимации с помощью раскадровки
В некоторых случаях нельзя изменить значение свойства после его анимации.  
  
## Пример  
 В следующем примере используется <xref:System.Windows.Media.Animation.Storyboard> для анимации цвета <xref:System.Windows.Media.SolidColorBrush>.  Раскадровка инициируется при нажатии кнопки.  Событие <xref:System.Windows.Media.Animation.Timeline.Completed> обрабатывается таким образом, чтобы программа получала уведомление о завершении <xref:System.Windows.Media.Animation.ColorAnimation>.  
  
 [!code-xml[timingbehaviors_snip#GraphicsMMButton1Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## Пример  
 После завершения <xref:System.Windows.Media.Animation.ColorAnimation> программа выполняет попытку изменить цвет кисти на голубой.  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 Предыдущий код как будто ничего не делает: кисть остается желтой, что является значением, предоставляемым анимирующим кисть <xref:System.Windows.Media.Animation.ColorAnimation>.  Значение базового свойства \(базовое значение\) фактически изменяется на значение синего цвета.  Однако эффективным, или текущим, значением остается желтый, поскольку <xref:System.Windows.Media.Animation.ColorAnimation> по\-прежнему переопределяет базовое значение.  Если требуется, чтобы базовое значение вновь стало эффективным, необходимо прекратить влияние анимации на данное свойство.  Есть три способа сделать это с помощью анимации раскадровки:  
  
-   Задайте для свойства анимации <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> значение <xref:System.Windows.Media.Animation.FillBehavior>.  
  
-   Удалите раскадровку целиком.  
  
-   Удалите анимацию из отдельного свойства.  
  
## Задайте для свойства анимации FillBehavior значение Stop  
 Установка для <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> значения <xref:System.Windows.Media.Animation.FillBehavior> уведомляет анимацию о прекращении влияния на целевое свойство после достижения конца активного периода.  
  
 [!code-xml[timingbehaviors_snip#GraphicsMMButton2Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## Удалите раскадровку целиком.  
 С помощью триггера <xref:System.Windows.Media.Animation.RemoveStoryboard> или метода <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=fullName> анимациям раскадровки предписывается прекратить влияние на их целевые свойства.  Разница между этим подходом и установкой свойства <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> заключается в том, что удалить раскадровку можно в любое время, в то время как свойство <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> окажет эффект только при достижении анимацией конца активного периода.  
  
 [!code-xml[timingbehaviors_snip#GraphicsMMButton3Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## Удаление анимации из отдельного свойства  
 Другим способом остановки влияния анимации на свойство является использование метода <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> анимируемого объекта.  Укажите анимируемое свойство в качестве первого параметра и `null` в качестве второго.  
  
 [!code-xml[timingbehaviors_snip#GraphicsMMButton4Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 Этот способ также работает для анимаций без раскадровки.  
  
## См. также  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>   
 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=fullName>   
 <xref:System.Windows.Media.Animation.RemoveStoryboard>   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)