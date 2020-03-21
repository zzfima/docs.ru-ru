---
title: Практическое руководство. Сохранение пропорций изображения, используемого в качестве фона
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: b467fcd353994faef19b5a997e03d6582789eac1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186034"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>Практическое руководство. Сохранение пропорций изображения, используемого в качестве фона
В этом примере <xref:System.Windows.Media.TileBrush.Stretch%2A> показано, <xref:System.Windows.Media.ImageBrush> как использовать свойство изображения для сохранения соотношения сторон изображения.  
  
 По умолчанию, когда <xref:System.Windows.Media.ImageBrush> вы используете для нарисования области, ее содержание растягивается, чтобы полностью заполнить область вывода. Если выходная область и изображение имеют разные пропорции, изображение искажается при таком растягивании.  
  
 Чтобы сохранить <xref:System.Windows.Media.ImageBrush> соотношение сторон его изображения, <xref:System.Windows.Media.TileBrush.Stretch%2A> установите <xref:System.Windows.Media.Stretch.Uniform> <xref:System.Windows.Media.Stretch.UniformToFill>свойство или .  
  
## <a name="example"></a>Пример  
 В следующем примере используются два <xref:System.Windows.Media.ImageBrush> объекта для нарисования двух прямоугольников. Каждый прямоугольник имеет размер 300 на 150 пикселей и каждый содержит изображение размером 300 на 300 пикселей. Свойство <xref:System.Windows.Media.TileBrush.Stretch%2A> первой кисти <xref:System.Windows.Media.Stretch.Uniform>устанавливается, <xref:System.Windows.Media.TileBrush.Stretch%2A> а свойство второй <xref:System.Windows.Media.Stretch.UniformToFill>кисти устанавливается.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 Следующая иллюстрация показывает выход первой кисти, <xref:System.Windows.Media.Stretch.Uniform>которая имеет настройки <xref:System.Windows.Media.TileBrush.Stretch%2A> .  
  
 ![ImageBrush с растяжением Uniform](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")  
  
 Следующая иллюстрация показывает выход второй кисти, <xref:System.Windows.Media.Stretch.UniformToFill>которая имеет настройки <xref:System.Windows.Media.TileBrush.Stretch%2A> .  
  
 ![ImageBrush с растяжением UniformToFill](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")  
  
 Обратите внимание, что <xref:System.Windows.Media.TileBrush.Stretch%2A> свойство ведет <xref:System.Windows.Media.TileBrush> себя одинаково для <xref:System.Windows.Media.DrawingBrush> других <xref:System.Windows.Media.VisualBrush>объектов, то есть для и . Для получения <xref:System.Windows.Media.ImageBrush> дополнительной информации о и других <xref:System.Windows.Media.TileBrush> объектов, см Картина с [изображениями, рисунки, и визуальные эффекты](painting-with-images-drawings-and-visuals.md).  
  
 Обратите внимание также, <xref:System.Windows.Media.TileBrush.Stretch%2A> что, хотя <xref:System.Windows.Media.TileBrush> свойство, как представляется, указать, как содержание <xref:System.Windows.Media.TileBrush> растягивается, чтобы соответствовать его выходной области, он на самом деле определяет, как содержание растягивается, чтобы заполнить свою базовую плитку. Дополнительные сведения см. в разделе <xref:System.Windows.Media.TileBrush>.  
  
 Этот пример кода является частью более крупного примера, который предоставляется классу. <xref:System.Windows.Media.ImageBrush> Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.TileBrush>
- [Заполнение с использованием изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md)
