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
ms.openlocfilehash: 084caac26fd68b6914ec3858652ec44557a0dbd7
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452861"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a><span data-ttu-id="72bbc-102">Практическое руководство. Анимация объекта вдоль пути (двойная анимация)</span><span class="sxs-lookup"><span data-stu-id="72bbc-102">How to: Animate an Object Along a Path (Double Animation)</span></span>
<span data-ttu-id="72bbc-103">В этом примере показано, как использовать класс <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> для перемещения объекта вдоль пути, определенного <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="72bbc-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> class to move an object along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72bbc-104">Пример</span><span class="sxs-lookup"><span data-stu-id="72bbc-104">Example</span></span>  
 <span data-ttu-id="72bbc-105">В следующем примере используются два объекта <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> для перемещения прямоугольника вдоль геометрического пути:</span><span class="sxs-lookup"><span data-stu-id="72bbc-105">The following example uses two <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path:</span></span>  
  
- <span data-ttu-id="72bbc-106">Первый <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> анимируется <xref:System.Windows.Media.TranslateTransform.X%2A> <xref:System.Windows.Media.TranslateTransform>, применяемого к прямоугольнику.</span><span class="sxs-lookup"><span data-stu-id="72bbc-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.X%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="72bbc-107">В результате прямоугольник перемещается горизонтально вдоль пути.</span><span class="sxs-lookup"><span data-stu-id="72bbc-107">It makes the rectangle move horizontally along the path.</span></span>  
  
- <span data-ttu-id="72bbc-108">Вторая <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> анимируется <xref:System.Windows.Media.TranslateTransform.Y%2A> <xref:System.Windows.Media.TranslateTransform>, применяемого к прямоугольнику.</span><span class="sxs-lookup"><span data-stu-id="72bbc-108">The second <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.Y%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="72bbc-109">В результате прямоугольник перемещается вертикально вдоль пути.</span><span class="sxs-lookup"><span data-stu-id="72bbc-109">It makes the rectangle move vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 <span data-ttu-id="72bbc-110">Полный пример см. в разделе [Пример анимации по путям](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span><span class="sxs-lookup"><span data-stu-id="72bbc-110">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="72bbc-111">Другой способ перемещения объекта с помощью геометрического пути заключается в использовании объекта <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>.</span><span class="sxs-lookup"><span data-stu-id="72bbc-111">Another way to move an object using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object.</span></span> <span data-ttu-id="72bbc-112">Пример см. в разделе [анимация объекта вдоль пути (матричная анимация)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="72bbc-112">For an example, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72bbc-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="72bbc-113">See also</span></span>

- [<span data-ttu-id="72bbc-114">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="72bbc-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="72bbc-115">Практические руководства, посвященные анимации вдоль пути</span><span class="sxs-lookup"><span data-stu-id="72bbc-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
