---
title: Практическое руководство. Анимация цвета с помощью ключевых кадров
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 8a444706f7541b52722ab8257a88e76c3e1b0938
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344751"
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="ec951-102">Практическое руководство. Анимация цвета с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="ec951-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="ec951-103">Этот пример показывает, как <xref:System.Windows.Media.SolidColorBrush.Color%2A> оживить <xref:System.Windows.Media.SolidColorBrush> кадры ключей.</span><span class="sxs-lookup"><span data-stu-id="ec951-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec951-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ec951-104">Example</span></span>  
 <span data-ttu-id="ec951-105">В следующем примере <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> используется класс <xref:System.Windows.Media.SolidColorBrush.Color%2A> для анимировать свойство <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="ec951-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="ec951-106">Эта анимация использует три ключевых кадра следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ec951-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="ec951-107">В течение первых двух секунд используется <xref:System.Windows.Media.Animation.LinearColorKeyFrame> экземпляр класса для постепенного изменения цвета с зеленого на красный.</span><span class="sxs-lookup"><span data-stu-id="ec951-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="ec951-108">Линейные ключевые <xref:System.Windows.Media.Animation.LinearColorKeyFrame> кадры, такие как создание плавного линейного перехода между значениями.</span><span class="sxs-lookup"><span data-stu-id="ec951-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="ec951-109">В конце следующей половины секунды используется <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> экземпляр класса, чтобы быстро изменить цвет с красного на желтый.</span><span class="sxs-lookup"><span data-stu-id="ec951-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="ec951-110">Дискретные ключевые <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> кадры, такие как создают внезапные изменения между значениями, то есть изменение цвета в этой части анимации происходит быстро и не является тонким.</span><span class="sxs-lookup"><span data-stu-id="ec951-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="ec951-111">В течение последних двух секунд, <xref:System.Windows.Media.Animation.SplineColorKeyFrame> использует экземпляр класса, чтобы изменить цвет снова- на этот раз с желтого на зеленый.</span><span class="sxs-lookup"><span data-stu-id="ec951-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="ec951-112">Сплайс-ключевые кадры, такие как <xref:System.Windows.Media.Animation.SplineColorKeyFrame> создание переменного <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> перехода между значениями в зависимости от значений свойства.</span><span class="sxs-lookup"><span data-stu-id="ec951-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="ec951-113">В этом примере изменение цвета начинается медленно и ускоряется экспоненциально к концу временного сегмента.</span><span class="sxs-lookup"><span data-stu-id="ec951-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="ec951-114">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="ec951-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec951-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ec951-115">See also</span></span>

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [<span data-ttu-id="ec951-116">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="ec951-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="ec951-117">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="ec951-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
