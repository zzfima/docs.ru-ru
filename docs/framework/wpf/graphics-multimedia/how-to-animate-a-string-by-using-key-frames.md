---
title: Как выполнить Анимация строки с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: 4cadc1e7e4b7ee70e3a71ddaf433327a7561125d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670840"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="b2850-102">Как выполнить Анимация строки с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="b2850-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="b2850-103">В этом примере демонстрируется анимация строку, которая в этом примере является <xref:System.Windows.Controls.ContentControl.Content%2A> свойство <xref:System.Windows.Controls.Button> элемента управления, с помощью ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="b2850-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2850-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b2850-104">Example</span></span>  
 <span data-ttu-id="b2850-105">В следующем примере используется <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> класс для анимации <xref:System.Windows.Controls.ContentControl.Content%2A> свойство <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="b2850-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="b2850-106">Все ключевые кадры в этом примере использует экземпляр <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> класса, так как анимация строки, которая создается по ключевым кадрам можно использовать только дискретные ключевые кадры.</span><span class="sxs-lookup"><span data-stu-id="b2850-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="b2850-107">Дискретные ключевые кадры, например <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> , создают скачкообразные переходы между значениями, то есть, изменения анимации происходят быстро, а не плавно.</span><span class="sxs-lookup"><span data-stu-id="b2850-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="b2850-108">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="b2850-108">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2850-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b2850-109">See also</span></span>
- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [<span data-ttu-id="b2850-110">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="b2850-110">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [<span data-ttu-id="b2850-111">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="b2850-111">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
