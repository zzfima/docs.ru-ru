---
title: "Практическое руководство. Анимация строки с помощью ключевых кадров | Microsoft Docs"
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
  - "анимация, строк по ключевым кадрам"
  - "ключевые кадры, анимация строк"
  - "строки, анимация по ключевым кадрам"
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Анимация строки с помощью ключевых кадров
В этом примере демонстрируется анимация строки, которая в данном примере является свойством <xref:System.Windows.Controls.ContentControl.Content%2A> элемента управления<xref:System.Windows.Controls.Button>, с помощью полных кадров.  
  
## Пример  
 В следующем примере для анимации свойства <xref:System.Windows.Controls.ContentControl.Content%2A> элемента управления <xref:System.Windows.Controls.Button> используется класс <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>.  
  
 В этом примере все полные кадры используют экземпляр класса <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>, поскольку при создании строковой анимации с помощью полных кадров применяются только дискретные полные кадры.  Дискретные полные кадры типа <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> совершают мгновенные переходы между значениями, т. е. изменения анимации происходят быстро, но заметно.  
  
 [!code-xml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 Полный пример см. на веб\-странице [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## См. также  
 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>   
 <xref:System.Windows.Controls.ContentControl.Content%2A>   
 <xref:System.Windows.Controls.Button>   
 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>   
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Практические руководства, посвященные анимации по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)