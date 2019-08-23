---
title: Практическое руководство. Использование MatrixTransform для создания пользовательских преобразований
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 1971d5fe9422c5138f140517e6fd4c9f9b2cf48b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913919"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="766c0-102">Практическое руководство. Использование MatrixTransform для создания пользовательских преобразований</span><span class="sxs-lookup"><span data-stu-id="766c0-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="766c0-103">В этом примере показано, как использовать <xref:System.Windows.Media.MatrixTransform> для перевода (перемещения) положения, растяжения и наклона. <xref:System.Windows.Controls.Button></span><span class="sxs-lookup"><span data-stu-id="766c0-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="766c0-104"><xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.Media.ScaleTransform> <xref:System.Windows.Media.SkewTransform> <xref:System.Windows.Media.RotateTransform>Используйте класс для создания пользовательских преобразований, не предоставляемых классами,, или. <xref:System.Windows.Media.MatrixTransform></span><span class="sxs-lookup"><span data-stu-id="766c0-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="766c0-105">Пример</span><span class="sxs-lookup"><span data-stu-id="766c0-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="766c0-106">См. также</span><span class="sxs-lookup"><span data-stu-id="766c0-106">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="766c0-107">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="766c0-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="766c0-108">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="766c0-108">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="766c0-109">Обзор фигур и базовых средств рисования в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="766c0-109">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
