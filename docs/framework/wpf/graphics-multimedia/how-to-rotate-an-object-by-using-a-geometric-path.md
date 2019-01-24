---
title: Как выполнить Поворот объекта с использованием геометрического пути
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: cd8aaee7563d684e70dc29f1c293b091c1e6cff9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661494"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a>Как выполнить Поворот объекта с использованием геометрического пути
В этом примере демонстрируется поворот (вращение) объекта вдоль геометрического пути, который определяется <xref:System.Windows.Media.PathGeometry> объекта.  
  
## <a name="example"></a>Пример  
 В следующем примере используется три <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> объекты для перемещения прямоугольника вдоль геометрического пути.  
  
-   Первый <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> анимирует <xref:System.Windows.Media.RotateTransform> , примененного к прямоугольнику. Анимация формирует значения угла. Это заставляет прямоугольник поворачиваться (вращаться) вдоль контуров пути.  
  
-   Другие два объекта анимируют <xref:System.Windows.Media.TranslateTransform.X%2A> и <xref:System.Windows.Media.TranslateTransform.Y%2A> значения <xref:System.Windows.Media.TranslateTransform> , примененного к прямоугольнику. Это заставляет прямоугольник двигаться горизонтально и вертикально вдоль пути.  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 Поворот объекта с использованием геометрического пути другим способом является использование <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> и задайте его <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> свойства `true`. Дополнительные сведения и пример см. в разделе [поворот объекта с использованием геометрического пути (матричная анимация)](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).  
  
 Полный пример см. в разделе [Пример анимации вдоль пути](https://go.microsoft.com/fwlink/?LinkID=160028).  
  
## <a name="see-also"></a>См. также
- [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Пример анимации вдоль пути](https://go.microsoft.com/fwlink/?LinkID=160028)
- [Практические руководства, посвященные анимации по контуру](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
