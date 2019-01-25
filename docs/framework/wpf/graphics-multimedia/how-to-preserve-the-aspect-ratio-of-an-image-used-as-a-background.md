---
title: Как выполнить Сохранение пропорций изображения, используемого в качестве фона
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: f8133ac4fcd01e08f41861b7a441e9ff1325f6ad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698327"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>Как выполнить Сохранение пропорций изображения, используемого в качестве фона
В этом примере показано, как использовать <xref:System.Windows.Media.TileBrush.Stretch%2A> свойство <xref:System.Windows.Media.ImageBrush> чтобы сохранить пропорции изображения.  
  
 По умолчанию, при использовании <xref:System.Windows.Media.ImageBrush> для закраски области, содержимое этого объекта растягивается для полного заполнения области вывода. Если выходная область и изображение имеют разные пропорции, изображение искажается при таком растягивании.  
  
 Чтобы сделать <xref:System.Windows.Media.ImageBrush> сохранение пропорций изображения, задайте <xref:System.Windows.Media.TileBrush.Stretch%2A> свойства <xref:System.Windows.Media.Stretch.Uniform> или <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
## <a name="example"></a>Пример  
 В следующем примере используется два <xref:System.Windows.Media.ImageBrush> объекты для закраски двух прямоугольников. Каждый прямоугольник имеет размер 300 на 150 пикселей и каждый содержит изображение размером 300 на 300 пикселей. <xref:System.Windows.Media.TileBrush.Stretch%2A> Первой кисти задано значение <xref:System.Windows.Media.Stretch.Uniform>и <xref:System.Windows.Media.TileBrush.Stretch%2A> второй кисти задано значение <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 Ниже показан результат выполнения первой кисти, у которой <xref:System.Windows.Media.TileBrush.Stretch%2A> параметр <xref:System.Windows.Media.Stretch.Uniform>.  
  
 ![ImageBrush с растяжением Uniform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")  
  
 На следующем рисунке показаны выходные данные второй кисти, у которой <xref:System.Windows.Media.TileBrush.Stretch%2A> параметр <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
 ![ImageBrush c растяжением UniformToFill](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")  
  
 Обратите внимание, что <xref:System.Windows.Media.TileBrush.Stretch%2A> свойство ведет себя идентично для других <xref:System.Windows.Media.TileBrush> объектов, то есть для <xref:System.Windows.Media.DrawingBrush> и <xref:System.Windows.Media.VisualBrush>. Дополнительные сведения о <xref:System.Windows.Media.ImageBrush> , а другой <xref:System.Windows.Media.TileBrush> объектов, см. в разделе [Рисование с помощью изображений, рисунков и визуальных элементов](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
 Обратите внимание, что, несмотря на то что <xref:System.Windows.Media.TileBrush.Stretch%2A> свойство, по-видимому, укажите как <xref:System.Windows.Media.TileBrush> содержимое увеличивается до размеров области вывода, оно фактически указывает как <xref:System.Windows.Media.TileBrush> растягивается для заполнения базового фрагмента содержимого. Дополнительные сведения см. в разделе <xref:System.Windows.Media.TileBrush>.  
  
 Данный пример кода является частью большего примера, предоставляемый для <xref:System.Windows.Media.ImageBrush> класса. Полный пример см. в разделе [пример использования кистей](https://go.microsoft.com/fwlink/?LinkID=160005).  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Media.TileBrush>
- [Заполнение с использованием изображений, рисунков и визуальных элементов](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
