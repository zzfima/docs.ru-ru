---
title: Практическое руководство. Определение автоматического реверса для шкалы времени
ms.date: 03/30/2017
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
ms.openlocfilehash: 498aefa16b8a76262c01965b8992ef9a94b7ce28
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="c1a72-102">Практическое руководство. Определение автоматического реверса для шкалы времени</span><span class="sxs-lookup"><span data-stu-id="c1a72-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="c1a72-103">Временная шкала <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> свойство определяет, является ли он воспроизводится в обратном направлении после завершения прямой итерации.</span><span class="sxs-lookup"><span data-stu-id="c1a72-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="c1a72-104">В следующем примере показано несколько анимаций с идентичной длительностью и целевые значения, но различными <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> параметры.</span><span class="sxs-lookup"><span data-stu-id="c1a72-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="c1a72-105">Чтобы продемонстрировать как <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> свойство ведет себя с различными <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> , некоторые анимации настроек для повторения.</span><span class="sxs-lookup"><span data-stu-id="c1a72-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="c1a72-106">Последняя анимация показывает как <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> свойство работает на вложенных временных шкал.</span><span class="sxs-lookup"><span data-stu-id="c1a72-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1a72-107">Пример</span><span class="sxs-lookup"><span data-stu-id="c1a72-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
