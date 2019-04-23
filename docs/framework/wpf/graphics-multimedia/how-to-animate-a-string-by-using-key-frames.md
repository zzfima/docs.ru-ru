---
title: Практическое руководство. Анимация строки с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: 4a37408ad90fda12a95e66c1b44018967b376837
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204176"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="9791b-102">Практическое руководство. Анимация строки с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="9791b-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="9791b-103">В этом примере демонстрируется анимация строку, которая в этом примере является <xref:System.Windows.Controls.ContentControl.Content%2A> свойство <xref:System.Windows.Controls.Button> элемента управления, с помощью ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="9791b-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9791b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="9791b-104">Example</span></span>  
 <span data-ttu-id="9791b-105">В следующем примере используется <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> класс для анимации <xref:System.Windows.Controls.ContentControl.Content%2A> свойство <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="9791b-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="9791b-106">Все ключевые кадры в этом примере использует экземпляр <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> класса, так как анимация строки, которая создается по ключевым кадрам можно использовать только дискретные ключевые кадры.</span><span class="sxs-lookup"><span data-stu-id="9791b-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="9791b-107">Дискретные ключевые кадры, например <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> , создают скачкообразные переходы между значениями, то есть, изменения анимации происходят быстро, а не плавно.</span><span class="sxs-lookup"><span data-stu-id="9791b-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="9791b-108">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="9791b-108">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9791b-109">См. также</span><span class="sxs-lookup"><span data-stu-id="9791b-109">See also</span></span>

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [<span data-ttu-id="9791b-110">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="9791b-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="9791b-111">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="9791b-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
