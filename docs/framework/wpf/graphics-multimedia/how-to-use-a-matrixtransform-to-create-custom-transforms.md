---
title: Практическое руководство. Использование MatrixTransform для создания пользовательских преобразований
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: aeccb961db539d4cc6dea75fb487fba06e59d6de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182316"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="89ef4-102">Практическое руководство. Использование MatrixTransform для создания пользовательских преобразований</span><span class="sxs-lookup"><span data-stu-id="89ef4-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="89ef4-103">В этом примере показано, как использовать <xref:System.Windows.Media.MatrixTransform> для переноса (перемещения) положение, растяжения и отклонение по <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="89ef4-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89ef4-104">Используйте <xref:System.Windows.Media.MatrixTransform> класса для создания пользовательских преобразований, которые не предоставляются службой <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, или <xref:System.Windows.Media.TranslateTransform> классы.</span><span class="sxs-lookup"><span data-stu-id="89ef4-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89ef4-105">Пример</span><span class="sxs-lookup"><span data-stu-id="89ef4-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="89ef4-106">См. также</span><span class="sxs-lookup"><span data-stu-id="89ef4-106">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="89ef4-107">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="89ef4-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="89ef4-108">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="89ef4-108">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="89ef4-109">Обзор фигур и базовых средств рисования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="89ef4-109">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
