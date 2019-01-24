---
title: Как выполнить Применение материала к лицевой и обратной стороне трехмерного объекта
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3-D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 16f30e3a880d7dcc943a9583ba0f04c4bd682827
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652037"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a><span data-ttu-id="2e4d4-102">Как выполнить Применение материала к лицевой и обратной стороне трехмерного объекта</span><span class="sxs-lookup"><span data-stu-id="2e4d4-102">How to: Apply Material to the Front and Back of a 3-D Object</span></span>
<span data-ttu-id="2e4d4-103">В следующем примере показано, как применить <xref:System.Windows.Media.Media3D.Material> к лицевой и обратной стороне трехмерного объекта и анимация объекта для отображения обеих сторон объекта.</span><span class="sxs-lookup"><span data-stu-id="2e4d4-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3-D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="2e4d4-104"><xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> Свойство <xref:System.Windows.Media.Media3D.GeometryModel3D> используется для применения красной <xref:System.Windows.Media.Brush> к передней части объекта и <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> свойство <xref:System.Windows.Media.Media3D.GeometryModel3D> используется для применения синим <xref:System.Windows.Media.Brush> к обратной стороне объекта.</span><span class="sxs-lookup"><span data-stu-id="2e4d4-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="2e4d4-105">В приведенном ниже коде показано применение материалов к объекту:</span><span class="sxs-lookup"><span data-stu-id="2e4d4-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="2e4d4-106">Пример</span><span class="sxs-lookup"><span data-stu-id="2e4d4-106">Example</span></span>  
 <span data-ttu-id="2e4d4-107">В следующем коде показано весь пример.</span><span class="sxs-lookup"><span data-stu-id="2e4d4-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="2e4d4-108">См. также</span><span class="sxs-lookup"><span data-stu-id="2e4d4-108">See also</span></span>
- [<span data-ttu-id="2e4d4-109">Создание трехмерной сцены</span><span class="sxs-lookup"><span data-stu-id="2e4d4-109">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="2e4d4-110">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="2e4d4-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [<span data-ttu-id="2e4d4-111">Анимация свойств материалов в трехмерной сцене</span><span class="sxs-lookup"><span data-stu-id="2e4d4-111">Animate Material Properties in a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="2e4d4-112">Применение эмиссионного материала к трехмерному объекту</span><span class="sxs-lookup"><span data-stu-id="2e4d4-112">Apply Emissive Material to a 3-D Object</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)
