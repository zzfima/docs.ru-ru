---
title: Как выполнить Ускорение или замедление анимации
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: 28c7940b9a60f3bd485ba2aea77e6bc1ae5fec54
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "55065847"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a><span data-ttu-id="d4ead-102">Как выполнить Ускорение или замедление анимации</span><span class="sxs-lookup"><span data-stu-id="d4ead-102">How to: Accelerate or Decelerate an Animation</span></span>
<span data-ttu-id="d4ead-103">В этом примере показано, как выполнять анимацию ускорения и замедления времени.</span><span class="sxs-lookup"><span data-stu-id="d4ead-103">This example demonstrates how to make an animation accelerate and decelerate over time.</span></span> <span data-ttu-id="d4ead-104">В следующем примере несколько прямоугольников анимируются по анимации с различными <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> и <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> параметры.</span><span class="sxs-lookup"><span data-stu-id="d4ead-104">In the following example, several rectangles are animated by animations with different <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> and <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4ead-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d4ead-105">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 <span data-ttu-id="d4ead-106">В этом примере отсутствует код.</span><span class="sxs-lookup"><span data-stu-id="d4ead-106">Code has been omitted from this example.</span></span> <span data-ttu-id="d4ead-107">Для получения полного кода см. в разделе [поведение анимации с учетом времени (C#)](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) или [поведение анимации с учетом времени (Visual Basic)](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).</span><span class="sxs-lookup"><span data-stu-id="d4ead-107">For the complete code, see the [Animation Timing Behavior (C#)](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) or [Animation Timing Behavior (Visual Basic)](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).</span></span>
