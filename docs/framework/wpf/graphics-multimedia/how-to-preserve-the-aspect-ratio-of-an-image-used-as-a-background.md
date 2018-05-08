---
title: Практическое руководство. Сохранение пропорций изображения, используемого в качестве фона
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: 906033b43ba657acc873f12a00000189db6796ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>Практическое руководство. Сохранение пропорций изображения, используемого в качестве фона
В этом примере показано, как использовать <xref:System.Windows.Media.TileBrush.Stretch%2A> свойство <xref:System.Windows.Media.ImageBrush> чтобы сохранить соотношение сторон изображения.  
  
 По умолчанию при использовании <xref:System.Windows.Media.ImageBrush> для закраски области, его содержимое увеличивается до полного заполнения области вывода. Если выходная область и изображение имеют разные пропорции, изображение искажается при таком растягивании.  
  
 Чтобы сделать <xref:System.Windows.Media.ImageBrush> сохранить соотношение сторон изображения, задайте <xref:System.Windows.Media.TileBrush.Stretch%2A> свойства <xref:System.Windows.Media.Stretch.Uniform> или <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
## <a name="example"></a>Пример  
 В следующем примере используются два <xref:System.Windows.Media.ImageBrush> объектов для рисования двух прямоугольников. Каждый прямоугольник имеет размер 300 на 150 пикселей и каждый содержит изображение размером 300 на 300 пикселей. <xref:System.Windows.Media.TileBrush.Stretch%2A> Первой кисти задано значение <xref:System.Windows.Media.Stretch.Uniform>и <xref:System.Windows.Media.TileBrush.Stretch%2A> второй кисти задано значение <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 Ниже показан результат выполнения первой кисти, который имеет <xref:System.Windows.Media.TileBrush.Stretch%2A> параметра <xref:System.Windows.Media.Stretch.Uniform>.  
  
 ![ImageBrush с растяжением Uniform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")  
  
 На следующем рисунке показан результат выполнения второй кисти, который имеет <xref:System.Windows.Media.TileBrush.Stretch%2A> параметра <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
 ![ImageBrush c растяжением UniformToFill](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")  
  
 Обратите внимание, что <xref:System.Windows.Media.TileBrush.Stretch%2A> свойство ведет себя одинаково для других <xref:System.Windows.Media.TileBrush> объектов, то есть для <xref:System.Windows.Media.DrawingBrush> и <xref:System.Windows.Media.VisualBrush>. Дополнительные сведения о <xref:System.Windows.Media.ImageBrush> , а другой <xref:System.Windows.Media.TileBrush> объектов, в разделе [Рисование с помощью изображения, рисунки и визуальные элементы](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
 Обратите внимание, что, несмотря на то что <xref:System.Windows.Media.TileBrush.Stretch%2A> отображается свойство для указания как <xref:System.Windows.Media.TileBrush> содержимое увеличивается до размеров выходной области, оно фактически указывает как <xref:System.Windows.Media.TileBrush> содержимого растягивается до его базового фрагмента. Дополнительные сведения см. в разделе <xref:System.Windows.Media.TileBrush>.  
  
 Данный пример кода является частью большего примера, приведенного для <xref:System.Windows.Media.ImageBrush> класса. Полный пример см. в разделе [ImageBrush образец](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.TileBrush>  
 [Заливка с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
