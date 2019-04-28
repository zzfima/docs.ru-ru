---
title: Практическое руководство. Анимация трехмерных преобразований
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations
- 3-D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 3e27c2d5f0cd44235a1d897b1b8f057808ae6bd8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762206"
---
# <a name="how-to-animate-3-d-translations"></a><span data-ttu-id="2ff1f-102">Практическое руководство. Анимация трехмерных преобразований</span><span class="sxs-lookup"><span data-stu-id="2ff1f-102">How to: Animate 3-D Translations</span></span>
<span data-ttu-id="2ff1f-103">В этом разделе показано, как анимировать преобразования перевода на [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] модели.</span><span class="sxs-lookup"><span data-stu-id="2ff1f-103">This topic demonstrates how to animate a translation transformation set on a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="2ff1f-104">В приведенном ниже коде показано применение <xref:System.Windows.Media.Media3D.TranslateTransform3D> объект <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> свойство <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="2ff1f-104">The code below shows the application of a <xref:System.Windows.Media.Media3D.TranslateTransform3D> object to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 <span data-ttu-id="2ff1f-105"><xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> Свойства данного объекта <xref:System.Windows.Media.Media3D.TranslateTransform3D> объекта анимируется с помощью следующего кода.</span><span class="sxs-lookup"><span data-stu-id="2ff1f-105">The <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> property of this <xref:System.Windows.Media.Media3D.TranslateTransform3D> object is animated using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a><span data-ttu-id="2ff1f-106">Пример</span><span class="sxs-lookup"><span data-stu-id="2ff1f-106">Example</span></span>  
 <span data-ttu-id="2ff1f-107">В следующем коде показано весь пример.</span><span class="sxs-lookup"><span data-stu-id="2ff1f-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="2ff1f-108">См. также</span><span class="sxs-lookup"><span data-stu-id="2ff1f-108">See also</span></span>

- [<span data-ttu-id="2ff1f-109">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="2ff1f-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="2ff1f-110">Создание трехмерной сцены</span><span class="sxs-lookup"><span data-stu-id="2ff1f-110">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="2ff1f-111">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="2ff1f-111">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="2ff1f-112">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="2ff1f-112">Transforms Overview</span></span>](transforms-overview.md)
