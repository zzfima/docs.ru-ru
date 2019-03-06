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
ms.openlocfilehash: 6d3dbc8c39e63b46871b0cc88fbe8d5d51b63463
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361659"
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="bb9d6-102">Практическое руководство. Управление часами в интерактивном режиме</span><span class="sxs-lookup"><span data-stu-id="bb9d6-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="bb9d6-103">Объект <xref:System.Windows.Media.Animation.Clock> объекта <xref:System.Windows.Media.Animation.ClockController> свойства можно в интерактивном режиме запуск, приостановка, возобновление, поиска, перемещать значение к периоду заполнения и остановить часы.</span><span class="sxs-lookup"><span data-stu-id="bb9d6-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="bb9d6-104">Можно интерактивно управлять только корневые часы дерево временной шкалы.</span><span class="sxs-lookup"><span data-stu-id="bb9d6-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb9d6-105">Существуют другие способы интерактивного управления анимации, которые не требуется работать непосредственно с часов: можно также использовать раскадровки.</span><span class="sxs-lookup"><span data-stu-id="bb9d6-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="bb9d6-106">Раскадровки поддерживаются в разметке и коде.</span><span class="sxs-lookup"><span data-stu-id="bb9d6-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="bb9d6-107">Например, см. в разделе [анимация свойства с помощью раскадровки](how-to-animate-a-property-by-using-a-storyboard.md) или [Общие сведения об анимации](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bb9d6-107">For an example, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="bb9d6-108">В следующем примере несколько кнопок используются для интерактивного управления таймера анимации.</span><span class="sxs-lookup"><span data-stu-id="bb9d6-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb9d6-109">Пример</span><span class="sxs-lookup"><span data-stu-id="bb9d6-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="bb9d6-110">См. также</span><span class="sxs-lookup"><span data-stu-id="bb9d6-110">See also</span></span>
- [<span data-ttu-id="bb9d6-111">Анимация свойства с помощью раскадровки</span><span class="sxs-lookup"><span data-stu-id="bb9d6-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="bb9d6-112">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="bb9d6-112">Animation Overview</span></span>](animation-overview.md)
