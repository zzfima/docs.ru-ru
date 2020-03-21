---
title: Практическое руководство. Отклонение элемента
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 10b00044c1c518641281e2e72cdb5a68474b5170
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112028"
---
# <a name="how-to-skew-an-element"></a>Практическое руководство. Отклонение элемента
В этом примере <xref:System.Windows.Media.SkewTransform> показано, как использовать элемент для искажать элемент. Отклонение (или срез) — это преобразование, которое неравномерно растягивает пространство координат. Одним из типичных видов использования <xref:System.Windows.Media.SkewTransform> является моделирование 3D глубины в 2D-объектах.  
  
 Используйте <xref:System.Windows.Media.SkewTransform.CenterX%2A> <xref:System.Windows.Media.SkewTransform.CenterY%2A> и свойства, чтобы указать центральную точку <xref:System.Windows.Media.SkewTransform>.  
  
 Используйте <xref:System.Windows.Media.SkewTransform.AngleX%2A> <xref:System.Windows.Media.SkewTransform.AngleY%2A> и свойства, чтобы указать угол перекоса x-оси и y-оси, и исказить текущую систему координат вдоль этих осей.  
  
 Чтобы предсказать эффект преобразования перекоса, учтите, что <xref:System.Windows.Media.SkewTransform.AngleX%2A> перекосы значений x-оси относительно исходной системы координат. Таким образом, <xref:System.Windows.Media.SkewTransform.AngleX%2A> для 30, y-оси вращается 30 градусов через происхождение и искажает значения в x- на 30 градусов от этого происхождения. Аналогичным образом, <xref:System.Windows.Media.SkewTransform.AngleY%2A> из 30 перекосы y- значения формы на 30 градусов от происхождения. Обратите внимание, что это не то же самое, что перенос (перемещение) системы координат на 30 градусов по осям X и Y.  
  
 Следующий пример применяется горизонтальный перекос 45 градусов <xref:System.Windows.Shapes.Rectangle> к от центральной точки (0,0).  
  
## <a name="example"></a>Пример  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 Следующий пример применяется горизонтальный перекос 45 градусов <xref:System.Windows.Shapes.Rectangle> к от центральной точки (25,25).  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 Следующий пример применяется вертикальный перекос 45 градусов <xref:System.Windows.Shapes.Rectangle> к от центральной точки (25,25).  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 На следующем рисунке показаны отклонения, использованные в этом примере.  
  
 ![Примеры SkewTransform](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")  
Показаны три примера SkewTransform  
  
 Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [Общие сведения о классах Transform](transforms-overview.md)
- [Как-к темам](transformations-how-to-topics.md)
