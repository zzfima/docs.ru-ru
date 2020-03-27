---
title: Практическое руководство. Анимация точки с помощью ключевых кадров
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
ms.openlocfilehash: edcba36644cf78d6e98f934d9bd8b593af38b328
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344883"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a><span data-ttu-id="f632b-102">Практическое руководство. Анимация точки с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="f632b-102">How to: Animate a Point by Using Key Frames</span></span>
<span data-ttu-id="f632b-103">В этом примере <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> показано, как использовать <xref:System.Windows.Point>класс для анимировать элемент .</span><span class="sxs-lookup"><span data-stu-id="f632b-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate a <xref:System.Windows.Point>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f632b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f632b-104">Example</span></span>  
 <span data-ttu-id="f632b-105">В следующем примере эллипс перемещается по треугольному пути.</span><span class="sxs-lookup"><span data-stu-id="f632b-105">The following example moves an ellipse along a triangular path.</span></span> <span data-ttu-id="f632b-106">Пример использует <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> класс для анимировать свойство <xref:System.Windows.Media.EllipseGeometry.Center%2A> . <xref:System.Windows.Media.EllipseGeometry></span><span class="sxs-lookup"><span data-stu-id="f632b-106">The example uses the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property of an <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="f632b-107">Эта анимация использует три ключевых кадра следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f632b-107">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="f632b-108">В течение первой половины второй, <xref:System.Windows.Media.Animation.LinearPointKeyFrame> использует экземпляр класса для перемещения эллипса по пути с постоянной скоростью от его исходного положения.</span><span class="sxs-lookup"><span data-stu-id="f632b-108">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearPointKeyFrame> class to move the ellipse along a path at a steady rate from its starting position.</span></span> <span data-ttu-id="f632b-109">Линейные ключевые <xref:System.Windows.Media.Animation.LinearPointKeyFrame> кадры, такие как создание плавной линейной интерполяции между значениями.</span><span class="sxs-lookup"><span data-stu-id="f632b-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearPointKeyFrame> create a smooth linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="f632b-110">В конце следующей половины секунды используется <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> экземпляр класса, чтобы внезапно переместить эллипс по пути в следующую позицию.</span><span class="sxs-lookup"><span data-stu-id="f632b-110">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> class to suddenly move the ellipse along the path to the next position.</span></span> <span data-ttu-id="f632b-111">Дискретные ключевые <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> кадры, такие как создают внезапные скачки между значениями.</span><span class="sxs-lookup"><span data-stu-id="f632b-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> create sudden jumps between values.</span></span>  
  
3. <span data-ttu-id="f632b-112">В течение последних двух секунд, <xref:System.Windows.Media.Animation.SplinePointKeyFrame> использует экземпляр класса для перемещения эллипса обратно в исходное положение.</span><span class="sxs-lookup"><span data-stu-id="f632b-112">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame> class to move the ellipse back to its starting position.</span></span> <span data-ttu-id="f632b-113">Сплайс-ключевые кадры, такие как <xref:System.Windows.Media.Animation.SplinePointKeyFrame> создание переменного <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> перехода между значениями в зависимости от значений свойства.</span><span class="sxs-lookup"><span data-stu-id="f632b-113">Spline key frames like <xref:System.Windows.Media.Animation.SplinePointKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="f632b-114">В этом примере анимация начинается медленно и ускоряется экспоненциально к концу временного отрезка.</span><span class="sxs-lookup"><span data-stu-id="f632b-114">In this example, the animation begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="f632b-115">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="f632b-115">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
 <span data-ttu-id="f632b-116">Для согласованности с другими примерами анимации <xref:System.Windows.Media.Animation.Storyboard> в кодовых <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>версиях этого примера используется объект для применения .</span><span class="sxs-lookup"><span data-stu-id="f632b-116">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="f632b-117">Однако при применении одной анимации в коде <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> проще использовать метод <xref:System.Windows.Media.Animation.Storyboard>вместо использования .</span><span class="sxs-lookup"><span data-stu-id="f632b-117">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="f632b-118">Например, [см. Animate a Property без использования раскадровки.](how-to-animate-a-property-without-using-a-storyboard.md)</span><span class="sxs-lookup"><span data-stu-id="f632b-118">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f632b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f632b-119">See also</span></span>

- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [<span data-ttu-id="f632b-120">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="f632b-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="f632b-121">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="f632b-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
