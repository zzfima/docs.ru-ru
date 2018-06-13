---
title: Практическое руководство. Использование рисунка в качестве источника изображения
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
ms.openlocfilehash: 7da8a2a594b0562667aaf417d736159d98818a63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562294"
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a><span data-ttu-id="cb8c1-102">Практическое руководство. Использование рисунка в качестве источника изображения</span><span class="sxs-lookup"><span data-stu-id="cb8c1-102">How to: Use a Drawing as an Image Source</span></span>
<span data-ttu-id="cb8c1-103">В этом примере показано, как использовать <xref:System.Windows.Media.Drawing> как <xref:System.Windows.Controls.Image.Source%2A> для <xref:System.Windows.Controls.Image> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cb8c1-103">This example shows how to use a <xref:System.Windows.Media.Drawing> as the <xref:System.Windows.Controls.Image.Source%2A> for an <xref:System.Windows.Controls.Image> control.</span></span> <span data-ttu-id="cb8c1-104">Для отображения <xref:System.Windows.Media.Drawing> с <xref:System.Windows.Controls.Image> управления, используйте <xref:System.Windows.Media.DrawingImage> как <xref:System.Windows.Controls.Image> элемента управления <xref:System.Windows.Controls.Image.Source%2A> и задайте <xref:System.Windows.Media.DrawingImage> объекта <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> свойство в документ, который требуется отобразить.</span><span class="sxs-lookup"><span data-stu-id="cb8c1-104">To display a <xref:System.Windows.Media.Drawing> with an <xref:System.Windows.Controls.Image> control, use a <xref:System.Windows.Media.DrawingImage> as the <xref:System.Windows.Controls.Image> control's <xref:System.Windows.Controls.Image.Source%2A> and set the <xref:System.Windows.Media.DrawingImage> object's <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> property to the drawing you want to display.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb8c1-105">Пример</span><span class="sxs-lookup"><span data-stu-id="cb8c1-105">Example</span></span>  
 <span data-ttu-id="cb8c1-106">В следующем примере используется <xref:System.Windows.Media.DrawingImage> и <xref:System.Windows.Controls.Image> управления для отображения <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="cb8c1-106">The following example uses a <xref:System.Windows.Media.DrawingImage> and an <xref:System.Windows.Controls.Image> control to display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="cb8c1-107">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="cb8c1-107">This example produces the following output:</span></span>  
  
 <span data-ttu-id="cb8c1-108">![GeometryDrawing двух эллипсов](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="cb8c1-108">![A GeometryDrawing of two ellipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
<span data-ttu-id="cb8c1-109">Объект DrawingImage</span><span class="sxs-lookup"><span data-stu-id="cb8c1-109">A DrawingImage</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="cb8c1-110">См. также</span><span class="sxs-lookup"><span data-stu-id="cb8c1-110">See Also</span></span>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [<span data-ttu-id="cb8c1-111">Рисование изображения с помощью объекта ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="cb8c1-111">Draw an Image Using ImageDrawing</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)  
 [<span data-ttu-id="cb8c1-112">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="cb8c1-112">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="cb8c1-113">Общие сведения об объектах класса Freezable</span><span class="sxs-lookup"><span data-stu-id="cb8c1-113">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="cb8c1-114">Атрибут PresentationOptions: Freeze</span><span class="sxs-lookup"><span data-stu-id="cb8c1-114">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
