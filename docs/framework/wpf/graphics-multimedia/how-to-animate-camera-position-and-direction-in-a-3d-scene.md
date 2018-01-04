---
title: "Практическое руководство. Изменение положения и направления камеры в 3D-сцене"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], camera position in 3-D scenes
- camera direction [WPF], animating in 3-D scenes
- 3-D scenes [WPF], animating camera position
- 3-D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3-D scenes
- animation [WPF], camera direction in 3-D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a8e80f1032e886d59240b74281c2ed87ad5743a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a>Практическое руководство. Изменение положения и направления камеры в 3D-сцене
В следующем примере показано, как анимации положения камеры и направления в трехмерной сцене. Это делается с помощью <xref:System.Windows.Media.Animation.Point3DAnimation> и <xref:System.Windows.Media.Animation.Vector3DAnimation> для анимации <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> и <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> свойства соответственно <xref:System.Windows.Media.Media3D.PerspectiveCamera>. Подобную анимацию можно использовать для изменения наблюдения кадра в ответ на событие.  
  
## <a name="example"></a>Пример  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Animation.Vector3DAnimation>  
 <xref:System.Windows.Media.Animation.Point3DAnimation>  
 [Анимация положения и направления камеры с помощью ключевых кадров](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-using-key-frames.md)  
 [Обзор трехмерной графики](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
