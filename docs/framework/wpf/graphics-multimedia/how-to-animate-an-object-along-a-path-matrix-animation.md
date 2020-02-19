---
title: Практическое руководство. Анимация объекта вдоль пути (матричная анимация)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: 7dfc233fe60e1cea293edc44a2bba79dc6962f7c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452913"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a>Практическое руководство. Анимация объекта вдоль пути (матричная анимация)
В этом примере показано, как использовать класс <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> для анимации объекта вдоль пути, определенного <xref:System.Windows.Media.PathGeometry>.  
  
## <a name="example"></a>Пример  
 Следующий пример анимирует объект вдоль пути следующим образом:  
  
- Применяет <xref:System.Windows.Media.MatrixTransform> к объекту, чтобы переместить его.  
  
- Определяет путь с помощью <xref:System.Windows.Media.PathGeometry>.  
  
- Создает <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> и использует его для анимации свойства <xref:System.Windows.Media.Matrix> <xref:System.Windows.Media.MatrixTransform>. <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> принимает <xref:System.Windows.Media.PathGeometry> и использует его для создания значений <xref:System.Windows.Media.Matrix>.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 Полный пример см. в разделе [Пример анимации по путям](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations). Дополнительные сведения о геометрических путях см. в разделе [Общие сведения о геометрии](geometry-overview.md).  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об эффектах анимации](animation-overview.md)
- [Пример анимации вдоль пути](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [Практические руководства, посвященные анимации вдоль пути](path-animation-how-to-topics.md)
