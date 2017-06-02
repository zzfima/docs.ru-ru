---
title: "Практическое руководство. Анимация свойства без раскадровки | Microsoft Docs"
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
  - "анимация, Анимация без использования Storyboard (локальная)"
  - "локальная анимация"
  - "Анимация без использования Storyboard"
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Анимация свойства без раскадровки
В этом примере показан один из способов применения анимации к свойству без использования раскадровки <xref:System.Windows.Media.Animation.Storyboard>.  
  
> [!NOTE]
>  Эта функция недоступна в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Сведения об анимации свойства в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] см. в разделе [Анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).  
  
 Чтобы применить локальную анимацию к свойству, используйте метод <xref:System.Windows.UIElement.BeginAnimation%2A>.  Этот метод требует два параметра: свойство зависимости <xref:System.Windows.DependencyProperty>, указывающее свойство, подлежащее анимации, и анимацию, применяемую к этому свойству.  
  
## Пример  
 В следующем примере показана анимация ширины и цвета фона кнопки <xref:System.Windows.Controls.Button>.  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 Разнообразные классы анимации в пространстве имен <xref:System.Windows.Media.Animation> существуют для анимации различных типов свойств.  Дополнительные сведения об анимации свойств см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  Дополнительные сведения о [свойствах зависимости](GTMT) \(тип свойств, приведенных в этих примерах\) и их функциях содержатся в разделе [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
 Существуют другие способы анимации без использования объектов <xref:System.Windows.Media.Animation.Storyboard>; дополнительные сведения см. в разделе [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
## См. также  
 <xref:System.Windows.Media.Animation.AnimationTimeline>   
 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>   
 <xref:System.Windows.Media.Animation>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)