---
title: "Практическое руководство. Сохранение пропорций изображения, используемого в качестве фона"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a34377403a55ba42d9d3f2946ef26ea48982f5d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a><span data-ttu-id="16500-102">Практическое руководство. Сохранение пропорций изображения, используемого в качестве фона</span><span class="sxs-lookup"><span data-stu-id="16500-102">How to: Preserve the Aspect Ratio of an Image Used as a Background</span></span>
<span data-ttu-id="16500-103">В этом примере показано, как использовать <xref:System.Windows.Media.TileBrush.Stretch%2A> свойство <xref:System.Windows.Media.ImageBrush> чтобы сохранить соотношение сторон изображения.</span><span class="sxs-lookup"><span data-stu-id="16500-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of an <xref:System.Windows.Media.ImageBrush> in order to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="16500-104">По умолчанию при использовании <xref:System.Windows.Media.ImageBrush> для закраски области, его содержимое увеличивается до полного заполнения области вывода.</span><span class="sxs-lookup"><span data-stu-id="16500-104">By default, when you use an <xref:System.Windows.Media.ImageBrush> to paint an area, its content stretches to completely fill the output area.</span></span> <span data-ttu-id="16500-105">Если выходная область и изображение имеют разные пропорции, изображение искажается при таком растягивании.</span><span class="sxs-lookup"><span data-stu-id="16500-105">When the output area and the image have different aspect ratios, the image is distorted by this stretching.</span></span>  
  
 <span data-ttu-id="16500-106">Чтобы сделать <xref:System.Windows.Media.ImageBrush> сохранить соотношение сторон изображения, задайте <xref:System.Windows.Media.TileBrush.Stretch%2A> свойства <xref:System.Windows.Media.Stretch.Uniform> или <xref:System.Windows.Media.Stretch.UniformToFill>.</span><span class="sxs-lookup"><span data-stu-id="16500-106">To make an <xref:System.Windows.Media.ImageBrush> preserve the aspect ratio of its image, set the <xref:System.Windows.Media.TileBrush.Stretch%2A> property to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16500-107">Пример</span><span class="sxs-lookup"><span data-stu-id="16500-107">Example</span></span>  
 <span data-ttu-id="16500-108">В следующем примере используются два <xref:System.Windows.Media.ImageBrush> объектов для рисования двух прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="16500-108">The following example uses two <xref:System.Windows.Media.ImageBrush> objects to paint two rectangles.</span></span> <span data-ttu-id="16500-109">Каждый прямоугольник имеет размер 300 на 150 пикселей и каждый содержит изображение размером 300 на 300 пикселей.</span><span class="sxs-lookup"><span data-stu-id="16500-109">Each rectangle is 300 by 150 pixels and each contains a 300 by 300 pixel image.</span></span> <span data-ttu-id="16500-110"><xref:System.Windows.Media.TileBrush.Stretch%2A> Первой кисти задано значение <xref:System.Windows.Media.Stretch.Uniform>и <xref:System.Windows.Media.TileBrush.Stretch%2A> второй кисти задано значение <xref:System.Windows.Media.Stretch.UniformToFill>.</span><span class="sxs-lookup"><span data-stu-id="16500-110">The <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the first brush is set to <xref:System.Windows.Media.Stretch.Uniform>, and the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the second brush is set to <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 <span data-ttu-id="16500-111">Ниже показан результат выполнения первой кисти, который имеет <xref:System.Windows.Media.TileBrush.Stretch%2A> параметра <xref:System.Windows.Media.Stretch.Uniform>.</span><span class="sxs-lookup"><span data-stu-id="16500-111">The following illustration shows the output of the first brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.Uniform>.</span></span>  
  
 <span data-ttu-id="16500-112">![ImageBrush с растяжением Uniform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span><span class="sxs-lookup"><span data-stu-id="16500-112">![ImageBrush with Uniform stretching](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span></span>  
  
 <span data-ttu-id="16500-113">На следующем рисунке показан результат выполнения второй кисти, который имеет <xref:System.Windows.Media.TileBrush.Stretch%2A> параметра <xref:System.Windows.Media.Stretch.UniformToFill>.</span><span class="sxs-lookup"><span data-stu-id="16500-113">The next illustration shows the output of the second brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 <span data-ttu-id="16500-114">![ImageBrush c растяжением UniformToFill](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span><span class="sxs-lookup"><span data-stu-id="16500-114">![ImageBrush with UniformToFill stretching](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span></span>  
  
 <span data-ttu-id="16500-115">Обратите внимание, что <xref:System.Windows.Media.TileBrush.Stretch%2A> свойство ведет себя одинаково для других <xref:System.Windows.Media.TileBrush> объектов, то есть для <xref:System.Windows.Media.DrawingBrush> и <xref:System.Windows.Media.VisualBrush>.</span><span class="sxs-lookup"><span data-stu-id="16500-115">Note that the <xref:System.Windows.Media.TileBrush.Stretch%2A> property behaves identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="16500-116">Дополнительные сведения о <xref:System.Windows.Media.ImageBrush> , а другой <xref:System.Windows.Media.TileBrush> объектов, в разделе [Рисование с помощью изображения, рисунки и визуальные элементы](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="16500-116">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="16500-117">Обратите внимание, что, несмотря на то что <xref:System.Windows.Media.TileBrush.Stretch%2A> отображается свойство для указания как <xref:System.Windows.Media.TileBrush> содержимое увеличивается до размеров выходной области, оно фактически указывает как <xref:System.Windows.Media.TileBrush> содержимого растягивается до его базового фрагмента.</span><span class="sxs-lookup"><span data-stu-id="16500-117">Note also that, although the <xref:System.Windows.Media.TileBrush.Stretch%2A> property appears to specify how the <xref:System.Windows.Media.TileBrush> content stretches to fit its output area, it actually specifies how the <xref:System.Windows.Media.TileBrush> content stretches to fill its base tile.</span></span> <span data-ttu-id="16500-118">Для получения дополнительной информации см. <xref:System.Windows.Media.TileBrush>.</span><span class="sxs-lookup"><span data-stu-id="16500-118">For more information, see <xref:System.Windows.Media.TileBrush>.</span></span>  
  
 <span data-ttu-id="16500-119">Данный пример кода является частью большего примера, приведенного для <xref:System.Windows.Media.ImageBrush> класса.</span><span class="sxs-lookup"><span data-stu-id="16500-119">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="16500-120">Полный пример см. в разделе [ImageBrush образец](http://go.microsoft.com/fwlink/?LinkID=160005).</span><span class="sxs-lookup"><span data-stu-id="16500-120">For the complete sample, see [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16500-121">См. также</span><span class="sxs-lookup"><span data-stu-id="16500-121">See Also</span></span>  
 <xref:System.Windows.Media.TileBrush>  
 [<span data-ttu-id="16500-122">Заливка с помощью объектов Image, Drawing и Visual</span><span class="sxs-lookup"><span data-stu-id="16500-122">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
