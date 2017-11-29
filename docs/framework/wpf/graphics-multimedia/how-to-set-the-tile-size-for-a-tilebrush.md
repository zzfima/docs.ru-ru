---
title: "Как установить размер мозаики для TileBrush"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TileBrush [WPF], size of tilepropertys
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 484419c05c3d607212ea6d565777cf49cbfdbc19
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>Как установить размер мозаики для TileBrush
В этом примере показано, как установить размер мозаики для <xref:System.Windows.Media.TileBrush>. По умолчанию <xref:System.Windows.Media.TileBrush> создает один фрагмент, который полностью заполняет область раскрашивания. Это поведение можно переопределить, задав <xref:System.Windows.Media.TileBrush.Viewport%2A> и <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> свойства.  
  
 <xref:System.Windows.Media.TileBrush.Viewport%2A> Свойство указывает размер мозаики для <xref:System.Windows.Media.TileBrush>. По умолчанию значение <xref:System.Windows.Media.TileBrush.Viewport%2A> свойства задается относительно размера закрашиваемой области. Чтобы сделать <xref:System.Windows.Media.TileBrush.Viewport%2A> указывать абсолютный размер мозаики, задайте <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> свойства <xref:System.Windows.Media.BrushMappingMode.Absolute>.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.ImageBrush>, тип <xref:System.Windows.Media.TileBrush>, для заполнения прямоугольника мозаикой. В примере для фрагмента мозаики задаются размеры 50 % на 50 % от области вывода (прямоугольника). В результате прямоугольник заполняется четырьмя проекциями изображения.  
  
 На следующей иллюстрации показан результат выполнения этого примера.
  
 ![Пример мозаики с использованием кисти изображения](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 В следующем примере создается <xref:System.Windows.Media.ImageBrush>, задает его <xref:System.Windows.Media.TileBrush.Viewport%2A> для `0,0,25,25` и его <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> для <xref:System.Windows.Media.BrushMappingMode.Absolute>и использует их для раскрашивания другого прямоугольника. В результате кисть создает мозаику размером 25 пикселей в ширину и 25 пикселей в высоту.  
  
 На следующей иллюстрации показан результат выполнения этого примера.  
  
 ![Мозаичная кисть TileBrush с областью отображения 0, 0, 0,25, 0,25](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 Следующий пример является частью большого примера. Полный пример см. в разделе [ImageBrush образец](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
 Несмотря на то, что в этом примере используется <xref:System.Windows.Media.ImageBrush> класса <xref:System.Windows.Media.TileBrush.Viewport%2A> и <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> ведут себя одинаково для других <xref:System.Windows.Media.TileBrush> объектов, то есть для <xref:System.Windows.Media.DrawingBrush> и <xref:System.Windows.Media.VisualBrush>. Дополнительные сведения о <xref:System.Windows.Media.ImageBrush> , а другой <xref:System.Windows.Media.TileBrush> объектов, в разделе [Рисование с помощью изображения, рисунки и визуальные элементы](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.TileBrush>  
 [Заполнение с использованием изображений, рисунков и визуальных элементов](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Создание различных шаблонов мозаики с помощью TileBrush](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-different-tile-patterns-with-a-tilebrush.md)
