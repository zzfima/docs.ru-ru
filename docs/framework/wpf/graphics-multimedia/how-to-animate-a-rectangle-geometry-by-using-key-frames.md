---
title: Практическое руководство. Анимация прямоугольника с помощью ключевых кадров
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344668"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="d0e8c-102">Практическое руководство. Анимация прямоугольника с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="d0e8c-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="d0e8c-103">В этом примере показано, <xref:System.Windows.Media.RectangleGeometry.Rect%2A> как <xref:System.Windows.Media.RectangleGeometry> оживить свойство элемента с помощью ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="d0e8c-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0e8c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d0e8c-104">Example</span></span>  
 <span data-ttu-id="d0e8c-105">В следующем примере <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> используется класс <xref:System.Windows.Media.RectangleGeometry.Rect%2A> для анимировать свойство <xref:System.Windows.Media.RectangleGeometry>.</span><span class="sxs-lookup"><span data-stu-id="d0e8c-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="d0e8c-106">Эта анимация использует три ключевых кадра следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d0e8c-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="d0e8c-107">В течение первых двух секунд используется <xref:System.Windows.Media.Animation.LinearRectKeyFrame> экземпляр класса для анимирования постепенного изменения положения, ширины и высоты прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="d0e8c-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="d0e8c-108">Линейные ключевые <xref:System.Windows.Media.Animation.LinearRectKeyFrame> кадры, такие как создание плавного линейного перехода между значениями.</span><span class="sxs-lookup"><span data-stu-id="d0e8c-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="d0e8c-109">В конце следующей половины секунды, <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> использует экземпляр класса, чтобы внезапно уменьшить высоту прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="d0e8c-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="d0e8c-110">Дискретные ключевые <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> кадры, такие как создают внезапные изменения между значениями, то есть снижение высоты происходит быстро и не является тонким.</span><span class="sxs-lookup"><span data-stu-id="d0e8c-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="d0e8c-111">В течение последних двух секунд, <xref:System.Windows.Media.Animation.SplineRectKeyFrame> использует экземпляр класса, чтобы изменить прямоугольник обратно в свой первоначальный размер и положение.</span><span class="sxs-lookup"><span data-stu-id="d0e8c-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="d0e8c-112">Сплайс-ключевые кадры, такие как <xref:System.Windows.Media.Animation.SplineRectKeyFrame> создание переменного <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> перехода между значениями в зависимости от значений свойства.</span><span class="sxs-lookup"><span data-stu-id="d0e8c-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="d0e8c-113">В этом примере изменение начинается медленно и ускоряется экспоненциально к концу временного сегмента.</span><span class="sxs-lookup"><span data-stu-id="d0e8c-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="d0e8c-114">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="d0e8c-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0e8c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d0e8c-115">See also</span></span>

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [<span data-ttu-id="d0e8c-116">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="d0e8c-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="d0e8c-117">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="d0e8c-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
