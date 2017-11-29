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
# <a name="how-to-paint-an-area-with-an-image"></a><span data-ttu-id="e55c4-102">Инструкция по закрашиванию области с изображением</span><span class="sxs-lookup"><span data-stu-id="e55c4-102">How to: Paint an Area with an Image</span></span>
<span data-ttu-id="e55c4-103">В этом примере показано, как использовать <xref:System.Windows.Media.ImageBrush> класса Закраска области с изображением.</span><span class="sxs-lookup"><span data-stu-id="e55c4-103">This example shows how to use the <xref:System.Windows.Media.ImageBrush> class to paint an area with an image.</span></span> <span data-ttu-id="e55c4-104"><xref:System.Windows.Media.ImageBrush> Отображает одно изображение, которое определяется его <xref:System.Windows.Media.ImageBrush.ImageSource%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="e55c4-104">An <xref:System.Windows.Media.ImageBrush> displays a single image, which is specified by its <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e55c4-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e55c4-105">Example</span></span>  
 <span data-ttu-id="e55c4-106">В следующем примере закрашивается <xref:System.Windows.Controls.Control.Background%2A> кнопки с помощью <xref:System.Windows.Media.ImageBrush>.</span><span class="sxs-lookup"><span data-stu-id="e55c4-106">The following example paints the <xref:System.Windows.Controls.Control.Background%2A> of a button by using an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 <span data-ttu-id="e55c4-107">По умолчанию <xref:System.Windows.Media.ImageBrush> увеличивает изображение для полного заполнения закрашиваемой области.</span><span class="sxs-lookup"><span data-stu-id="e55c4-107">By default, an <xref:System.Windows.Media.ImageBrush> stretches its image to completely fill the area that you are painting.</span></span> <span data-ttu-id="e55c4-108">В предыдущем примере изображение растягивается до заполнения кнопки, возможно искажение изображения.</span><span class="sxs-lookup"><span data-stu-id="e55c4-108">In the preceding example, the image is stretched to fill the button, possibly distorting the image.</span></span> <span data-ttu-id="e55c4-109">Можно контролировать это поведение, задав <xref:System.Windows.Media.TileBrush.Stretch%2A> свойство <xref:System.Windows.Media.TileBrush> для <xref:System.Windows.Media.Stretch.Uniform> или <xref:System.Windows.Media.Stretch.UniformToFill>, вследствие чего кисти сохранить соотношение сторон изображения.</span><span class="sxs-lookup"><span data-stu-id="e55c4-109">You can control this behavior by setting the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of <xref:System.Windows.Media.TileBrush> to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>, which causes the brush to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="e55c4-110">Если задать <xref:System.Windows.Media.TileBrush.Viewport%2A> и <xref:System.Windows.Media.TileBrush.TileMode%2A> свойства <xref:System.Windows.Media.ImageBrush>, можно создать повторяющийся рисунок.</span><span class="sxs-lookup"><span data-stu-id="e55c4-110">If you set the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties of an <xref:System.Windows.Media.ImageBrush>, you can create a repeating pattern.</span></span> <span data-ttu-id="e55c4-111">Следующий пример закрашивает кнопку с помощью шаблона, который создается из изображения.</span><span class="sxs-lookup"><span data-stu-id="e55c4-111">The following example paints a button by using a pattern that is created from an image.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 <span data-ttu-id="e55c4-112">Дополнительные сведения о <xref:System.Windows.Media.ImageBrush> см. в описании [Рисование с помощью изображения, рисунки и визуальные элементы](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="e55c4-112">For more information about the <xref:System.Windows.Media.ImageBrush> class, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="e55c4-113">Данный пример кода является частью большего примера, приведенного для <xref:System.Windows.Media.ImageBrush> класса.</span><span class="sxs-lookup"><span data-stu-id="e55c4-113">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="e55c4-114">Полный пример см. в разделе [ImageBrush образец](http://go.microsoft.com/fwlink/?LinkID=160005).</span><span class="sxs-lookup"><span data-stu-id="e55c4-114">For the complete sample, see [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e55c4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e55c4-115">See Also</span></span>  
 [<span data-ttu-id="e55c4-116">Заливка с помощью объектов Image, Drawing и Visual</span><span class="sxs-lookup"><span data-stu-id="e55c4-116">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
