---
title: "Практическое руководство. Определение автоматического реверса для шкалы времени"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2abce54905f0bb06bf983c065e064ce2dfeba932
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="790b9-102">Практическое руководство. Определение автоматического реверса для шкалы времени</span><span class="sxs-lookup"><span data-stu-id="790b9-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="790b9-103">Временная шкала <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> свойство определяет, является ли он воспроизводится в обратном направлении после завершения прямой итерации.</span><span class="sxs-lookup"><span data-stu-id="790b9-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="790b9-104">В следующем примере показано несколько анимаций с идентичной длительностью и целевые значения, но различными <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> параметры.</span><span class="sxs-lookup"><span data-stu-id="790b9-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="790b9-105">Чтобы продемонстрировать как <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> свойство ведет себя с различными <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> , некоторые анимации настроек для повторения.</span><span class="sxs-lookup"><span data-stu-id="790b9-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="790b9-106">Последняя анимация показывает как <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> свойство работает на вложенных временных шкал.</span><span class="sxs-lookup"><span data-stu-id="790b9-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="790b9-107">Пример</span><span class="sxs-lookup"><span data-stu-id="790b9-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
