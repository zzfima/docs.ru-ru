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
ms.openlocfilehash: 5899531291c22ada76213905d0f2ca6944fcbba7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408024"
---
# <a name="how-to-paint-an-area-with-an-image"></a><span data-ttu-id="d9df2-102">Инструкция по закрашиванию области с изображением</span><span class="sxs-lookup"><span data-stu-id="d9df2-102">How to: Paint an Area with an Image</span></span>
<span data-ttu-id="d9df2-103">В этом примере показано, как использовать <xref:System.Windows.Media.ImageBrush> класс для закраски области изображением.</span><span class="sxs-lookup"><span data-stu-id="d9df2-103">This example shows how to use the <xref:System.Windows.Media.ImageBrush> class to paint an area with an image.</span></span> <span data-ttu-id="d9df2-104"><xref:System.Windows.Media.ImageBrush> Отображает одно изображение, которое определяется ее <xref:System.Windows.Media.ImageBrush.ImageSource%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="d9df2-104">An <xref:System.Windows.Media.ImageBrush> displays a single image, which is specified by its <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9df2-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d9df2-105">Example</span></span>  
 <span data-ttu-id="d9df2-106">В следующем примере закрашивается <xref:System.Windows.Controls.Control.Background%2A> кнопки с помощью <xref:System.Windows.Media.ImageBrush>.</span><span class="sxs-lookup"><span data-stu-id="d9df2-106">The following example paints the <xref:System.Windows.Controls.Control.Background%2A> of a button by using an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 <span data-ttu-id="d9df2-107">По умолчанию <xref:System.Windows.Media.ImageBrush> растягивает изображения до полного заполнения закрашиваемой области.</span><span class="sxs-lookup"><span data-stu-id="d9df2-107">By default, an <xref:System.Windows.Media.ImageBrush> stretches its image to completely fill the area that you are painting.</span></span> <span data-ttu-id="d9df2-108">В предыдущем примере изображение растягивается до заполнения кнопки, возможно искажение изображения.</span><span class="sxs-lookup"><span data-stu-id="d9df2-108">In the preceding example, the image is stretched to fill the button, possibly distorting the image.</span></span> <span data-ttu-id="d9df2-109">Этим поведением можно управлять, задав <xref:System.Windows.Media.TileBrush.Stretch%2A> свойство <xref:System.Windows.Media.TileBrush> для <xref:System.Windows.Media.Stretch.Uniform> или <xref:System.Windows.Media.Stretch.UniformToFill>, чего кисть сохранить пропорции изображения.</span><span class="sxs-lookup"><span data-stu-id="d9df2-109">You can control this behavior by setting the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of <xref:System.Windows.Media.TileBrush> to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>, which causes the brush to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="d9df2-110">Если задать <xref:System.Windows.Media.TileBrush.Viewport%2A> и <xref:System.Windows.Media.TileBrush.TileMode%2A> свойства <xref:System.Windows.Media.ImageBrush>, можно создать повторяющийся шаблон.</span><span class="sxs-lookup"><span data-stu-id="d9df2-110">If you set the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties of an <xref:System.Windows.Media.ImageBrush>, you can create a repeating pattern.</span></span> <span data-ttu-id="d9df2-111">Следующий пример закрашивает кнопку с помощью шаблона, который создается из изображения.</span><span class="sxs-lookup"><span data-stu-id="d9df2-111">The following example paints a button by using a pattern that is created from an image.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 <span data-ttu-id="d9df2-112">Дополнительные сведения о <xref:System.Windows.Media.ImageBrush> , представлена в разделе [Рисование с помощью изображений, рисунков и визуальных элементов](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span><span class="sxs-lookup"><span data-stu-id="d9df2-112">For more information about the <xref:System.Windows.Media.ImageBrush> class, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="d9df2-113">Данный пример кода является частью большего примера, предоставляемый для <xref:System.Windows.Media.ImageBrush> класса.</span><span class="sxs-lookup"><span data-stu-id="d9df2-113">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="d9df2-114">Полный пример см. в разделе [пример использования кистей](https://go.microsoft.com/fwlink/?LinkID=160005).</span><span class="sxs-lookup"><span data-stu-id="d9df2-114">For the complete sample, see [ImageBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9df2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d9df2-115">See Also</span></span>  
 [<span data-ttu-id="d9df2-116">Заливка с помощью объектов Image, Drawing и Visual</span><span class="sxs-lookup"><span data-stu-id="d9df2-116">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
