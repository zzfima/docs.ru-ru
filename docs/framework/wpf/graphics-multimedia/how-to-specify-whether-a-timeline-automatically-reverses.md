---
title: Практическое руководство. Определение автоматического реверса для шкалы времени
ms.date: 03/30/2017
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
ms.openlocfilehash: 0fe2d337d8afa5197475e5b9ee40950226596e8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024668"
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="46f64-102">Практическое руководство. Определение автоматического реверса для шкалы времени</span><span class="sxs-lookup"><span data-stu-id="46f64-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="46f64-103">Временной шкалы <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> свойство определяет, будет ли он воспроизводиться в обратном порядке после завершения прямой итерации.</span><span class="sxs-lookup"><span data-stu-id="46f64-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="46f64-104">В следующем примере показано несколько анимаций с идентичной длительностью и целевыми значениями, но с разными <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> параметры.</span><span class="sxs-lookup"><span data-stu-id="46f64-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="46f64-105">Чтобы продемонстрировать, как <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> свойство ведет себя с различными <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> , некоторых анимаций настроены для повторения.</span><span class="sxs-lookup"><span data-stu-id="46f64-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="46f64-106">Последняя анимация показывает как <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> свойство работает с вложенными временными шкалами.</span><span class="sxs-lookup"><span data-stu-id="46f64-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46f64-107">Пример</span><span class="sxs-lookup"><span data-stu-id="46f64-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
