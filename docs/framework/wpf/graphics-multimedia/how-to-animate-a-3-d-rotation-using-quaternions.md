---
title: 'Как: Оживить 3D вращения с использованием кватернов'
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3D translations [WPF], with quaternions
- 3D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: 0d229b0a714cc53459943fae751ab4d4f787d7d8
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112249"
---
# <a name="how-to-animate-a-3d-rotation-using-quaternions"></a>Как: Оживить 3D вращения с использованием кватернов
Этот пример показывает, как оживить вращение 3D-объекта с помощью кватернов.  
  
 Приведенный ниже <xref:System.Windows.Media.Media3D.QuaternionRotation3D> код показывает используемое <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> в <xref:System.Windows.Media.Media3D.RotateTransform3D>качестве значения для свойства .  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 Это <xref:System.Windows.Media.Media3D.QuaternionRotation3D> анимировано <xref:System.Windows.Media.Animation.QuaternionAnimation> <xref:System.Windows.Media.Animation.Storyboard> с в пределах использования кода ниже.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a>Пример  
 Следующий код показывает весь образец.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об эффектах анимации](animation-overview.md)
- [Создание 3D-сцены](how-to-create-a-3-d-scene.md)
- [3D Графика Обзор](3-d-graphics-overview.md)
- [Общие сведения о классах Transform](transforms-overview.md)
- [Оживите 3D вращение с помощью раскадровки](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Оживите 3D вращение с помощью вращения3DAnimationи](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
