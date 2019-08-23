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
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a>Практическое руководство. Использование MatrixTransform для создания пользовательских преобразований
В этом примере показано, как использовать <xref:System.Windows.Media.MatrixTransform> для перевода (перемещения) положения, растяжения и наклона. <xref:System.Windows.Controls.Button>  
  
> [!NOTE]
> <xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.Media.ScaleTransform> <xref:System.Windows.Media.SkewTransform> <xref:System.Windows.Media.RotateTransform>Используйте класс для создания пользовательских преобразований, не предоставляемых классами,, или. <xref:System.Windows.Media.MatrixTransform>  
  
## <a name="example"></a>Пример  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [Общие сведения о классах Transform](transforms-overview.md)
- [Разделы практического руководства](transformations-how-to-topics.md)
- [Обзор фигур и базовых средств рисования в приложении WPF](shapes-and-basic-drawing-in-wpf-overview.md)
