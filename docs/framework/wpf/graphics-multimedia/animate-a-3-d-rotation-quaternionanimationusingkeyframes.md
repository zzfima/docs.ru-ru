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
# <a name="how-to-animate-a-3d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a>Как: Оживить 3D вращения с помощью ключевых кадров (КватернионАнимацияUsingKeyFrames)
В следующем примере <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> используется для вращения 3D-объекта. Эта анимация использует следующие ключевые кадры:  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>используется для создания гладкой, линейной интерполяции между значениями.  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>используется для создания внезапных "прыжков" между значениями (без интерполяции).  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>используется для создания переменного перехода между значениями в зависимости <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> от свойства. В приведенном ниже примере эта часть анимации начинается медленно, но ближе к концу временного сегмента ускоряется в геометрической прогрессии.  
  
## <a name="example"></a>Пример  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>См. также раздел

- [Оживите 3D вращение с помощью раскадровки](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Оживите 3D вращение с помощью вращения3DAnimationи](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Оживите 3D Вращение с использованием кватернов](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [Оживите 3D-вращение с помощью ключевых кадров (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [3D Графика Обзор](3-d-graphics-overview.md)
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
