---
title: "Как раскрасить область с видео"
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
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a72843547d934aeaeec062eec1241e402baf56bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-paint-an-area-with-a-video"></a>Как раскрасить область с видео
В этом примере показано, как Закраска области с носителя. Один способ заполнения области с мультимедиа является использование <xref:System.Windows.Controls.MediaElement> вместе с <xref:System.Windows.Media.VisualBrush>. Используйте <xref:System.Windows.Controls.MediaElement> для загрузки и воспроизведения файлов мультимедиа и затем использовать его для задания <xref:System.Windows.Media.VisualBrush.Visual%2A> свойство <xref:System.Windows.Media.VisualBrush>. Затем можно использовать <xref:System.Windows.Media.VisualBrush> для закрашивания области с загруженным мультимедиа.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Controls.MediaElement> и <xref:System.Windows.Media.VisualBrush> для закрашивания <xref:System.Windows.Controls.TextBlock.Foreground%2A> из <xref:System.Windows.Controls.TextBlock> управления видео. В этом примере устанавливается <xref:System.Windows.Controls.MediaElement.IsMuted%2A> свойство <xref:System.Windows.Controls.MediaElement> для `true` , чтобы отключить звук.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a>Пример  
 Поскольку <xref:System.Windows.Media.VisualBrush> наследует от <xref:System.Windows.Media.TileBrush> класс предоставляет несколько режимов заполнения. Установив <xref:System.Windows.Media.TileBrush.TileMode%2A> свойство <xref:System.Windows.Media.VisualBrush> для <xref:System.Windows.Media.TileMode.Tile> и установив его <xref:System.Windows.Media.TileBrush.Viewport%2A> свойство в значение меньше, чем область закрашивания, можно создать шаблон заполнения.  
  
 Следующий пример идентичен предыдущему примеру, за исключением того, что <xref:System.Windows.Media.VisualBrush> создает шаблон из видео.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 Сведения о добавлении файла содержимого, такие как файл мультимедиа в приложение, в разделе [ресурса приложения WPF, содержимое и файлы данных](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md). При добавлении файла мультимедиа, необходимо добавить его как файл содержимого, а не как файл ресурсов.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.VisualBrush>  
 [Заполнение с использованием изображений, рисунков и визуальных элементов](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Общие сведения об объекте TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)  
 [Общие сведения о мультимедиа](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)
