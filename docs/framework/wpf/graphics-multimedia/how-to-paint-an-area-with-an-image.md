---
title: "Инструкция по закрашиванию области с изображением"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3edbe30347580bb4f9677d7fb98d3b4fd8b92cff
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-paint-an-area-with-an-image"></a>Инструкция по закрашиванию области с изображением
В этом примере показано, как использовать <xref:System.Windows.Media.ImageBrush> класса Закраска области с изображением. <xref:System.Windows.Media.ImageBrush> Отображает одно изображение, которое определяется его <xref:System.Windows.Media.ImageBrush.ImageSource%2A> свойство.  
  
## <a name="example"></a>Пример  
 В следующем примере закрашивается <xref:System.Windows.Controls.Control.Background%2A> кнопки с помощью <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 По умолчанию <xref:System.Windows.Media.ImageBrush> увеличивает изображение для полного заполнения закрашиваемой области. В предыдущем примере изображение растягивается до заполнения кнопки, возможно искажение изображения. Можно контролировать это поведение, задав <xref:System.Windows.Media.TileBrush.Stretch%2A> свойство <xref:System.Windows.Media.TileBrush> для <xref:System.Windows.Media.Stretch.Uniform> или <xref:System.Windows.Media.Stretch.UniformToFill>, вследствие чего кисти сохранить соотношение сторон изображения.  
  
 Если задать <xref:System.Windows.Media.TileBrush.Viewport%2A> и <xref:System.Windows.Media.TileBrush.TileMode%2A> свойства <xref:System.Windows.Media.ImageBrush>, можно создать повторяющийся рисунок. Следующий пример закрашивает кнопку с помощью шаблона, который создается из изображения.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 Дополнительные сведения о <xref:System.Windows.Media.ImageBrush> см. в описании [Рисование с помощью изображения, рисунки и визуальные элементы](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
 Данный пример кода является частью большего примера, приведенного для <xref:System.Windows.Media.ImageBrush> класса. Полный пример см. в разделе [ImageBrush образец](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
## <a name="see-also"></a>См. также  
 [Заливка с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
