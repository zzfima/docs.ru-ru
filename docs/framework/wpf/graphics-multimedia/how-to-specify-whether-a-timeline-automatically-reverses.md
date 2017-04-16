---
title: "Практическое руководство. Определение автоматического реверса для шкалы времени | Microsoft Docs"
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
  - "Временные шкалы - свойство AutoReverse"
  - "Временные шкалы, свойство AutoReverse"
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Практическое руководство. Определение автоматического реверса для шкалы времени
Свойство шкалы времени элемента <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> определяет, будет ли он воспроизводиться в обратном порядке после завершения прямой итерации.  В следующем примере показано несколько анимаций с идентичной длительностью и конечными величинами, но различными параметрами <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>.  Для демонстрации, как свойство <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> ведет себя с различными настройками <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, несколько анимаций настроены на повтор.  Последняя анимация показывает, как свойство <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> работает с вложенными временными шкалами.  
  
## Пример  
 [!code-xml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]