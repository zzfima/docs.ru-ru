---
title: Практическое руководство. Анимация строки с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: c954806ca901bbfc3ab6d4bbcc237cd0e404f154
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344672"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="629fc-102">Практическое руководство. Анимация строки с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="629fc-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="629fc-103">В этом примере показано, как анимировать строку, которая в данном примере является <xref:System.Windows.Controls.ContentControl.Content%2A> свойством <xref:System.Windows.Controls.Button> элемента управления, используя ключевые кадры.</span><span class="sxs-lookup"><span data-stu-id="629fc-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="629fc-104">Пример</span><span class="sxs-lookup"><span data-stu-id="629fc-104">Example</span></span>  
 <span data-ttu-id="629fc-105">В следующем примере <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> используется класс <xref:System.Windows.Controls.ContentControl.Content%2A> для анимировать свойство <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="629fc-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="629fc-106">Все ключевые кадры в этом примере используют экземпляр <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> класса, потому что струнная анимация, созданная с помощью ключевых кадров, может использовать только дискретные ключевые кадры.</span><span class="sxs-lookup"><span data-stu-id="629fc-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="629fc-107">Дискретные ключевые <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> кадры, такие как создают резкие скачки между значениями, то есть изменения в анимации происходят быстро и не являются тонкими.</span><span class="sxs-lookup"><span data-stu-id="629fc-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="629fc-108">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="629fc-108">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="629fc-109">См. также</span><span class="sxs-lookup"><span data-stu-id="629fc-109">See also</span></span>

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [<span data-ttu-id="629fc-110">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="629fc-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="629fc-111">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="629fc-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
