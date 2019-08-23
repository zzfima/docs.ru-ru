---
title: Практическое руководство. Управление часами в интерактивном режиме
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 2d18f395974750a6b85458f636a27f6101e7978f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951339"
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="e2188-102">Практическое руководство. Управление часами в интерактивном режиме</span><span class="sxs-lookup"><span data-stu-id="e2188-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="e2188-103">Свойство<xref:System.Windows.Media.Animation.ClockController>объектапозволяет интерактивно запускать, приостанавливать, возобновлять, искать, прерывать часы до периода заполнения и останавливать часы. <xref:System.Windows.Media.Animation.Clock></span><span class="sxs-lookup"><span data-stu-id="e2188-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="e2188-104">Только корневые часы дерева времени можно контролировать в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="e2188-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2188-105">Существуют и другие способы интерактивного управления анимациями, которые не нуждаются в непосредственной работе с часами. можно также использовать раскадровки.</span><span class="sxs-lookup"><span data-stu-id="e2188-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="e2188-106">Раскадровки поддерживаются как в разметке, так и в коде.</span><span class="sxs-lookup"><span data-stu-id="e2188-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="e2188-107">Пример см. в разделе [анимация свойства с помощью](how-to-animate-a-property-by-using-a-storyboard.md) раскадровки или [обзора анимации](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e2188-107">For an example, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="e2188-108">В следующем примере несколько кнопок используются для интерактивного управления часами анимации.</span><span class="sxs-lookup"><span data-stu-id="e2188-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2188-109">Пример</span><span class="sxs-lookup"><span data-stu-id="e2188-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="e2188-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e2188-110">See also</span></span>

- [<span data-ttu-id="e2188-111">Анимация свойства с помощью раскадровки</span><span class="sxs-lookup"><span data-stu-id="e2188-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="e2188-112">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="e2188-112">Animation Overview</span></span>](animation-overview.md)
