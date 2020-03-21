---
title: Практическое руководство. Поворот объекта с использованием геометрического пути
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: a351fdc936f634b7c57ba5a49e51501f7572a3c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186878"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a>Практическое руководство. Поворот объекта с использованием геометрического пути
Этот пример показывает, как повернуть (поворот) объекта вдоль геометрического <xref:System.Windows.Media.PathGeometry> пути, который определяется объектом.  
  
## <a name="example"></a>Пример  
 В следующем примере используются три <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> объекта для перемещения прямоугольника по геометрическому пути.  
  
- Первый <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> <xref:System.Windows.Media.RotateTransform> оживляет, который наносится на прямоугольник. Анимация формирует значения угла. Это заставляет прямоугольник поворачиваться (вращаться) вдоль контуров пути.  
  
- Два других объекта <xref:System.Windows.Media.TranslateTransform.X%2A> оживляют <xref:System.Windows.Media.TranslateTransform.Y%2A> и <xref:System.Windows.Media.TranslateTransform> значения, которые применяются к прямоугольнику. Это заставляет прямоугольник двигаться горизонтально и вертикально вдоль пути.  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 Другой способ повернуть объект с помощью геометрического <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> пути — <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> использовать `true`объект и установить его свойство. Для получения дополнительной информации и примера [см.](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md)  
  
 Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об эффектах анимации](animation-overview.md)
- [Пример анимации по контуру](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [Практические руководства, посвященные анимации по контуру](path-animation-how-to-topics.md)
