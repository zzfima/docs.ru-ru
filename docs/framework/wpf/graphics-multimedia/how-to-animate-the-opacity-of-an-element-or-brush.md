---
title: "Практическое руководство. Анимация свойства &quot;Прозрачность&quot; элемента или кисти | Microsoft Docs"
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
  - "анимация, Opacity - свойство"
  - "непрозрачность, анимирование"
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Анимация свойства &quot;Прозрачность&quot; элемента или кисти
Чтобы создать эффект проявления и исчезновения элемента Framework, можно анимировать его свойство <xref:System.Windows.UIElement.Opacity%2A>, или анимировать свойство <xref:System.Windows.Media.Brush.Opacity%2A> использующейся для его рисования кисти <xref:System.Windows.Media.Brush> \(или нескольких кистей\).  Анимация свойства прозрачности элемента создает эффект появления и исчезновения для него и его потомков, но анимация кисти используется для рисования элемента с лучшим выделением, в зависимости от того, какая часть элемента постепенно изменяется.   Например, можно анимировать свойство «Прозрачность» элемента «Кисть», использующегося для рисования фона кнопки.  Это вызовет эффект проявления и исчезновения фона кнопки, в то время как текст кнопки будет оставаться полностью непрозрачным.  
  
> [!NOTE]
>  Анимация <xref:System.Windows.Media.Brush.Opacity%2A> <xref:System.Windows.Media.Brush> имеет большую производительность, чем анимация свойства <xref:System.Windows.UIElement.Opacity%2A> элемента.  
  
 В следующем примере создается эффект проявления и исчезновения для двух кнопок.  Свойство «Прозрачность» первой <xref:System.Windows.Controls.Button> анимируется от `1.0` до `0.0` с <xref:System.Windows.Media.Animation.Timeline.Duration%2A> в пять секунд.  Вторая кнопка также анимирована, но свойство «Прозрачность» элемента SolidColorBrush используется для рисования только ее фона <xref:System.Windows.Controls.Control.Background%2A>, поэтому анимируется фон, а не вся кнопка.  Во время выполнения примера первая кнопка проявляется и исчезает вся, а во второй кнопке проявляется и исчезает только фон.  Текст и границы второй кнопки остаются полностью непрозрачными.  
  
## Пример  
 [!code-xml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 В этот пример не включен код.  Полный пример также показывает, как анимировать прозрачность <xref:System.Windows.Media.Color> внутри <xref:System.Windows.Media.LinearGradientBrush>.  Полный код примера см. в разделе [Пример анимации прозрачности элемента](http://go.microsoft.com/fwlink/?LinkID=159968).