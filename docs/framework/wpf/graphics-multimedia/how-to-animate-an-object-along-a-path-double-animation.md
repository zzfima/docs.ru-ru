---
title: Практическое руководство. Анимация объекта вдоль пути (двойная анимация)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
ms.openlocfilehash: 3dcdf6cfe8631ae0b7b1472e22d027cf9288a1db
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43749740"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a><span data-ttu-id="c2976-102">Практическое руководство. Анимация объекта вдоль пути (двойная анимация)</span><span class="sxs-lookup"><span data-stu-id="c2976-102">How to: Animate an Object Along a Path (Double Animation)</span></span>
<span data-ttu-id="c2976-103">В этом примере показано, как использовать <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> класс для перемещения объекта вдоль пути, определенного с <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="c2976-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> class to move an object along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2976-104">Пример</span><span class="sxs-lookup"><span data-stu-id="c2976-104">Example</span></span>  
 <span data-ttu-id="c2976-105">В следующем примере используется два <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> объекты для перемещения прямоугольника вдоль геометрического пути:</span><span class="sxs-lookup"><span data-stu-id="c2976-105">The following example uses two <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path:</span></span>  
  
-   <span data-ttu-id="c2976-106">Первый <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> анимирует <xref:System.Windows.Media.TranslateTransform.X%2A> из <xref:System.Windows.Media.TranslateTransform> примененного к прямоугольнику.</span><span class="sxs-lookup"><span data-stu-id="c2976-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.X%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="c2976-107">В результате прямоугольник перемещается горизонтально вдоль пути.</span><span class="sxs-lookup"><span data-stu-id="c2976-107">It makes the rectangle move horizontally along the path.</span></span>  
  
-   <span data-ttu-id="c2976-108">Второй <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> анимирует <xref:System.Windows.Media.TranslateTransform.Y%2A> из <xref:System.Windows.Media.TranslateTransform> примененного к прямоугольнику.</span><span class="sxs-lookup"><span data-stu-id="c2976-108">The second <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.Y%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="c2976-109">В результате прямоугольник перемещается вертикально вдоль пути.</span><span class="sxs-lookup"><span data-stu-id="c2976-109">It makes the rectangle move vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 <span data-ttu-id="c2976-110">Полный пример см. в разделе [Пример анимации вдоль пути](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="c2976-110">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="c2976-111">Другой способ перемещения объекта с помощью геометрического пути является использование <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> объекта.</span><span class="sxs-lookup"><span data-stu-id="c2976-111">Another way to move an object using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object.</span></span> <span data-ttu-id="c2976-112">Например, см. в разделе [анимация объекта вдоль пути (матричная анимация)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="c2976-112">For an example, see [Animate an Object Along a Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2976-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c2976-113">See Also</span></span>  
 [<span data-ttu-id="c2976-114">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="c2976-114">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="c2976-115">Практические руководства, посвященные анимации по контуру</span><span class="sxs-lookup"><span data-stu-id="c2976-115">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
