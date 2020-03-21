---
title: Практическое руководство. Применение нескольких преобразований к объекту
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- grouping Transform objects [WPF]
- Transform objects [WPF], grouping
- graphics [WPF], grouping Transform objects
- TransformGroup [WPF]
ms.assetid: 98cd1921-12bc-4bf5-8193-529228fb7402
ms.openlocfilehash: 3ef11104b2a4fc775d29d2a388c9a70a69a3f10f
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112119"
---
# <a name="how-to-apply-multiple-transforms-to-an-object"></a><span data-ttu-id="8abfe-102">Практическое руководство. Применение нескольких преобразований к объекту</span><span class="sxs-lookup"><span data-stu-id="8abfe-102">How to: Apply Multiple Transforms to an Object</span></span>
<span data-ttu-id="8abfe-103">В этом примере <xref:System.Windows.Media.TransformGroup> показано, как <xref:System.Windows.Media.Transform> использовать для группы два или более объектов в один состав. <xref:System.Windows.Media.Transform></span><span class="sxs-lookup"><span data-stu-id="8abfe-103">This example shows how to use a <xref:System.Windows.Media.TransformGroup> to group two or more <xref:System.Windows.Media.Transform> objects into a single composite <xref:System.Windows.Media.Transform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8abfe-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8abfe-104">Example</span></span>  
 <span data-ttu-id="8abfe-105">Следующий пример <xref:System.Windows.Media.TransformGroup> использует a <xref:System.Windows.Media.ScaleTransform> для <xref:System.Windows.Media.RotateTransform> применения <xref:System.Windows.Controls.Button>a и a к .</span><span class="sxs-lookup"><span data-stu-id="8abfe-105">The following example uses a <xref:System.Windows.Media.TransformGroup> to apply a <xref:System.Windows.Media.ScaleTransform> and a <xref:System.Windows.Media.RotateTransform> to a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="8abfe-106">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8abfe-106">See also</span></span>

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Media.TransformGroup>
- [<span data-ttu-id="8abfe-107">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="8abfe-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="8abfe-108">2D Преобразует образец</span><span class="sxs-lookup"><span data-stu-id="8abfe-108">2D Transforms Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
