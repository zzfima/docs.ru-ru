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
ms.openlocfilehash: cb09a54df3d99e05e89ec0f3d9f17b0e9fe78647
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43419081"
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="cf40f-102">Практическое руководство. Анимация цвета с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="cf40f-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="cf40f-103">В этом примере демонстрируется анимация <xref:System.Windows.Media.SolidColorBrush.Color%2A> из <xref:System.Windows.Media.SolidColorBrush> с помощью ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="cf40f-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf40f-104">Пример</span><span class="sxs-lookup"><span data-stu-id="cf40f-104">Example</span></span>  
 <span data-ttu-id="cf40f-105">В следующем примере используется <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> класс для анимации <xref:System.Windows.Media.SolidColorBrush.Color%2A> свойство <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="cf40f-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="cf40f-106">Эта анимация использует три ключевых кадра следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cf40f-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="cf40f-107">В течение первых двух секунд используется экземпляр <xref:System.Windows.Media.Animation.LinearColorKeyFrame> класс для постепенного изменения цвета от зеленого к красному.</span><span class="sxs-lookup"><span data-stu-id="cf40f-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="cf40f-108">Линейные ключевые кадры, например <xref:System.Windows.Media.Animation.LinearColorKeyFrame> создать плавный линейный переход между значениями.</span><span class="sxs-lookup"><span data-stu-id="cf40f-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="cf40f-109">В конце следующей половины секунды используется экземпляр <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> класс для быстрого изменения цвета с красного на желтый.</span><span class="sxs-lookup"><span data-stu-id="cf40f-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="cf40f-110">Дискретные ключевые кадры, например <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> создают резкие изменения значений, то есть, изменение цвета в этой части анимации происходит быстро и не плавно.</span><span class="sxs-lookup"><span data-stu-id="cf40f-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3.  <span data-ttu-id="cf40f-111">В течение последних двух секунд используется экземпляр <xref:System.Windows.Media.Animation.SplineColorKeyFrame> класс для изменения цвета — это время с желтого обратно на зеленый.</span><span class="sxs-lookup"><span data-stu-id="cf40f-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="cf40f-112">Ключевые кадры сплайна, например <xref:System.Windows.Media.Animation.SplineColorKeyFrame> , создают переменный переход между значениями в соответствии со значениями из <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="cf40f-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="cf40f-113">В этом примере изменение цвета начинается медленно и ускоряется экспоненциально к концу временного сегмента.</span><span class="sxs-lookup"><span data-stu-id="cf40f-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="cf40f-114">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="cf40f-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf40f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="cf40f-115">See Also</span></span>  
 <xref:System.Windows.Media.SolidColorBrush.Color%2A>  
 <xref:System.Windows.Media.SolidColorBrush>  
 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>  
 [<span data-ttu-id="cf40f-116">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="cf40f-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="cf40f-117">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="cf40f-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
