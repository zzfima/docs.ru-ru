---
title: Практическое руководство. Анимация логического типа с помощью ключевых кадров
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
ms.openlocfilehash: 35704996dcf21fe463169dc13572941bcd8fbad1
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344944"
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a><span data-ttu-id="b56d3-102">Практическое руководство. Анимация логического типа с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="b56d3-102">How to: Animate a Boolean by Using Key Frames</span></span>
<span data-ttu-id="b56d3-103">В этом примере показано, как оживить значение <xref:System.Windows.Controls.Button> свойства Boolean элемента управления с помощью ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="b56d3-103">This example shows how to animate the Boolean property value of a <xref:System.Windows.Controls.Button> control by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b56d3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b56d3-104">Example</span></span>  
 <span data-ttu-id="b56d3-105">В следующем примере <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> используется класс <xref:System.Windows.UIElement.IsEnabled%2A> для анимировать свойство элемента <xref:System.Windows.Controls.Button> управления.</span><span class="sxs-lookup"><span data-stu-id="b56d3-105">The following example uses the <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> class to animate the <xref:System.Windows.UIElement.IsEnabled%2A> property of a <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="b56d3-106">Все ключевые кадры в этом примере используют экземпляр <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> класса.</span><span class="sxs-lookup"><span data-stu-id="b56d3-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> class.</span></span> <span data-ttu-id="b56d3-107">Дискретные ключевые <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> кадры, такие как создают резкие скачки между значениями, то есть движение анимации отрывисто.</span><span class="sxs-lookup"><span data-stu-id="b56d3-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="b56d3-108">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="b56d3-108">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b56d3-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b56d3-109">See also</span></span>

- <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>
- <xref:System.Windows.UIElement.IsEnabled%2A>
- <xref:System.Windows.Controls.Button>
- [<span data-ttu-id="b56d3-110">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="b56d3-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="b56d3-111">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="b56d3-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
