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
# <a name="how-to-animate-a-3d-rotation-using-storyboards"></a><span data-ttu-id="0bce6-102">Как: Оживить 3D вращения с помощью раскадровки</span><span class="sxs-lookup"><span data-stu-id="0bce6-102">How to: Animate a 3D Rotation Using Storyboards</span></span>
<span data-ttu-id="0bce6-103">Ниже приводится следующий пример, как сделать 3D-объект вращаться, пока <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> он "колеблется" путем одиования и свойств <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> объекта.</span><span class="sxs-lookup"><span data-stu-id="0bce6-103">The following example shows how to make a 3D object rotate while it "wobbles" by animating the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> and <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> properties of an <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object.</span></span> <span data-ttu-id="0bce6-104">Этот <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> объект определяет преобразование вращения 3D-объекта и таким образом олицетворяет его свойства, создает эффект вращения желания.</span><span class="sxs-lookup"><span data-stu-id="0bce6-104">This <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object specifies the rotation transform of the 3D object and so animating its properties creates the desire rotation effect.</span></span> <span data-ttu-id="0bce6-105">В <xref:System.Windows.Media.Animation.DoubleAnimation> раскадровке, используется для <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> анимировать свойство в то время как <xref:System.Windows.Media.Animation.Vector3DAnimation> используется для анимировать свойство. <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A></span><span class="sxs-lookup"><span data-stu-id="0bce6-105">Within the Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> property while <xref:System.Windows.Media.Animation.Vector3DAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bce6-106">Пример</span><span class="sxs-lookup"><span data-stu-id="0bce6-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0bce6-107">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0bce6-107">See also</span></span>

- [<span data-ttu-id="0bce6-108">Оживите 3D вращение с помощью вращения3DAnimationи</span><span class="sxs-lookup"><span data-stu-id="0bce6-108">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="0bce6-109">Оживите 3D-вращение с помощью ключевых кадров (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="0bce6-109">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="0bce6-110">3D Графика Обзор</span><span class="sxs-lookup"><span data-stu-id="0bce6-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="0bce6-111">Общие сведения о раскадровке</span><span class="sxs-lookup"><span data-stu-id="0bce6-111">Storyboards Overview</span></span>](storyboards-overview.md)
