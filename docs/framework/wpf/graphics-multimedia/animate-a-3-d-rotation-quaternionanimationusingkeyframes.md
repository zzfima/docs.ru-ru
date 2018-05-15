---
title: Как анимировать 3-D поворот с помощью ключевых кадров (QuaternionAnimationUsingKeyFrames)
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3-D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 59514dcd617f73cc8c8e458dc13880b3521c0fb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a><span data-ttu-id="eaa7e-102">Как анимировать 3-D поворот с помощью ключевых кадров (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="eaa7e-102">How to: Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>
<span data-ttu-id="eaa7e-103">В следующем примере <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> используются, чтобы сделать трехмерный поворот объекта.</span><span class="sxs-lookup"><span data-stu-id="eaa7e-103">In the following example, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> is used to make a 3D object rotate.</span></span> <span data-ttu-id="eaa7e-104">Эта анимация использует следующие ключевые кадры:</span><span class="sxs-lookup"><span data-stu-id="eaa7e-104">This animation uses the following key frames:</span></span>  
  
1.  <span data-ttu-id="eaa7e-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> используется для создания гладкой, линейной интерполяции между значениями.</span><span class="sxs-lookup"><span data-stu-id="eaa7e-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="eaa7e-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> используется для создания резкие «переходы» между значениями (без интерполяции).</span><span class="sxs-lookup"><span data-stu-id="eaa7e-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <span data-ttu-id="eaa7e-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> используется для создания переменного перехода между значениями в зависимости от <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="eaa7e-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="eaa7e-108">В приведенном ниже примере эта часть анимации начинается медленно, но ближе к концу временного отрезка, экспоненциально ускоряется.</span><span class="sxs-lookup"><span data-stu-id="eaa7e-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eaa7e-109">Пример</span><span class="sxs-lookup"><span data-stu-id="eaa7e-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="eaa7e-110">См. также</span><span class="sxs-lookup"><span data-stu-id="eaa7e-110">See Also</span></span>  
 [<span data-ttu-id="eaa7e-111">Анимация трехмерного вращения с помощью раскадровки</span><span class="sxs-lookup"><span data-stu-id="eaa7e-111">Animate a 3-D Rotation Using Storyboards</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [<span data-ttu-id="eaa7e-112">Анимация трехмерного поворота с помощью Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="eaa7e-112">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [<span data-ttu-id="eaa7e-113">Анимация трехмерного вращения с помощью кватернионов</span><span class="sxs-lookup"><span data-stu-id="eaa7e-113">Animate a 3-D Rotation Using Quaternions</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)  
 [<span data-ttu-id="eaa7e-114">Анимация трехмерного поворота с помощью ключевых кадров (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="eaa7e-114">Animate a 3-D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)  
 [<span data-ttu-id="eaa7e-115">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="eaa7e-115">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="eaa7e-116">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="eaa7e-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
