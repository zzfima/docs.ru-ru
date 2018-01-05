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
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a><span data-ttu-id="28657-102">Практическое руководство. Анимация трехмерного вращения с помощью раскадровки</span><span class="sxs-lookup"><span data-stu-id="28657-102">How to: Animate a 3-D Rotation Using Storyboards</span></span>
<span data-ttu-id="28657-103">В следующем примере показано, как сделать трехмерный поворот во время его «качания» с помощью анимации объекта <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> и <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> свойства <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> объекта.</span><span class="sxs-lookup"><span data-stu-id="28657-103">The following example shows how to make a 3D object rotate while it "wobbles" by animating the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> and <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> properties of an <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object.</span></span> <span data-ttu-id="28657-104">Это <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> объект задает преобразование поворота 3D-объекта и поэтому анимации его свойств создает эффект желания поворота.</span><span class="sxs-lookup"><span data-stu-id="28657-104">This <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object specifies the rotation transform of the 3D object and so animating its properties creates the desire rotation effect.</span></span> <span data-ttu-id="28657-105">В раскадровку <xref:System.Windows.Media.Animation.DoubleAnimation> используется для анимации <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> свойство при <xref:System.Windows.Media.Animation.Vector3DAnimation> используется для анимации <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="28657-105">Within the Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> property while <xref:System.Windows.Media.Animation.Vector3DAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28657-106">Пример</span><span class="sxs-lookup"><span data-stu-id="28657-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="28657-107">См. также</span><span class="sxs-lookup"><span data-stu-id="28657-107">See Also</span></span>  
 [<span data-ttu-id="28657-108">Анимация трехмерного поворота с помощью Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="28657-108">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [<span data-ttu-id="28657-109">Анимация трехмерного поворота с помощью ключевых кадров (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="28657-109">Animate a 3-D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)  
 [<span data-ttu-id="28657-110">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="28657-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="28657-111">Общие сведения о раскадровке</span><span class="sxs-lookup"><span data-stu-id="28657-111">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
