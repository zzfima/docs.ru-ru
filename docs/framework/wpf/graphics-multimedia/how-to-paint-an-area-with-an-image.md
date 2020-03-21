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
# <a name="how-to-paint-an-area-with-an-image"></a><span data-ttu-id="a9913-102">Инструкция по закрашиванию области с изображением</span><span class="sxs-lookup"><span data-stu-id="a9913-102">How to: Paint an Area with an Image</span></span>
<span data-ttu-id="a9913-103">В этом примере <xref:System.Windows.Media.ImageBrush> показано, как использовать класс для нарисования области с изображением.</span><span class="sxs-lookup"><span data-stu-id="a9913-103">This example shows how to use the <xref:System.Windows.Media.ImageBrush> class to paint an area with an image.</span></span> <span data-ttu-id="a9913-104">Отображаетодно <xref:System.Windows.Media.ImageBrush> одно изображение, которое определяется его <xref:System.Windows.Media.ImageBrush.ImageSource%2A> свойством.</span><span class="sxs-lookup"><span data-stu-id="a9913-104">An <xref:System.Windows.Media.ImageBrush> displays a single image, which is specified by its <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9913-105">Пример</span><span class="sxs-lookup"><span data-stu-id="a9913-105">Example</span></span>  
 <span data-ttu-id="a9913-106">Следующий пример рисует <xref:System.Windows.Controls.Control.Background%2A> кнопку с <xref:System.Windows.Media.ImageBrush>помощью .</span><span class="sxs-lookup"><span data-stu-id="a9913-106">The following example paints the <xref:System.Windows.Controls.Control.Background%2A> of a button by using an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 <span data-ttu-id="a9913-107">По умолчанию, <xref:System.Windows.Media.ImageBrush> растягивает свой образ, чтобы полностью заполнить область, которую вы рисуете.</span><span class="sxs-lookup"><span data-stu-id="a9913-107">By default, an <xref:System.Windows.Media.ImageBrush> stretches its image to completely fill the area that you are painting.</span></span> <span data-ttu-id="a9913-108">В предыдущем примере изображение растягивается до заполнения кнопки, возможно искажение изображения.</span><span class="sxs-lookup"><span data-stu-id="a9913-108">In the preceding example, the image is stretched to fill the button, possibly distorting the image.</span></span> <span data-ttu-id="a9913-109">Вы можете контролировать это <xref:System.Windows.Media.TileBrush.Stretch%2A> поведение, <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.Stretch.Uniform> установив <xref:System.Windows.Media.Stretch.UniformToFill>свойство к или , что приводит к кисти, чтобы сохранить соотношение сторон изображения.</span><span class="sxs-lookup"><span data-stu-id="a9913-109">You can control this behavior by setting the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of <xref:System.Windows.Media.TileBrush> to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>, which causes the brush to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="a9913-110">Если вы <xref:System.Windows.Media.TileBrush.Viewport%2A> установите <xref:System.Windows.Media.TileBrush.TileMode%2A> и <xref:System.Windows.Media.ImageBrush>свойства, вы можете создать повторяющийся шаблон.</span><span class="sxs-lookup"><span data-stu-id="a9913-110">If you set the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties of an <xref:System.Windows.Media.ImageBrush>, you can create a repeating pattern.</span></span> <span data-ttu-id="a9913-111">Следующий пример закрашивает кнопку с помощью шаблона, который создается из изображения.</span><span class="sxs-lookup"><span data-stu-id="a9913-111">The following example paints a button by using a pattern that is created from an image.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 <span data-ttu-id="a9913-112">Для получения дополнительной <xref:System.Windows.Media.ImageBrush> информации о классе, см [Картина с изображениями, рисунки и визуальные эффекты](painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="a9913-112">For more information about the <xref:System.Windows.Media.ImageBrush> class, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="a9913-113">Этот пример кода является частью более крупного примера, который предоставляется классу. <xref:System.Windows.Media.ImageBrush></span><span class="sxs-lookup"><span data-stu-id="a9913-113">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="a9913-114">Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)</span><span class="sxs-lookup"><span data-stu-id="a9913-114">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9913-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a9913-115">See also</span></span>

- [<span data-ttu-id="a9913-116">Заполнение с использованием изображений, рисунков и визуальных элементов</span><span class="sxs-lookup"><span data-stu-id="a9913-116">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
