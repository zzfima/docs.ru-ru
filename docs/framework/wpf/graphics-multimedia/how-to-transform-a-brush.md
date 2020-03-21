---
title: Практическое руководство. Преобразование кисти
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: b4484e2fc1ae3e969b02b1d8f3ae4ab2a035558e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187339"
---
# <a name="how-to-transform-a-brush"></a>Практическое руководство. Преобразование кисти
В этом примере <xref:System.Windows.Media.Brush> показано, как преобразовывать объекты, используя два их свойства преобразования: <xref:System.Windows.Media.Brush.RelativeTransform%2A> и <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 В следующих <xref:System.Windows.Media.RotateTransform> примерах используется для <xref:System.Windows.Media.ImageBrush> вращения содержимого на 45 градусов.  
  
 Следующая иллюстрация <xref:System.Windows.Media.ImageBrush> показывает <xref:System.Windows.Media.RotateTransform>без <xref:System.Windows.Media.RotateTransform> , с <xref:System.Windows.Media.Brush.RelativeTransform%2A> применяется к <xref:System.Windows.Media.RotateTransform> собственности, и с применяется к собственности. <xref:System.Windows.Media.Brush.Transform%2A>  
  
 ![Параметры кисти RelativeTransform и Transform](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
## <a name="example"></a>Пример  
 Первый пример применяется <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.Brush.RelativeTransform%2A> к свойству <xref:System.Windows.Media.ImageBrush>. Свойства <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> объекта <xref:System.Windows.Media.RotateTransform> установлены на 0,5, что является относительной координатой центральной точки этого содержимого. В результате содержимое <xref:System.Windows.Media.ImageBrush> вращается вокруг его центра.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 Второй пример также <xref:System.Windows.Media.RotateTransform> применяется <xref:System.Windows.Media.ImageBrush>к ; однако в этом <xref:System.Windows.Media.Brush.Transform%2A> примере <xref:System.Windows.Media.Brush.RelativeTransform%2A> используется свойство вместо свойства.  
  
 Чтобы повернуть кисть вокруг ее центра, <xref:System.Windows.Media.RotateTransform.CenterY%2A> пример <xref:System.Windows.Media.RotateTransform> устанавливает <xref:System.Windows.Media.RotateTransform.CenterX%2A> и свойства объекта к абсолютным координатам. Так как эта кисть рисует прямоугольник размером 175 на 90 пикселей, центральная точка прямоугольника имеет координаты (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Описание того, как <xref:System.Windows.Media.Brush.RelativeTransform%2A> <xref:System.Windows.Media.Brush.Transform%2A> работают и как работают свойства, можно ознакомьтесь с [обзором трансформации кисти.](brush-transformation-overview.md)  
  
 Полный пример см. в разделе [Примеры кистей](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes). Дополнительные сведения о кистях см. в разделе [Общие сведения о закраске сплошным цветом и градиентом](painting-with-solid-colors-and-gradients-overview.md).  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения о преобразованиях кистей](brush-transformation-overview.md)
- [Общие сведения о закраске сплошным цветом и градиентом](painting-with-solid-colors-and-gradients-overview.md)
- [Общие сведения о классах Transform](transforms-overview.md)
