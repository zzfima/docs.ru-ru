---
title: Практическое руководство. Наклон элемента
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: cf770a284238826852e788e27f3b3f329ed0269f
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67664087"
---
# <a name="how-to-skew-an-element"></a>Практическое руководство. Наклон элемента
В этом примере показано, как использовать <xref:System.Windows.Media.SkewTransform> для отклонения элемента. Отклонение (или срез) — это преобразование, которое неравномерно растягивает пространство координат. Одним из примеров использования <xref:System.Windows.Media.SkewTransform> является имитация трехмерной глубины в объектах 2-D.  
  
 Используйте <xref:System.Windows.Media.SkewTransform.CenterX%2A> и <xref:System.Windows.Media.SkewTransform.CenterY%2A> точка свойства для указания центра <xref:System.Windows.Media.SkewTransform>.  
  
 Используйте <xref:System.Windows.Media.SkewTransform.AngleX%2A> и <xref:System.Windows.Media.SkewTransform.AngleY%2A> свойства для задания угла наклона осей x и y и отклонения текущей системы координат по этим осям.  
  
 Чтобы спрогнозировать результат наклона, обратите внимание на <xref:System.Windows.Media.SkewTransform.AngleX%2A> Наклоняет значений по оси x относительно исходной системы координат. Таким образом, для <xref:System.Windows.Media.SkewTransform.AngleX%2A> 30, ось y поворачивается на 30 градусов через начало координат и Наклоняет значений в x-на 30 градусов от начала координат. Аналогичным образом <xref:System.Windows.Media.SkewTransform.AngleY%2A> 30 наклон значений y фигуры на 30 градусов от начала координат. Обратите внимание, что это не то же самое, что перенос (перемещение) системы координат на 30 градусов по осям X и Y.  
  
 В следующем примере применяется горизонтальное отклонение на 45 градусов <xref:System.Windows.Shapes.Rectangle> относительно центральной точки (0,0).  
  
## <a name="example"></a>Пример  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 В следующем примере применяется горизонтальное отклонение на 45 градусов <xref:System.Windows.Shapes.Rectangle> относительно центральной точки (25, 25).  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 В следующем примере применяется вертикальное отклонение на 45 градусов <xref:System.Windows.Shapes.Rectangle> относительно центральной точки (25, 25).  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 На следующем рисунке показаны отклонения, использованные в этом примере.  
  
 ![Примеры SkewTransform](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")  
Показаны три примера SkewTransform  
  
 Полный пример см. в разделе [Примеры двумерных преобразований](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [Общие сведения о классах Transform](transforms-overview.md)
- [Разделы практического руководства](transformations-how-to-topics.md)
