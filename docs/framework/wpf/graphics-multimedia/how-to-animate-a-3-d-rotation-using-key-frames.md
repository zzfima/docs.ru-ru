---
title: Практическое руководство. Анимация трехмерного вращения с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3-D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: e72ec94f830f0f5001a77e7492aa1326a47b309d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762154"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames"></a><span data-ttu-id="37433-102">Практическое руководство. Анимация трехмерного вращения с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="37433-102">How to: Animate a 3-D Rotation Using Key Frames</span></span>
<span data-ttu-id="37433-103">В следующем примере <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> используется для создания трехмерный поворот объекта во время его ось вращения анимирует приводит к «Иванин».</span><span class="sxs-lookup"><span data-stu-id="37433-103">In the following example, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> is used to make a 3D object rotate while its axis of rotation animates resulting in a "wobble".</span></span> <span data-ttu-id="37433-104">Эта анимация использует следующие ключевые кадры:</span><span class="sxs-lookup"><span data-stu-id="37433-104">This animation uses the following key frames:</span></span>  
  
1. <span data-ttu-id="37433-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> используется для создания гладкой, линейной интерполяции между значениями.</span><span class="sxs-lookup"><span data-stu-id="37433-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="37433-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> используется для создания скачкообразные «переходы» между значениями (без интерполяции).</span><span class="sxs-lookup"><span data-stu-id="37433-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="37433-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> используется для, создают переменный переход между значениями в зависимости от <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="37433-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="37433-108">В следующем примере эта часть анимация начинается медленно, но к концу временного сегмента, экспоненциально ускоряется.</span><span class="sxs-lookup"><span data-stu-id="37433-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37433-109">Пример</span><span class="sxs-lookup"><span data-stu-id="37433-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="37433-110">См. также</span><span class="sxs-lookup"><span data-stu-id="37433-110">See also</span></span>

- [<span data-ttu-id="37433-111">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="37433-111">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="37433-112">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="37433-112">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="37433-113">Анимация трехмерного вращения с помощью раскадровки</span><span class="sxs-lookup"><span data-stu-id="37433-113">Animate a 3-D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="37433-114">Анимация трехмерного поворота с помощью Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="37433-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="37433-115">Анимация трехмерного вращения с помощью кватернионов</span><span class="sxs-lookup"><span data-stu-id="37433-115">Animate a 3-D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="37433-116">Анимация трехмерного поворота с помощью ключевых кадров (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="37433-116">Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>](animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
