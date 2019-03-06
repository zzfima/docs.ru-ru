---
title: Практическое руководство. Закрашивание области с помощью Image
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: c1db803aacad85ce90fec519b5eabdd8df7bb584
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369127"
---
# <a name="how-to-paint-an-area-with-an-image"></a>Практическое руководство. Закрашивание области с помощью Image
В этом примере показано, как использовать <xref:System.Windows.Media.ImageBrush> класс для закраски области изображением. <xref:System.Windows.Media.ImageBrush> Отображает одно изображение, которое определяется ее <xref:System.Windows.Media.ImageBrush.ImageSource%2A> свойство.  
  
## <a name="example"></a>Пример  
 В следующем примере закрашивается <xref:System.Windows.Controls.Control.Background%2A> кнопки с помощью <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 По умолчанию <xref:System.Windows.Media.ImageBrush> растягивает изображения до полного заполнения закрашиваемой области. В предыдущем примере изображение растягивается до заполнения кнопки, возможно искажение изображения. Этим поведением можно управлять, задав <xref:System.Windows.Media.TileBrush.Stretch%2A> свойство <xref:System.Windows.Media.TileBrush> для <xref:System.Windows.Media.Stretch.Uniform> или <xref:System.Windows.Media.Stretch.UniformToFill>, чего кисть сохранить пропорции изображения.  
  
 Если задать <xref:System.Windows.Media.TileBrush.Viewport%2A> и <xref:System.Windows.Media.TileBrush.TileMode%2A> свойства <xref:System.Windows.Media.ImageBrush>, можно создать повторяющийся шаблон. Следующий пример закрашивает кнопку с помощью шаблона, который создается из изображения.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 Дополнительные сведения о <xref:System.Windows.Media.ImageBrush> , представлена в разделе [Рисование с помощью изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md).  
  
 Данный пример кода является частью большего примера, предоставляемый для <xref:System.Windows.Media.ImageBrush> класса. Полный пример см. в разделе [пример использования кистей](https://go.microsoft.com/fwlink/?LinkID=160005).  
  
## <a name="see-also"></a>См. также
- [Заполнение с использованием изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md)
