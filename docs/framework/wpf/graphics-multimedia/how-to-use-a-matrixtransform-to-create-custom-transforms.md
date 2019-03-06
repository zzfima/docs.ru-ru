---
title: Практическое руководство. Использование MatrixTransform для создания пользовательских преобразований
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 179c7986b6a7021f4e1245aef01eb555108ebf4f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358864"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a>Практическое руководство. Использование MatrixTransform для создания пользовательских преобразований
В этом примере показано, как использовать <xref:System.Windows.Media.MatrixTransform> для переноса (перемещения) положение, растяжения и отклонение по <xref:System.Windows.Controls.Button>.  
  
> [!NOTE]
>  Используйте <xref:System.Windows.Media.MatrixTransform> класса для создания пользовательских преобразований, которые не предоставляются службой <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, или <xref:System.Windows.Media.TranslateTransform> классы.  
  
## <a name="example"></a>Пример  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [Общие сведения о классах Transform](transforms-overview.md)
- [Разделы практического руководства](transformations-how-to-topics.md)
- [Обзор фигур и базовых средств рисования в приложении WPF](shapes-and-basic-drawing-in-wpf-overview.md)
