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
# <a name="how-to-animate-a-3d-rotation-using-quaternions"></a><span data-ttu-id="a1e8f-102">Как: Оживить 3D вращения с использованием кватернов</span><span class="sxs-lookup"><span data-stu-id="a1e8f-102">How to: Animate a 3D Rotation Using Quaternions</span></span>
<span data-ttu-id="a1e8f-103">Этот пример показывает, как оживить вращение 3D-объекта с помощью кватернов.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-103">This example shows how to animate a rotation of a 3D object using quaternions.</span></span>  
  
 <span data-ttu-id="a1e8f-104">Приведенный ниже <xref:System.Windows.Media.Media3D.QuaternionRotation3D> код показывает используемое <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> в <xref:System.Windows.Media.Media3D.RotateTransform3D>качестве значения для свойства .</span><span class="sxs-lookup"><span data-stu-id="a1e8f-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="a1e8f-105">Это <xref:System.Windows.Media.Media3D.QuaternionRotation3D> анимировано <xref:System.Windows.Media.Animation.QuaternionAnimation> <xref:System.Windows.Media.Animation.Storyboard> с в пределах использования кода ниже.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="a1e8f-106">Пример</span><span class="sxs-lookup"><span data-stu-id="a1e8f-106">Example</span></span>  
 <span data-ttu-id="a1e8f-107">Следующий код показывает весь образец.</span><span class="sxs-lookup"><span data-stu-id="a1e8f-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a1e8f-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a1e8f-108">See also</span></span>

- [<span data-ttu-id="a1e8f-109">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="a1e8f-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="a1e8f-110">Создание 3D-сцены</span><span class="sxs-lookup"><span data-stu-id="a1e8f-110">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="a1e8f-111">3D Графика Обзор</span><span class="sxs-lookup"><span data-stu-id="a1e8f-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="a1e8f-112">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="a1e8f-112">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="a1e8f-113">Оживите 3D вращение с помощью раскадровки</span><span class="sxs-lookup"><span data-stu-id="a1e8f-113">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="a1e8f-114">Оживите 3D вращение с помощью вращения3DAnimationи</span><span class="sxs-lookup"><span data-stu-id="a1e8f-114">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
