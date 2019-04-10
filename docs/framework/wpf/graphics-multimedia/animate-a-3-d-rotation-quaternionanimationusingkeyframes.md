---
title: Практическое руководство. Анимация трехмерного поворота с помощью ключевых кадров (QuaternionAnimationUsingKeyFrames)
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3-D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 87176df26405a69cb2c3d63620def0575b750b52
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59338024"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a><span data-ttu-id="d0e88-102">Практическое руководство. Анимация трехмерного поворота с помощью ключевых кадров (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="d0e88-102">How to: Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>
<span data-ttu-id="d0e88-103">В следующем примере <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> используется для поворота трехмерного объекта.</span><span class="sxs-lookup"><span data-stu-id="d0e88-103">In the following example, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> is used to make a 3D object rotate.</span></span> <span data-ttu-id="d0e88-104">Эта анимация использует следующие ключевые кадры:</span><span class="sxs-lookup"><span data-stu-id="d0e88-104">This animation uses the following key frames:</span></span>  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> <span data-ttu-id="d0e88-105">используется для создания гладкой, линейной интерполяции между значениями.</span><span class="sxs-lookup"><span data-stu-id="d0e88-105">is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> <span data-ttu-id="d0e88-106">используется для создания скачкообразные «переходы» между значениями (без интерполяции).</span><span class="sxs-lookup"><span data-stu-id="d0e88-106">is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> <span data-ttu-id="d0e88-107">используется для, создают переменный переход между значениями в зависимости от <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="d0e88-107">is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="d0e88-108">В следующем примере эта часть анимация начинается медленно, но к концу временного сегмента, экспоненциально ускоряется.</span><span class="sxs-lookup"><span data-stu-id="d0e88-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0e88-109">Пример</span><span class="sxs-lookup"><span data-stu-id="d0e88-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d0e88-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d0e88-110">See also</span></span>

- [<span data-ttu-id="d0e88-111">Анимация трехмерного вращения с помощью раскадровки</span><span class="sxs-lookup"><span data-stu-id="d0e88-111">Animate a 3-D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="d0e88-112">Анимация трехмерного поворота с помощью Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="d0e88-112">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="d0e88-113">Анимация трехмерного вращения с помощью кватернионов</span><span class="sxs-lookup"><span data-stu-id="d0e88-113">Animate a 3-D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="d0e88-114">Анимация трехмерного поворота с помощью ключевых кадров (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="d0e88-114">Animate a 3-D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="d0e88-115">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="d0e88-115">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="d0e88-116">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="d0e88-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
