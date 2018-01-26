---
title: "Практическое руководство. Анимация трехмерного вращения с помощью раскадровки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aa67db777ee04edcafa6ca3a53a37a638992fe29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a>Практическое руководство. Анимация трехмерного вращения с помощью раскадровки
В следующем примере показано, как сделать трехмерный поворот во время его «качания» с помощью анимации объекта <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> и <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> свойства <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> объекта. Это <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> объект задает преобразование поворота 3D-объекта и поэтому анимации его свойств создает эффект желания поворота. В раскадровку <xref:System.Windows.Media.Animation.DoubleAnimation> используется для анимации <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> свойство при <xref:System.Windows.Media.Animation.Vector3DAnimation> используется для анимации <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> свойство.  
  
## <a name="example"></a>Пример  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>См. также  
 [Анимация трехмерного поворота с помощью Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [Анимация трехмерного поворота с помощью ключевых кадров (Rotation3DAnimationUsingKeyFrames)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)  
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [Общие сведения о раскадровке](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
