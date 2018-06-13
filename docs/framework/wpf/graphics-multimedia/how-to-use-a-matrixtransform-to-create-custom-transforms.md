---
title: Практическое руководство. Использование класса MatrixTransform для создания пользовательских преобразований
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 4ffbefea498e9a2bdc5546d112f6ff10e12fed67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561164"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="f3f21-102">Практическое руководство. Использование класса MatrixTransform для создания пользовательских преобразований</span><span class="sxs-lookup"><span data-stu-id="f3f21-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="f3f21-103">В этом примере показано, как использовать <xref:System.Windows.Media.MatrixTransform> для переноса (перемещения) положение, растягивать и наклон <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="f3f21-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3f21-104">Используйте <xref:System.Windows.Media.MatrixTransform> класс для создания пользовательских преобразований, которые не предоставляются <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, или <xref:System.Windows.Media.TranslateTransform> классы.</span><span class="sxs-lookup"><span data-stu-id="f3f21-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3f21-105">Пример</span><span class="sxs-lookup"><span data-stu-id="f3f21-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="f3f21-106">См. также</span><span class="sxs-lookup"><span data-stu-id="f3f21-106">See Also</span></span>  
 <xref:System.Windows.Media.MatrixTransform>  
 <xref:System.Windows.Media.Transform>  
 [<span data-ttu-id="f3f21-107">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="f3f21-107">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="f3f21-108">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="f3f21-108">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)  
 [<span data-ttu-id="f3f21-109">Обзор фигур и базовых средств рисования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="f3f21-109">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
