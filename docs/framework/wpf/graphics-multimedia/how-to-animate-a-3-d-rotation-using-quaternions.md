---
title: Практическое руководство. Анимация трехмерного вращения с помощью кватернионов
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3-D translations [WPF], with quaternions
- 3-D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: 079358ec12da803c8aa497bce1c272fa51f1c3b5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368575"
---
# <a name="how-to-animate-a-3-d-rotation-using-quaternions"></a><span data-ttu-id="83e65-102">Практическое руководство. Анимация трехмерного вращения с помощью кватернионов</span><span class="sxs-lookup"><span data-stu-id="83e65-102">How to: Animate a 3-D Rotation Using Quaternions</span></span>
<span data-ttu-id="83e65-103">В этом примере демонстрируется анимация поворота трехмерного объекта с помощью кватернионов.</span><span class="sxs-lookup"><span data-stu-id="83e65-103">This example shows how to animate a rotation of a 3-D object using quaternions.</span></span>  
  
 <span data-ttu-id="83e65-104">В коде ниже показан <xref:System.Windows.Media.Media3D.QuaternionRotation3D> используется в качестве значения для <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> свойство <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span><span class="sxs-lookup"><span data-stu-id="83e65-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="83e65-105">Это <xref:System.Windows.Media.Media3D.QuaternionRotation3D> анимируется с <xref:System.Windows.Media.Animation.QuaternionAnimation> в <xref:System.Windows.Media.Animation.Storyboard> с помощью следующего кода.</span><span class="sxs-lookup"><span data-stu-id="83e65-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="83e65-106">Пример</span><span class="sxs-lookup"><span data-stu-id="83e65-106">Example</span></span>  
 <span data-ttu-id="83e65-107">В следующем коде показано весь пример.</span><span class="sxs-lookup"><span data-stu-id="83e65-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="83e65-108">См. также</span><span class="sxs-lookup"><span data-stu-id="83e65-108">See also</span></span>
- [<span data-ttu-id="83e65-109">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="83e65-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="83e65-110">Создание трехмерной сцены</span><span class="sxs-lookup"><span data-stu-id="83e65-110">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="83e65-111">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="83e65-111">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="83e65-112">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="83e65-112">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="83e65-113">Анимация трехмерного вращения с помощью раскадровки</span><span class="sxs-lookup"><span data-stu-id="83e65-113">Animate a 3-D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="83e65-114">Анимация трехмерного поворота с помощью Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="83e65-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
