---
title: Практическое руководство. Анимация положения и направления камеры с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 5be14513755c3b5c80c13cbc5cae889cc4663cec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558847"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="0dd91-102">Практическое руководство. Анимация положения и направления камеры с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="0dd91-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="0dd91-103">В следующем примере <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> используется для анимации положения <xref:System.Windows.Media.Media3D.PerspectiveCamera> в трехмерной сцене.</span><span class="sxs-lookup"><span data-stu-id="0dd91-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="0dd91-104">Кроме того <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> используется для направления в трехмерной сцене указывает камера.</span><span class="sxs-lookup"><span data-stu-id="0dd91-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="0dd91-105">Эти анимации используйте несколько ключевых кадров, создающих ряд эффектов анимации.</span><span class="sxs-lookup"><span data-stu-id="0dd91-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1.  <span data-ttu-id="0dd91-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> и <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> используются для создания гладкой, линейной интерполяции между значениями.</span><span class="sxs-lookup"><span data-stu-id="0dd91-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="0dd91-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> и <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> используются для создания резкие «переходы» между значениями (без интерполяции).</span><span class="sxs-lookup"><span data-stu-id="0dd91-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <span data-ttu-id="0dd91-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> и <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> используются для создания переменного перехода между значениями в зависимости от <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="0dd91-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="0dd91-109">В следующем примере анимация начинается медленно, но ближе к концу временного отрезка, экспоненциально ускоряется.</span><span class="sxs-lookup"><span data-stu-id="0dd91-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0dd91-110">Пример</span><span class="sxs-lookup"><span data-stu-id="0dd91-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0dd91-111">См. также</span><span class="sxs-lookup"><span data-stu-id="0dd91-111">See Also</span></span>  
 [<span data-ttu-id="0dd91-112">Анимация положения и направления камеры в трехмерной сцене</span><span class="sxs-lookup"><span data-stu-id="0dd91-112">Animate Camera Position and Direction in a 3D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-in-a-3d-scene.md)  
 [<span data-ttu-id="0dd91-113">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="0dd91-113">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
