---
title: "Практическое руководство. Упрощение анимации с помощью дочерних шкал времени | Microsoft Docs"
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
  - "анимация, упрощение с помощью дочерних временных шкал"
  - "дочерние временные шкалы"
  - "упрощение анимации с помощью дочерних временных шкал"
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Упрощение анимации с помощью дочерних шкал времени
В этом примере показано, как упростить анимацию с помощью дочерних объектов <xref:System.Windows.Media.Animation.ParallelTimeline>.  <xref:System.Windows.Media.Animation.Storyboard> является типом <xref:System.Windows.Media.Animation.Timeline>, предоставляющим сведения о содержащихся в нем объектах шкалы времени.  Используйте <xref:System.Windows.Media.Animation.Storyboard> для предоставления сведений о шкале времени, включая информацию об объектах и свойствах.  
  
 Чтобы начать анимацию, используйте один или несколько объектов <xref:System.Windows.Media.Animation.ParallelTimeline> в качестве вложенных дочерних элементов <xref:System.Windows.Media.Animation.Storyboard>.  Эти объекты <xref:System.Windows.Media.Animation.ParallelTimeline> могут содержать другие анимации и, таким образом, могут лучше инкапсулировать временные последовательности в сложных анимациях.  Например, если осуществляется анимация <xref:System.Windows.Controls.TextBlock> и нескольких фигур в одном <xref:System.Windows.Media.Animation.Storyboard>, то можно разделить анимацию для <xref:System.Windows.Controls.TextBlock> и фигур, помещая каждую в отдельный объект <xref:System.Windows.Media.Animation.ParallelTimeline>.  Поскольку в каждом <xref:System.Windows.Media.Animation.ParallelTimeline> имеется собственное свойство <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> и все дочерние элементы <xref:System.Windows.Media.Animation.ParallelTimeline> начинаются относительно этого <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, то время инкапсулируется лучше.  
  
 В приведенном ниже примере осуществляется анимация двух фрагментов текста \(объектов <xref:System.Windows.Controls.TextBlock>\) внутри одного и того же <xref:System.Windows.Media.Animation.Storyboard>.  <xref:System.Windows.Media.Animation.ParallelTimeline> инкапсулирует анимацию одного из объектов <xref:System.Windows.Controls.TextBlock>.  
  
 **Замечание о производительности.** Хотя можно вложить шкалы времени <xref:System.Windows.Media.Animation.Storyboard> друг в друга, объекты <xref:System.Windows.Media.Animation.ParallelTimeline> больше подходят для вложения, так как они требуют меньше издержек.  \(Класс <xref:System.Windows.Media.Animation.Storyboard> наследует из класса <xref:System.Windows.Media.Animation.ParallelTimeline>.\)  
  
## Пример  
 [!code-xml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Задание значения свойства HandoffBehavior для анимаций раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)