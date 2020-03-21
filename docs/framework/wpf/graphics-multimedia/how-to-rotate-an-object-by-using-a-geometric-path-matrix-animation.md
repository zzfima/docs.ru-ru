---
title: Практическое руководство. Поворот объекта с использованием геометрического пути (матрица анимации)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
ms.openlocfilehash: 63dc873a2b840ea3f870a8c60c5691ab271c1c9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187414"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a>Практическое руководство. Поворот объекта с использованием геометрического пути (матрица анимации)
В этом примере <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> показано, <xref:System.Windows.Media.MatrixTransform> как использовать и использовать (поворот) объекта вдоль <xref:System.Windows.Media.PathGeometry> геометрического пути, определяемого объектом.  
  
## <a name="example"></a>Пример  
 В следующем примере <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> используется объект <xref:System.Windows.Media.MatrixTransform.Matrix%2A> для анимировать свойство <xref:System.Windows.Media.MatrixTransform>. Применяется <xref:System.Windows.Media.MatrixTransform> к кнопке и заставляет ее двигаться по изогнутому пути. Поскольку <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> свойство `true`настроено на то, что прямоугольник вращается по касательной пути.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)  
  
 Кодовая версия предыдущего <xref:System.Windows.Media.Animation.Storyboard> образца использовала <xref:System.Windows.Media.EllipseGeometry>a для анимации , хотя была применена только одна анимация. Проще всего применить одну анимацию к свойству в <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> коде — использовать метод. Например, [см. Animate a Property без использования раскадровки.](how-to-animate-a-property-without-using-a-storyboard.md)  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об эффектах анимации](animation-overview.md)
- [Практические руководства, посвященные анимации по контуру](path-animation-how-to-topics.md)
- [Пример анимации по контуру](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
