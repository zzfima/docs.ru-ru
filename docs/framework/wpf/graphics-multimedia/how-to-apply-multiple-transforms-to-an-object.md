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
# <a name="how-to-apply-multiple-transforms-to-an-object"></a>Практическое руководство. Применение нескольких преобразований к объекту
В этом примере <xref:System.Windows.Media.TransformGroup> показано, как <xref:System.Windows.Media.Transform> использовать для группы два или более объектов в один состав. <xref:System.Windows.Media.Transform>  
  
## <a name="example"></a>Пример  
 Следующий пример <xref:System.Windows.Media.TransformGroup> использует a <xref:System.Windows.Media.ScaleTransform> для <xref:System.Windows.Media.RotateTransform> применения <xref:System.Windows.Controls.Button>a и a к .  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Media.TransformGroup>
- [Общие сведения о классах Transform](transforms-overview.md)
- [2D Преобразует образец](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
