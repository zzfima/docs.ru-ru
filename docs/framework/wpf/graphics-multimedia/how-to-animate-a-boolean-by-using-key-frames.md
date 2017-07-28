---
title: "Практическое руководство. Анимация логического типа с помощью ключевых кадров | Microsoft Docs"
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
  - "анимация, Boolean по ключевым кадрам"
  - "Boolean, анимация по ключевым кадрам"
  - "ключевые кадры, анимация Boolean по"
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Анимация логического типа с помощью ключевых кадров
В этом примере демонстрируется анимация значения свойства логического типа элемента управления <xref:System.Windows.Controls.Button> с помощью полных кадров.  
  
## Пример  
 В следующем примере для анимации свойства <xref:System.Windows.UIElement.IsEnabled%2A> элемента управления <xref:System.Windows.Controls.Button> используется класс <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>.  Все полные кадры в этом примере используют экземпляр класса <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame>.  Дискретные полные кадры, такие как <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame>, создают внезапные переходы между значениями, т. е анимация выполняется рывками.  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 Полный пример см. на веб\-странице [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## См. также  
 <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>   
 <xref:System.Windows.UIElement.IsEnabled%2A>   
 <xref:System.Windows.Controls.Button>   
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Практические руководства, посвященные анимации по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)