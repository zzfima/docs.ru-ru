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
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a>Практическое руководство. Анимация положения и направления камеры с помощью ключевых кадров
В следующем примере используется <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> для анимирования <xref:System.Windows.Media.Media3D.PerspectiveCamera> положения в 3D-сцене. Кроме того, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> используется для анимировать направление, в котором камера указывает на 3D-сцену. Обе эти анимации используют несколько ключевых кадров, которые создают серию анимационных эффектов:  
  
1. <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame>и <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> используются для создания гладкой, линейной интерполяции между значениями.  
  
2. <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame>и <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> используются для создания внезапных "прыжков" между значениями (без интерполяции).  
  
3. <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>и <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> используются для создания переменного перехода между <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> значениями в зависимости от свойства. В приведенном ниже примере анимация начинается медленно, но ближе к концу временного сегмента ускоряется в геометрической прогрессии.  
  
## <a name="example"></a>Пример  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>См. также раздел

- [Анимация положения и направления камеры в трехмерной сцене](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [3D Графика Обзор](3-d-graphics-overview.md)
