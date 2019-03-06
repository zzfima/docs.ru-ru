---
title: Практическое руководство. Анимация свойств материалов в трехмерной сцене
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3-D scenes
- animation [WPF], Material properties in 3-D scenes
- 3-D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: 59200fa7ec7acb16c37666505143a3679d487f52
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358796"
---
# <a name="how-to-animate-material-properties-in-a-3-d-scene"></a><span data-ttu-id="266d6-102">Практическое руководство. Анимация свойств материалов в трехмерной сцене</span><span class="sxs-lookup"><span data-stu-id="266d6-102">How to: Animate Material Properties in a 3-D Scene</span></span>
<span data-ttu-id="266d6-103">В этом примере демонстрируется анимация <xref:System.Windows.Media.Brush.Opacity%2A> свойство <xref:System.Windows.Media.Media3D.Material> применяется к [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] модели.</span><span class="sxs-lookup"><span data-stu-id="266d6-103">This example shows how to animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Media3D.Material> applied to a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="266d6-104">В следующем примере кода определяется <xref:System.Windows.Media.LinearGradientBrush> используется в качестве <xref:System.Windows.Media.Media3D.Material> трехмерного объекта.</span><span class="sxs-lookup"><span data-stu-id="266d6-104">The following code example defines the <xref:System.Windows.Media.LinearGradientBrush> used as the <xref:System.Windows.Media.Media3D.Material> applied to the 3D object.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 <span data-ttu-id="266d6-105"><xref:System.Windows.Media.Brush.Opacity%2A> Свойства данного объекта <xref:System.Windows.Media.LinearGradientBrush> анимируется с помощью в примере кода.</span><span class="sxs-lookup"><span data-stu-id="266d6-105">The <xref:System.Windows.Media.Brush.Opacity%2A> property of this <xref:System.Windows.Media.LinearGradientBrush> is animated using the code example below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="266d6-106">Пример</span><span class="sxs-lookup"><span data-stu-id="266d6-106">Example</span></span>  
 <span data-ttu-id="266d6-107">В следующем коде показано весь пример.</span><span class="sxs-lookup"><span data-stu-id="266d6-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="266d6-108">См. также</span><span class="sxs-lookup"><span data-stu-id="266d6-108">See also</span></span>
- [<span data-ttu-id="266d6-109">Создание трехмерной сцены</span><span class="sxs-lookup"><span data-stu-id="266d6-109">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="266d6-110">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="266d6-110">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
