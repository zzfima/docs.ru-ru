---
title: 'Как: Оживить 3D вращения с помощью ключевых кадров'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: 2b9059df079125c34c70237c0f600751020044c6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112314"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames"></a>Как: Оживить 3D вращения с помощью ключевых кадров
В следующем примере <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> используется для вращения 3D-объекта, в то время как его ось вращения оживляет, что приводит к "колебанию". Эта анимация использует следующие ключевые кадры:  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>используется для создания гладкой, линейной интерполяции между значениями.  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>используется для создания внезапных "прыжков" между значениями (без интерполяции).  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>используется для создания переменного перехода между значениями в зависимости <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> от свойства. В приведенном ниже примере эта часть анимации начинается медленно, но ближе к концу временного сегмента ускоряется в геометрической прогрессии.  
  
## <a name="example"></a>Пример  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>См. также раздел

- [3D Графика Обзор](3-d-graphics-overview.md)
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Оживите 3D вращение с помощью раскадровки](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Оживите 3D вращение с помощью вращения3DAnimationи](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Оживите 3D Вращение с использованием кватернов](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [Оживите 3D-вращение с помощью ключевых кадров (кватернионАнимацияUsingKeyFrames)](animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
