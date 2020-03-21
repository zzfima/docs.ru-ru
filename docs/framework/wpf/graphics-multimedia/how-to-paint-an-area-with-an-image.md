---
title: Инструкция по закрашиванию области с изображением
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 92969778c04c6ac634a2964c402d6c3439b96b49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186055"
---
# <a name="how-to-paint-an-area-with-an-image"></a>Инструкция по закрашиванию области с изображением
В этом примере <xref:System.Windows.Media.ImageBrush> показано, как использовать класс для нарисования области с изображением. Отображаетодно <xref:System.Windows.Media.ImageBrush> одно изображение, которое определяется его <xref:System.Windows.Media.ImageBrush.ImageSource%2A> свойством.  
  
## <a name="example"></a>Пример  
 Следующий пример рисует <xref:System.Windows.Controls.Control.Background%2A> кнопку с <xref:System.Windows.Media.ImageBrush>помощью .  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 По умолчанию, <xref:System.Windows.Media.ImageBrush> растягивает свой образ, чтобы полностью заполнить область, которую вы рисуете. В предыдущем примере изображение растягивается до заполнения кнопки, возможно искажение изображения. Вы можете контролировать это <xref:System.Windows.Media.TileBrush.Stretch%2A> поведение, <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.Stretch.Uniform> установив <xref:System.Windows.Media.Stretch.UniformToFill>свойство к или , что приводит к кисти, чтобы сохранить соотношение сторон изображения.  
  
 Если вы <xref:System.Windows.Media.TileBrush.Viewport%2A> установите <xref:System.Windows.Media.TileBrush.TileMode%2A> и <xref:System.Windows.Media.ImageBrush>свойства, вы можете создать повторяющийся шаблон. Следующий пример закрашивает кнопку с помощью шаблона, который создается из изображения.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 Для получения дополнительной <xref:System.Windows.Media.ImageBrush> информации о классе, см [Картина с изображениями, рисунки и визуальные эффекты](painting-with-images-drawings-and-visuals.md).  
  
 Этот пример кода является частью более крупного примера, который предоставляется классу. <xref:System.Windows.Media.ImageBrush> Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)  
  
## <a name="see-also"></a>См. также раздел

- [Заполнение с использованием изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md)
