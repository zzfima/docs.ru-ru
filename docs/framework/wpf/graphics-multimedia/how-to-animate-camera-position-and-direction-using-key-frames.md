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
ms.openlocfilehash: 28471f9b42140a6c75b043d33939503528b63194
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112171"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="740aa-102">Практическое руководство. Анимация положения и направления камеры с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="740aa-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="740aa-103">В следующем примере используется <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> для анимирования <xref:System.Windows.Media.Media3D.PerspectiveCamera> положения в 3D-сцене.</span><span class="sxs-lookup"><span data-stu-id="740aa-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="740aa-104">Кроме того, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> используется для анимировать направление, в котором камера указывает на 3D-сцену.</span><span class="sxs-lookup"><span data-stu-id="740aa-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="740aa-105">Обе эти анимации используют несколько ключевых кадров, которые создают серию анимационных эффектов:</span><span class="sxs-lookup"><span data-stu-id="740aa-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1. <span data-ttu-id="740aa-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame>и <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> используются для создания гладкой, линейной интерполяции между значениями.</span><span class="sxs-lookup"><span data-stu-id="740aa-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="740aa-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame>и <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> используются для создания внезапных "прыжков" между значениями (без интерполяции).</span><span class="sxs-lookup"><span data-stu-id="740aa-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="740aa-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>и <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> используются для создания переменного перехода между <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> значениями в зависимости от свойства.</span><span class="sxs-lookup"><span data-stu-id="740aa-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="740aa-109">В приведенном ниже примере анимация начинается медленно, но ближе к концу временного сегмента ускоряется в геометрической прогрессии.</span><span class="sxs-lookup"><span data-stu-id="740aa-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="740aa-110">Пример</span><span class="sxs-lookup"><span data-stu-id="740aa-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="740aa-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="740aa-111">See also</span></span>

- [<span data-ttu-id="740aa-112">Анимация положения и направления камеры в трехмерной сцене</span><span class="sxs-lookup"><span data-stu-id="740aa-112">Animate Camera Position and Direction in a 3D Scene</span></span>](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [<span data-ttu-id="740aa-113">3D Графика Обзор</span><span class="sxs-lookup"><span data-stu-id="740aa-113">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
