---
title: 'Как: Оживить 3D вращения с помощью ключевых кадров (КватернионАнимацияUsingKeyFrames)'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 5273183aaa49a743cc401dec0b4b16bae09e3129
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112301"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a><span data-ttu-id="2646f-102">Как: Оживить 3D вращения с помощью ключевых кадров (КватернионАнимацияUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="2646f-102">How to: Animate a 3D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>
<span data-ttu-id="2646f-103">В следующем примере <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> используется для вращения 3D-объекта.</span><span class="sxs-lookup"><span data-stu-id="2646f-103">In the following example, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> is used to make a 3D object rotate.</span></span> <span data-ttu-id="2646f-104">Эта анимация использует следующие ключевые кадры:</span><span class="sxs-lookup"><span data-stu-id="2646f-104">This animation uses the following key frames:</span></span>  
  
1. <span data-ttu-id="2646f-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>используется для создания гладкой, линейной интерполяции между значениями.</span><span class="sxs-lookup"><span data-stu-id="2646f-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="2646f-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>используется для создания внезапных "прыжков" между значениями (без интерполяции).</span><span class="sxs-lookup"><span data-stu-id="2646f-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="2646f-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>используется для создания переменного перехода между значениями в зависимости <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> от свойства.</span><span class="sxs-lookup"><span data-stu-id="2646f-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="2646f-108">В приведенном ниже примере эта часть анимации начинается медленно, но ближе к концу временного сегмента ускоряется в геометрической прогрессии.</span><span class="sxs-lookup"><span data-stu-id="2646f-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2646f-109">Пример</span><span class="sxs-lookup"><span data-stu-id="2646f-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="2646f-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2646f-110">See also</span></span>

- [<span data-ttu-id="2646f-111">Оживите 3D вращение с помощью раскадровки</span><span class="sxs-lookup"><span data-stu-id="2646f-111">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="2646f-112">Оживите 3D вращение с помощью вращения3DAnimationи</span><span class="sxs-lookup"><span data-stu-id="2646f-112">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="2646f-113">Оживите 3D Вращение с использованием кватернов</span><span class="sxs-lookup"><span data-stu-id="2646f-113">Animate a 3D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="2646f-114">Оживите 3D-вращение с помощью ключевых кадров (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="2646f-114">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="2646f-115">3D Графика Обзор</span><span class="sxs-lookup"><span data-stu-id="2646f-115">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="2646f-116">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="2646f-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
