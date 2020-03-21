---
title: Практическое руководство. Изменение положения и направления камеры в 3D-сцене
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera position in 3D scenes
- camera direction [WPF], animating in 3D scenes
- 3D scenes [WPF], animating camera position
- 3D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3D scenes
- animation [WPF], camera direction in 3D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
ms.openlocfilehash: 5ce94e154cd5aa29b59260f893ec2b63a08db0fc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112220"
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a>Практическое руководство. Изменение положения и направления камеры в 3D-сцене
Ниже приводится следующий пример, как оживить положение камеры и оживить направление, в котором она указывает в 3D-сцене. Это делается <xref:System.Windows.Media.Animation.Point3DAnimation> с <xref:System.Windows.Media.Animation.Vector3DAnimation> помощью и <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> для анимировать <xref:System.Windows.Media.Media3D.PerspectiveCamera>и свойства соответственно . Таким образом, можно использовать такую анимацию, чтобы изменить представление зрителя о сцене в ответ на событие.  
  
## <a name="example"></a>Пример  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Animation.Vector3DAnimation>
- <xref:System.Windows.Media.Animation.Point3DAnimation>
- [Анимация положения и направления камеры с помощью ключевых кадров](how-to-animate-camera-position-and-direction-using-key-frames.md)
- [3D Графика Обзор](3-d-graphics-overview.md)
