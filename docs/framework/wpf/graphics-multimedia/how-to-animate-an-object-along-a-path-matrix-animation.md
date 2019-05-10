---
title: Практическое руководство. Анимация объекта вдоль контура (матричная анимация)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: 3c90d20cac60004aa9876d9fe8d213d33c5a6883
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651437"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a><span data-ttu-id="a9d6c-102">Практическое руководство. Анимация объекта вдоль контура (матричная анимация)</span><span class="sxs-lookup"><span data-stu-id="a9d6c-102">How to: Animate an Object Along a Path (Matrix Animation)</span></span>
<span data-ttu-id="a9d6c-103">В этом примере показано, как использовать <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> класс для анимации объекта вдоль пути, который определяется <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="a9d6c-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path that is defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9d6c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a9d6c-104">Example</span></span>  
 <span data-ttu-id="a9d6c-105">Следующий пример анимирует объект вдоль пути следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a9d6c-105">The following example animates an object along a path by doing the following:</span></span>  
  
- <span data-ttu-id="a9d6c-106">Применяет <xref:System.Windows.Media.MatrixTransform> к объекту, чтобы переместить его.</span><span class="sxs-lookup"><span data-stu-id="a9d6c-106">Applies a <xref:System.Windows.Media.MatrixTransform> to the object in order to move it.</span></span>  
  
- <span data-ttu-id="a9d6c-107">Определяет путь с помощью <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="a9d6c-107">Defines the path by using a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
- <span data-ttu-id="a9d6c-108">Создает <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> и использует его для анимации <xref:System.Windows.Media.Matrix> свойство <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="a9d6c-108">Creates a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and uses it to animate the <xref:System.Windows.Media.Matrix> property of the <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="a9d6c-109"><xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> Принимает <xref:System.Windows.Media.PathGeometry> и использует их для создания <xref:System.Windows.Media.Matrix> значения.</span><span class="sxs-lookup"><span data-stu-id="a9d6c-109">The <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> takes the <xref:System.Windows.Media.PathGeometry> and uses it to generate <xref:System.Windows.Media.Matrix> values.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 <span data-ttu-id="a9d6c-110">Полный пример см. в разделе [Пример анимации вдоль пути](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="a9d6c-110">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="a9d6c-111">Дополнительные сведения о геометрических путях см. в разделе [Общие сведения о геометрии](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a9d6c-111">For more information about geometric paths, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9d6c-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a9d6c-112">See also</span></span>

- [<span data-ttu-id="a9d6c-113">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="a9d6c-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="a9d6c-114">Пример анимации вдоль пути</span><span class="sxs-lookup"><span data-stu-id="a9d6c-114">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)
- [<span data-ttu-id="a9d6c-115">Практические руководства, посвященные анимации по контуру</span><span class="sxs-lookup"><span data-stu-id="a9d6c-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
