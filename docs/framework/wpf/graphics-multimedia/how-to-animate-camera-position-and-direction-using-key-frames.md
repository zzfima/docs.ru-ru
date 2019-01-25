---
title: Как выполнить Анимация положения и направления камеры с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 3284b11939b6f0bb921a4cfeb7fd0d4172b46f69
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663561"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="e0e46-102">Как выполнить Анимация положения и направления камеры с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="e0e46-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="e0e46-103">В следующем примере <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> используется для анимации положения <xref:System.Windows.Media.Media3D.PerspectiveCamera> в трехмерной сцене.</span><span class="sxs-lookup"><span data-stu-id="e0e46-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="e0e46-104">Кроме того <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> используется для направления указывает камеры в трехмерной сцене.</span><span class="sxs-lookup"><span data-stu-id="e0e46-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="e0e46-105">Эти анимации используйте несколько ключевых кадров, которые создают серию эффектов анимации:</span><span class="sxs-lookup"><span data-stu-id="e0e46-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1.  <span data-ttu-id="e0e46-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> и <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> используются для создания гладкой, линейной интерполяции между значениями.</span><span class="sxs-lookup"><span data-stu-id="e0e46-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="e0e46-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> и <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> используются для создания скачкообразные «переходы» между значениями (без интерполяции).</span><span class="sxs-lookup"><span data-stu-id="e0e46-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <span data-ttu-id="e0e46-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> и <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> используются для, создают переменный переход между значениями в зависимости от <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="e0e46-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="e0e46-109">В приведенном ниже примере анимация начинается медленно, но к концу временного сегмента, экспоненциально ускоряется.</span><span class="sxs-lookup"><span data-stu-id="e0e46-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0e46-110">Пример</span><span class="sxs-lookup"><span data-stu-id="e0e46-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e0e46-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e0e46-111">See also</span></span>
- [<span data-ttu-id="e0e46-112">Анимация положения и направления камеры в трехмерной сцене</span><span class="sxs-lookup"><span data-stu-id="e0e46-112">Animate Camera Position and Direction in a 3D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [<span data-ttu-id="e0e46-113">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="e0e46-113">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
