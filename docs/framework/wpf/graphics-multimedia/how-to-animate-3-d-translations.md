---
title: Как выполнить Анимация трехмерных преобразований
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations
- 3-D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: e73035a48e32e3eec20b44c82b5b9ec6763c1e7c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653038"
---
# <a name="how-to-animate-3-d-translations"></a><span data-ttu-id="0c318-102">Как выполнить Анимация трехмерных преобразований</span><span class="sxs-lookup"><span data-stu-id="0c318-102">How to: Animate 3-D Translations</span></span>
<span data-ttu-id="0c318-103">В этом разделе показано, как анимировать преобразования перевода на [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] модели.</span><span class="sxs-lookup"><span data-stu-id="0c318-103">This topic demonstrates how to animate a translation transformation set on a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="0c318-104">В приведенном ниже коде показано применение <xref:System.Windows.Media.Media3D.TranslateTransform3D> объект <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> свойство <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="0c318-104">The code below shows the application of a <xref:System.Windows.Media.Media3D.TranslateTransform3D> object to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 <span data-ttu-id="0c318-105"><xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> Свойства данного объекта <xref:System.Windows.Media.Media3D.TranslateTransform3D> объекта анимируется с помощью следующего кода.</span><span class="sxs-lookup"><span data-stu-id="0c318-105">The <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> property of this <xref:System.Windows.Media.Media3D.TranslateTransform3D> object is animated using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a><span data-ttu-id="0c318-106">Пример</span><span class="sxs-lookup"><span data-stu-id="0c318-106">Example</span></span>  
 <span data-ttu-id="0c318-107">В следующем коде показано весь пример.</span><span class="sxs-lookup"><span data-stu-id="0c318-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0c318-108">См. также</span><span class="sxs-lookup"><span data-stu-id="0c318-108">See also</span></span>
- [<span data-ttu-id="0c318-109">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="0c318-109">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="0c318-110">Создание трехмерной сцены</span><span class="sxs-lookup"><span data-stu-id="0c318-110">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="0c318-111">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="0c318-111">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [<span data-ttu-id="0c318-112">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="0c318-112">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
