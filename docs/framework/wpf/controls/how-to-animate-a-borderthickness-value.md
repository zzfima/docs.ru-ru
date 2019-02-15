---
title: Как выполнить  Анимирование значения BorderThickness
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 96467fd013ddd2b2e215520384da2000aec68866
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2019
ms.locfileid: "56304223"
---
# <a name="how-to-animate-a-borderthickness-value"></a><span data-ttu-id="62157-102">Как выполнить  Анимирование значения BorderThickness</span><span class="sxs-lookup"><span data-stu-id="62157-102">How to: Animate a BorderThickness Value</span></span>
<span data-ttu-id="62157-103">В этом примере показано, как анимировать изменения толщины границы с помощью <xref:System.Windows.Media.Animation.ThicknessAnimation> класса.</span><span class="sxs-lookup"><span data-stu-id="62157-103">This example shows how to animate changes to the thickness of a border by using the <xref:System.Windows.Media.Animation.ThicknessAnimation> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62157-104">Пример</span><span class="sxs-lookup"><span data-stu-id="62157-104">Example</span></span>  
 <span data-ttu-id="62157-105">Следующий пример анимирует толщины границы с помощью <xref:System.Windows.Media.Animation.ThicknessAnimation>.</span><span class="sxs-lookup"><span data-stu-id="62157-105">The following example animates the thickness of a border by using <xref:System.Windows.Media.Animation.ThicknessAnimation>.</span></span> <span data-ttu-id="62157-106">В примере используется <xref:System.Windows.Controls.Border.BorderThickness%2A> свойство <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="62157-106">The example uses the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 <span data-ttu-id="62157-107">Полный пример см. в разделе [Коллекция примеров анимации](https://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="62157-107">For the complete sample, see [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62157-108">См. также</span><span class="sxs-lookup"><span data-stu-id="62157-108">See also</span></span>
- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [<span data-ttu-id="62157-109">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="62157-109">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="62157-110">Анимации и практические руководства</span><span class="sxs-lookup"><span data-stu-id="62157-110">Animation and Timing How-to Topics</span></span>](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="62157-111">Анимация толщины границы с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="62157-111">Animate the Thickness of a Border by Using Key Frames</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
