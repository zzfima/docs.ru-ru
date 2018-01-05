---
title: "Практическое руководство. Управление часами в интерактивном режиме"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d24a5154607bf535cbf995705332092bb86ca02e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="951e7-102">Практическое руководство. Управление часами в интерактивном режиме</span><span class="sxs-lookup"><span data-stu-id="951e7-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="951e7-103">Объект <xref:System.Windows.Media.Animation.Clock> объекта <xref:System.Windows.Media.Animation.ClockController> свойство позволяет интерактивно запуск, приостановка, возобновление, поиска, перемещать значение до периода заполнения и остановить часы.</span><span class="sxs-lookup"><span data-stu-id="951e7-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="951e7-104">Можно интерактивно управлять только корневые часы временного дерева.</span><span class="sxs-lookup"><span data-stu-id="951e7-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="951e7-105">Существуют другие способы интерактивного управления анимации, не требующие непосредственной работы с часами: можно также использовать раскадровки.</span><span class="sxs-lookup"><span data-stu-id="951e7-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="951e7-106">Раскадровки поддерживаются в разметке и коде.</span><span class="sxs-lookup"><span data-stu-id="951e7-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="951e7-107">Пример см. в разделе [анимации свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) или [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="951e7-107">For an example, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
 <span data-ttu-id="951e7-108">В следующем примере несколько кнопок используются для интерактивного управления таймера анимации.</span><span class="sxs-lookup"><span data-stu-id="951e7-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="951e7-109">Пример</span><span class="sxs-lookup"><span data-stu-id="951e7-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="951e7-110">См. также</span><span class="sxs-lookup"><span data-stu-id="951e7-110">See Also</span></span>  
 [<span data-ttu-id="951e7-111">Анимация свойства с помощью раскадровки</span><span class="sxs-lookup"><span data-stu-id="951e7-111">Animate a Property by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [<span data-ttu-id="951e7-112">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="951e7-112">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
