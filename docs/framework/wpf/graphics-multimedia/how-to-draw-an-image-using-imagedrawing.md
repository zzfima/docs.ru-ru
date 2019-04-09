---
title: Практическое руководство. Рисование изображения с помощью объекта ImageDrawing
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
ms.openlocfilehash: f9459185bf81160b45222e7d6821e0f945ada381
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100162"
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a><span data-ttu-id="93a15-102">Практическое руководство. Рисование изображения с помощью объекта ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="93a15-102">How to: Draw an Image Using ImageDrawing</span></span>
<span data-ttu-id="93a15-103">В этом примере показано, как использовать <xref:System.Windows.Media.ImageDrawing> для рисования изображения.</span><span class="sxs-lookup"><span data-stu-id="93a15-103">This example shows how to use an <xref:System.Windows.Media.ImageDrawing> to draw an image.</span></span> <span data-ttu-id="93a15-104"><xref:System.Windows.Media.ImageDrawing> Позволяет отображать <xref:System.Windows.Media.ImageSource> с <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, или <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="93a15-104">An <xref:System.Windows.Media.ImageDrawing> enables you display an <xref:System.Windows.Media.ImageSource> with a <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, or <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="93a15-105">Чтобы нарисовать изображение, необходимо создать <xref:System.Windows.Media.ImageDrawing> и задайте его <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> и <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> свойства.</span><span class="sxs-lookup"><span data-stu-id="93a15-105">To draw an image, you create an <xref:System.Windows.Media.ImageDrawing> and set its <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> and <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="93a15-106"><xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> Свойство задает изображения для рисования и <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> свойство указывает положение и размер каждого изображения.</span><span class="sxs-lookup"><span data-stu-id="93a15-106">The <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> property specifies the image to draw, and the <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> property specifies the position and size of each image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93a15-107">Пример</span><span class="sxs-lookup"><span data-stu-id="93a15-107">Example</span></span>  
 <span data-ttu-id="93a15-108">В следующем примере создается составной рисунок с помощью четырех <xref:System.Windows.Media.ImageDrawing> объектов.</span><span class="sxs-lookup"><span data-stu-id="93a15-108">The following example creates a composite drawing using four <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="93a15-109">В этом примере получается следующее изображение:</span><span class="sxs-lookup"><span data-stu-id="93a15-109">This example produces the following image:</span></span>  
  
 <span data-ttu-id="93a15-110">![Несколько объектов DrawingImage](./media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span><span class="sxs-lookup"><span data-stu-id="93a15-110">![Several DrawingImage objects](./media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span></span>  
<span data-ttu-id="93a15-111">Четыре объекта ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="93a15-111">Four ImageDrawing objects</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 <span data-ttu-id="93a15-112">Пример, показывающий простой способ отображения изображения без использования <xref:System.Windows.Media.ImageDrawing>, см. в разделе [использование элемента изображения](../controls/how-to-use-the-image-element.md).</span><span class="sxs-lookup"><span data-stu-id="93a15-112">For an example showing a simple way to display an image without using <xref:System.Windows.Media.ImageDrawing>, see [Use the Image Element](../controls/how-to-use-the-image-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93a15-113">См. также</span><span class="sxs-lookup"><span data-stu-id="93a15-113">See also</span></span>

- <xref:System.Windows.Freezable.Freeze%2A>
- <xref:System.Windows.Controls.Image>
- [<span data-ttu-id="93a15-114">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="93a15-114">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="93a15-115">Общие сведения об объектах класса Freezable</span><span class="sxs-lookup"><span data-stu-id="93a15-115">Freezable Objects Overview</span></span>](../advanced/freezable-objects-overview.md)
- [<span data-ttu-id="93a15-116">Атрибут PresentationOptions:Freeze</span><span class="sxs-lookup"><span data-stu-id="93a15-116">PresentationOptions:Freeze Attribute</span></span>](../advanced/presentationoptions-freeze-attribute.md)
