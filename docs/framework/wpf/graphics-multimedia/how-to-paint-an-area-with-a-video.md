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
ms.openlocfilehash: 362231bbd1f4e95c260370a99233b7e8c2617ca1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-paint-an-area-with-a-video"></a><span data-ttu-id="29060-102">Как раскрасить область с видео</span><span class="sxs-lookup"><span data-stu-id="29060-102">How to: Paint an Area with a Video</span></span>
<span data-ttu-id="29060-103">В этом примере показано, как Закраска области с носителя.</span><span class="sxs-lookup"><span data-stu-id="29060-103">This example shows how to paint an area with media.</span></span> <span data-ttu-id="29060-104">Один способ заполнения области с мультимедиа является использование <xref:System.Windows.Controls.MediaElement> вместе с <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="29060-104">One way to paint an area with media is to use a <xref:System.Windows.Controls.MediaElement> together with a <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="29060-105">Используйте <xref:System.Windows.Controls.MediaElement> для загрузки и воспроизведения файлов мультимедиа и затем использовать его для задания <xref:System.Windows.Media.VisualBrush.Visual%2A> свойство <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="29060-105">Use the <xref:System.Windows.Controls.MediaElement> to load and play the media, and then use it to set the <xref:System.Windows.Media.VisualBrush.Visual%2A> property of the <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="29060-106">Затем можно использовать <xref:System.Windows.Media.VisualBrush> для закрашивания области с загруженным мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="29060-106">You can then use the <xref:System.Windows.Media.VisualBrush> to paint an area with the loaded media.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29060-107">Пример</span><span class="sxs-lookup"><span data-stu-id="29060-107">Example</span></span>  
 <span data-ttu-id="29060-108">В следующем примере используется <xref:System.Windows.Controls.MediaElement> и <xref:System.Windows.Media.VisualBrush> для закрашивания <xref:System.Windows.Controls.TextBlock.Foreground%2A> из <xref:System.Windows.Controls.TextBlock> управления видео.</span><span class="sxs-lookup"><span data-stu-id="29060-108">The following example uses a <xref:System.Windows.Controls.MediaElement> and a <xref:System.Windows.Media.VisualBrush> to paint the <xref:System.Windows.Controls.TextBlock.Foreground%2A> of a <xref:System.Windows.Controls.TextBlock> control with video.</span></span> <span data-ttu-id="29060-109">В этом примере устанавливается <xref:System.Windows.Controls.MediaElement.IsMuted%2A> свойство <xref:System.Windows.Controls.MediaElement> для `true` , чтобы отключить звук.</span><span class="sxs-lookup"><span data-stu-id="29060-109">This example sets the <xref:System.Windows.Controls.MediaElement.IsMuted%2A> property of the <xref:System.Windows.Controls.MediaElement> to `true` so that it produces no sound.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a><span data-ttu-id="29060-110">Пример</span><span class="sxs-lookup"><span data-stu-id="29060-110">Example</span></span>  
 <span data-ttu-id="29060-111">Поскольку <xref:System.Windows.Media.VisualBrush> наследует от <xref:System.Windows.Media.TileBrush> класс предоставляет несколько режимов заполнения.</span><span class="sxs-lookup"><span data-stu-id="29060-111">Because <xref:System.Windows.Media.VisualBrush> inherits from the <xref:System.Windows.Media.TileBrush> class, it provides several tiling modes.</span></span> <span data-ttu-id="29060-112">Установив <xref:System.Windows.Media.TileBrush.TileMode%2A> свойство <xref:System.Windows.Media.VisualBrush> для <xref:System.Windows.Media.TileMode.Tile> и установив его <xref:System.Windows.Media.TileBrush.Viewport%2A> свойство в значение меньше, чем область закрашивания, можно создать шаблон заполнения.</span><span class="sxs-lookup"><span data-stu-id="29060-112">By setting the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.VisualBrush> to <xref:System.Windows.Media.TileMode.Tile> and by setting its <xref:System.Windows.Media.TileBrush.Viewport%2A> property to a value smaller than the area that you are painting, you can create a tiled pattern.</span></span>  
  
 <span data-ttu-id="29060-113">Следующий пример идентичен предыдущему примеру, за исключением того, что <xref:System.Windows.Media.VisualBrush> создает шаблон из видео.</span><span class="sxs-lookup"><span data-stu-id="29060-113">The following example is identical to the previous example, except that the <xref:System.Windows.Media.VisualBrush> generates a pattern from the video.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 <span data-ttu-id="29060-114">Сведения о добавлении файла содержимого, такие как файл мультимедиа в приложение, в разделе [ресурса приложения WPF, содержимое и файлы данных](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).</span><span class="sxs-lookup"><span data-stu-id="29060-114">For information about how to add a content file, such as a media file, to your application, see [WPF Application Resource, Content, and Data Files](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).</span></span> <span data-ttu-id="29060-115">При добавлении файла мультимедиа, необходимо добавить его как файл содержимого, а не как файл ресурсов.</span><span class="sxs-lookup"><span data-stu-id="29060-115">When you add a media file, you must add it as a content file, not as a resource file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29060-116">См. также</span><span class="sxs-lookup"><span data-stu-id="29060-116">See Also</span></span>  
 <xref:System.Windows.Media.VisualBrush>  
 [<span data-ttu-id="29060-117">Заполнение с использованием изображений, рисунков и визуальных элементов</span><span class="sxs-lookup"><span data-stu-id="29060-117">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [<span data-ttu-id="29060-118">Общие сведения об объекте TileBrush</span><span class="sxs-lookup"><span data-stu-id="29060-118">TileBrush Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)  
 [<span data-ttu-id="29060-119">Общие сведения о мультимедиа</span><span class="sxs-lookup"><span data-stu-id="29060-119">Multimedia Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)
