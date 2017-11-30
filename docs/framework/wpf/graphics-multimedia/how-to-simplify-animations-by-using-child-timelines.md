---
title: "Практическое руководство. Упрощение анимации с помощью дочерних шкал времени"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simplifying animations by child timelines [WPF]
- animation [WPF], simplifying by child timelines
- child timelines [WPF]
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: daa4caac0046293e8b86a773bfffd46cf30e835b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-simplify-animations-by-using-child-timelines"></a>Практическое руководство. Упрощение анимации с помощью дочерних шкал времени
В этом примере показано, как упростить анимации с помощью дочерних <xref:System.Windows.Media.Animation.ParallelTimeline> объектов. Объект <xref:System.Windows.Media.Animation.Storyboard> — это тип <xref:System.Windows.Media.Animation.Timeline> , предоставляющий сведения о содержащихся в нем шкалах. Используйте <xref:System.Windows.Media.Animation.Storyboard> для предоставления данных, включая объект и свойство сведения о шкале времени.  
  
 Чтобы начать анимацию, используйте один или несколько <xref:System.Windows.Media.Animation.ParallelTimeline> объекты, как вложенные дочерние элементы <xref:System.Windows.Media.Animation.Storyboard>. Эти <xref:System.Windows.Media.Animation.ParallelTimeline> объекты могут содержать другие анимации и таким образом, могут лучше инкапсулировать временные последовательности в сложных анимациях. Например, при анимации <xref:System.Windows.Controls.TextBlock> и нескольких фигур в одном <xref:System.Windows.Media.Animation.Storyboard>, можно разделить анимацию для <xref:System.Windows.Controls.TextBlock> и фигур, помещая каждую в отдельный <xref:System.Windows.Media.Animation.ParallelTimeline>. Поскольку каждый <xref:System.Windows.Media.Animation.ParallelTimeline> имеет свой собственный <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> и все дочерние элементы элемента <xref:System.Windows.Media.Animation.ParallelTimeline> начинаются относительно этого <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, время инкапсулируется лучше.  
  
 В следующем примере анимируется двух фрагментов текста (<xref:System.Windows.Controls.TextBlock> объектов) из в одном <xref:System.Windows.Media.Animation.Storyboard>. Объект <xref:System.Windows.Media.Animation.ParallelTimeline> инкапсулирует анимацию одного из <xref:System.Windows.Controls.TextBlock> объектов.  
  
 **Замечания о производительности:** несмотря на то, что можно вложить <xref:System.Windows.Media.Animation.Storyboard> временных шкал друг в друга, <xref:System.Windows.Media.Animation.ParallelTimeline>больше подходят для вложения, так как они требуют меньше ресурсов. ( <xref:System.Windows.Media.Animation.Storyboard> Класс наследует от <xref:System.Windows.Media.Animation.ParallelTimeline> класса.)  
  
## <a name="example"></a>Пример  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Задание значения свойства HandoffBehavior для анимаций раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)
