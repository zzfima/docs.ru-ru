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
ms.openlocfilehash: 0700a7ae3f18f745b0d479ace3acbf2d7fbd9722
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48029395"
---
# <a name="how-to-apply-multiple-transforms-to-an-object"></a><span data-ttu-id="be8ee-102">Практическое руководство. Применение нескольких преобразований к объекту</span><span class="sxs-lookup"><span data-stu-id="be8ee-102">How to: Apply Multiple Transforms to an Object</span></span>
<span data-ttu-id="be8ee-103">В этом примере показано, как использовать <xref:System.Windows.Media.TransformGroup> для группировки двух или более <xref:System.Windows.Media.Transform> объектов в один составной <xref:System.Windows.Media.Transform>.</span><span class="sxs-lookup"><span data-stu-id="be8ee-103">This example shows how to use a <xref:System.Windows.Media.TransformGroup> to group two or more <xref:System.Windows.Media.Transform> objects into a single composite <xref:System.Windows.Media.Transform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be8ee-104">Пример</span><span class="sxs-lookup"><span data-stu-id="be8ee-104">Example</span></span>  
 <span data-ttu-id="be8ee-105">В следующем примере используется <xref:System.Windows.Media.TransformGroup> для применения <xref:System.Windows.Media.ScaleTransform> и <xref:System.Windows.Media.RotateTransform> для <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="be8ee-105">The following example uses a <xref:System.Windows.Media.TransformGroup> to apply a <xref:System.Windows.Media.ScaleTransform> and a <xref:System.Windows.Media.RotateTransform> to a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="be8ee-106">См. также</span><span class="sxs-lookup"><span data-stu-id="be8ee-106">See Also</span></span>  
 <xref:System.Windows.UIElement.RenderTransform%2A>  
 <xref:System.Windows.Media.TransformGroup>  
 [<span data-ttu-id="be8ee-107">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="be8ee-107">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="be8ee-108">Пример двумерных преобразований</span><span class="sxs-lookup"><span data-stu-id="be8ee-108">2-D Transforms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=158252)
