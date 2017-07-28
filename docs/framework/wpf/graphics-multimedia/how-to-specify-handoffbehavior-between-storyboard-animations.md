---
title: "Практическое руководство. Задание значения свойства HandoffBehavior для анимаций раскадровки | Microsoft Docs"
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
  - "анимация, переадресуемое поведение"
  - "Раскадровки, переадресуемое поведение между анимациями"
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Задание значения свойства HandoffBehavior для анимаций раскадровки
В данном примере показано, как задавать переадресуемое поведение между анимациями раскадровки.  Свойство <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> класса <xref:System.Windows.Media.Animation.BeginStoryboard> указывает, как новая анимация должна взаимодействовать с любыми существующими анимациями, которые уже применены к свойству.  
  
## Пример  
 В следующем примере создаются две кнопки, увеличивающиеся при наведении на них курсора мыши и уменьшающиеся при отведении от них курсора.  Если навести курсор на кнопку и затем быстро убрать его, вторая анимация будут применена до завершения первой.  Именно при подобном перекрытии двух объектов анимации можно увидеть разницу между значениями <xref:System.Windows.Media.Animation.HandoffBehavior> и <xref:System.Windows.Media.Animation.HandoffBehavior> свойства <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>.  Значение <xref:System.Windows.Media.Animation.HandoffBehavior> объединяет перекрывающиеся анимации и вызывает сглаженный переход между ними, а значение <xref:System.Windows.Media.Animation.HandoffBehavior> вызывает немедленное замещение новой анимацией перекрывавшейся ранее анимации.  
  
 [!code-xml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## См. также  
 <xref:System.Windows.Media.Animation.BeginStoryboard>   
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Animation and Timing](http://msdn.microsoft.com/ru-ru/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)