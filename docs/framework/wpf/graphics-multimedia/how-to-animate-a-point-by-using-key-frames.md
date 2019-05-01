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
ms.openlocfilehash: b706568a0e8221aac737780592882f728f0f9e9c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010167"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a><span data-ttu-id="1d30d-102">Практическое руководство. Анимация точки с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="1d30d-102">How to: Animate a Point by Using Key Frames</span></span>
<span data-ttu-id="1d30d-103">В этом примере показано, как использовать <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> класс для анимации <xref:System.Windows.Point>.</span><span class="sxs-lookup"><span data-stu-id="1d30d-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate a <xref:System.Windows.Point>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d30d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="1d30d-104">Example</span></span>  
 <span data-ttu-id="1d30d-105">В следующем примере эллипс перемещается по треугольному пути.</span><span class="sxs-lookup"><span data-stu-id="1d30d-105">The following example moves an ellipse along a triangular path.</span></span> <span data-ttu-id="1d30d-106">В примере используется <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> класс для анимации <xref:System.Windows.Media.EllipseGeometry.Center%2A> свойство <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="1d30d-106">The example uses the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property of an <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="1d30d-107">Эта анимация использует три ключевых кадра следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1d30d-107">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="1d30d-108">В течение первой половины секунды используется экземпляр <xref:System.Windows.Media.Animation.LinearPointKeyFrame> класс для перемещения эллипса вдоль пути с постоянной скоростью из его начальной позиции.</span><span class="sxs-lookup"><span data-stu-id="1d30d-108">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearPointKeyFrame> class to move the ellipse along a path at a steady rate from its starting position.</span></span> <span data-ttu-id="1d30d-109">Линейные ключевые кадры, например <xref:System.Windows.Media.Animation.LinearPointKeyFrame> Создание smooth линейной интерполяции между значениями.</span><span class="sxs-lookup"><span data-stu-id="1d30d-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearPointKeyFrame> create a smooth linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="1d30d-110">В конце следующей половины секунды используется экземпляр <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> класс для резкого перемещения эллипса вдоль пути в следующую позицию.</span><span class="sxs-lookup"><span data-stu-id="1d30d-110">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> class to suddenly move the ellipse along the path to the next position.</span></span> <span data-ttu-id="1d30d-111">Дискретные ключевые кадры, например <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> , создают скачкообразные переходы между значениями.</span><span class="sxs-lookup"><span data-stu-id="1d30d-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> create sudden jumps between values.</span></span>  
  
3. <span data-ttu-id="1d30d-112">В течение последних двух секунд используется экземпляр <xref:System.Windows.Media.Animation.SplinePointKeyFrame> класс для перемещения эллипса обратно в исходное положение.</span><span class="sxs-lookup"><span data-stu-id="1d30d-112">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame> class to move the ellipse back to its starting position.</span></span> <span data-ttu-id="1d30d-113">Ключевые кадры сплайна, например <xref:System.Windows.Media.Animation.SplinePointKeyFrame> , создают переменный переход между значениями в соответствии со значениями из <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="1d30d-113">Spline key frames like <xref:System.Windows.Media.Animation.SplinePointKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="1d30d-114">В этом примере анимация начинается медленно и ускоряется экспоненциально к концу временного отрезка.</span><span class="sxs-lookup"><span data-stu-id="1d30d-114">In this example, the animation begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="1d30d-115">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="1d30d-115">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
 <span data-ttu-id="1d30d-116">Для обеспечения согласованности с другими примерами анимации версии кода этого примера используют <xref:System.Windows.Media.Animation.Storyboard> объекта для применения <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="1d30d-116">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="1d30d-117">Тем не менее, при применении в коде одной анимации, проще использовать <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метода вместо использования <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="1d30d-117">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="1d30d-118">Пример см. в разделе [Анимация свойства без использования раскадровки](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="1d30d-118">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d30d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1d30d-119">See also</span></span>

- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [<span data-ttu-id="1d30d-120">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="1d30d-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="1d30d-121">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="1d30d-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
