---
title: "Практическое руководство. Ускорение или замедление анимации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c06518e3eada30bd4e22549a9ee3c8f16070f5ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a><span data-ttu-id="ba502-102">Практическое руководство. Ускорение или замедление анимации</span><span class="sxs-lookup"><span data-stu-id="ba502-102">How to: Accelerate or Decelerate an Animation</span></span>
<span data-ttu-id="ba502-103">В этом примере показано, как выполнять анимацию ускоряется и замедляется перемещение со временем.</span><span class="sxs-lookup"><span data-stu-id="ba502-103">This example demonstrates how to make an animation accelerate and decelerate over time.</span></span> <span data-ttu-id="ba502-104">В следующем примере несколько прямоугольников анимированных помощи анимаций с разными <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> и <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> параметры.</span><span class="sxs-lookup"><span data-stu-id="ba502-104">In the following example, several rectangles are animated by animations with different <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> and <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba502-105">Пример</span><span class="sxs-lookup"><span data-stu-id="ba502-105">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 <span data-ttu-id="ba502-106">В этом примере отсутствует код.</span><span class="sxs-lookup"><span data-stu-id="ba502-106">Code has been omitted from this example.</span></span> <span data-ttu-id="ba502-107">Для получения полного кода в разделе [пример поведения анимации времени](http://go.microsoft.com/fwlink/?LinkID=159970).</span><span class="sxs-lookup"><span data-stu-id="ba502-107">For the complete code, see the [Animation Timing Behavior Sample](http://go.microsoft.com/fwlink/?LinkID=159970).</span></span>
