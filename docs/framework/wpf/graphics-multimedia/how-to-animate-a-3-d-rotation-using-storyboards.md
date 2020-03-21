---
title: 'Как: Оживить 3D вращения с помощью раскадровки'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 088f1a33cfc73a706ffed55ffff6494adaf8fca4
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112221"
---
# <a name="how-to-animate-a-3d-rotation-using-storyboards"></a>Как: Оживить 3D вращения с помощью раскадровки
Ниже приводится следующий пример, как сделать 3D-объект вращаться, пока <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> он "колеблется" путем одиования и свойств <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> объекта. Этот <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> объект определяет преобразование вращения 3D-объекта и таким образом олицетворяет его свойства, создает эффект вращения желания. В <xref:System.Windows.Media.Animation.DoubleAnimation> раскадровке, используется для <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> анимировать свойство в то время как <xref:System.Windows.Media.Animation.Vector3DAnimation> используется для анимировать свойство. <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A>  
  
## <a name="example"></a>Пример  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>См. также раздел

- [Оживите 3D вращение с помощью вращения3DAnimationи](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Оживите 3D-вращение с помощью ключевых кадров (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [3D Графика Обзор](3-d-graphics-overview.md)
- [Общие сведения о раскадровке](storyboards-overview.md)
