---
title: "Практическое руководство. Задание значения свойства HandoffBehavior для анимаций раскадровки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 323ea563aec7bc7ad0abec2372e3af977c7e38eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a><span data-ttu-id="d3c6a-102">Практическое руководство. Задание значения свойства HandoffBehavior для анимаций раскадровки</span><span class="sxs-lookup"><span data-stu-id="d3c6a-102">How to: Specify HandoffBehavior Between Storyboard Animations</span></span>
<span data-ttu-id="d3c6a-103">В этом примере показано, как указать поведение перемещения между анимациями раскадровки.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-103">This example shows how to specify handoff behavior between storyboard animations.</span></span> <span data-ttu-id="d3c6a-104"><xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> Свойство <xref:System.Windows.Media.Animation.BeginStoryboard> указывает, как новая анимация взаимодействовать с любыми существующими анимациями, которые уже применены к свойству.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-104">The <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> property of <xref:System.Windows.Media.Animation.BeginStoryboard> specifies how new animations interact with any existing ones that are already applied to a property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3c6a-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d3c6a-105">Example</span></span>  
 <span data-ttu-id="d3c6a-106">В следующем примере создается две кнопки, увеличивающиеся при перемещении курсора мыши над ними и уменьшаются при перемещении курсора немедленно.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-106">The following example creates two buttons that enlarge when the mouse cursor moves over them and become smaller when the cursor moves away.</span></span> <span data-ttu-id="d3c6a-107">Если указатель мыши находится над кнопки и быстро удалить курсор, вторая анимация будут применены до завершения первой.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-107">If you mouse over a button and then quickly remove the cursor, the second animation will be applied before the first one is finished.</span></span> <span data-ttu-id="d3c6a-108">При перекрытии двух объектов анимации следующим образом, можно увидеть разницу между <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> значения <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> и <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-108">It is when two animations overlap like this that you can see the difference between the <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> values of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> and <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span></span> <span data-ttu-id="d3c6a-109">Значение <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> объединяет перекрывающиеся анимации, вызывая плавный переход между анимации при значение <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> вызывает новой анимацией немедленно заменить ранее перекрывающиеся анимации.</span><span class="sxs-lookup"><span data-stu-id="d3c6a-109">A value of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combines the overlapping animations causing a smoother transition between animations while a value of <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> causes the new animation to immediately replace the earlier overlapping animation.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d3c6a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d3c6a-110">See Also</span></span>  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>  
 [<span data-ttu-id="d3c6a-111">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="d3c6a-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="d3c6a-112">Анимация и расчет времени</span><span class="sxs-lookup"><span data-stu-id="d3c6a-112">Animation and Timing</span></span>](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="d3c6a-113">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="d3c6a-113">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
