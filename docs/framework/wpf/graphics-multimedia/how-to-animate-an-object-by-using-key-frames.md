---
title: "Практическое руководство. Анимация объекта с помощью ключевых кадров | Microsoft Docs"
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
  - "анимация, объектов по ключевым кадрам"
  - "ключевые кадры, анимация объектов"
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Анимация объекта с помощью ключевых кадров
В этом примере показана анимация объекта \(свойство <xref:System.Windows.Controls.Page.Background%2A> элемента управления <xref:System.Windows.Controls.Page>\) с помощью полных кадров.  
  
## Пример  
 В следующем примере используется класс <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> для анимации изменения цвета свойства <xref:System.Windows.Controls.Page.Background%2A> элемента управления <xref:System.Windows.Controls.Page>.  В этом примере через определенные интервалы времени изменяется цвет кисти фона.  Для создания трех различных полных кадров в этой анимации используется класс <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>.  Полные кадры используются для анимации следующим способом:  
  
1.  В конце первой секунды происходит анимация экземпляра класса <xref:System.Windows.Media.LinearGradientBrush>.  В этой части примера к фоновому цвету применяется линейный градиент, определяющий переход цвета от желтого к оранжевому и к красному.  
  
2.  В конце следующей секунды происходит анимация экземпляра класса <xref:System.Windows.Media.RadialGradientBrush>.  В этой части примера к фоновому цвету применяется радиальный градиент, определяющий переход цвета от белого к синему и к черному.  
  
3.  В конце третьей секунды происходит анимация экземпляра класса <xref:System.Windows.Media.DrawingBrush>.  В этой части примера к фону применяется шаблон шахматной доски.  
  
4.  Анимация начинается еще раз и повторяется бесконечно.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> является единственным типом полного кадра, который можно использовать с классом <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>.  Полные кадры, например <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>, создают внезапные изменения в значениях, т. е. в примере происходит внезапное изменение цвета.  
  
 [!code-xml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 Полный пример см. на веб\-странице [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## См. также  
 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>   
 <xref:System.Windows.Controls.Page.Background%2A>   
 <xref:System.Windows.Controls.Page>   
 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>   
 <xref:System.Windows.Media.LinearGradientBrush>   
 <xref:System.Windows.Media.RadialGradientBrush>   
 <xref:System.Windows.Media.DrawingBrush>   
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Практические руководства, посвященные анимации по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)