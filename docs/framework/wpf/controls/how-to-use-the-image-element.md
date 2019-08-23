---
title: Практическое руководство. Использование элемента изображения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Image
- Image control [WPF]
- rendering images [WPF]
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
ms.openlocfilehash: 164eee7c10d9e388c6e6ee695af479ca2d6974b3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958328"
---
# <a name="how-to-use-the-image-element"></a><span data-ttu-id="da779-102">Практическое руководство. Использование элемента изображения</span><span class="sxs-lookup"><span data-stu-id="da779-102">How to: Use the Image Element</span></span>
<span data-ttu-id="da779-103">В этом примере показано, как включить изображения в приложение с помощью <xref:System.Windows.Controls.Image> элемента.</span><span class="sxs-lookup"><span data-stu-id="da779-103">This example shows how to include images in an application by using the <xref:System.Windows.Controls.Image> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da779-104">Пример</span><span class="sxs-lookup"><span data-stu-id="da779-104">Example</span></span>  
 <span data-ttu-id="da779-105">В следующем примере показано, как построить изображение шириной 200 пикселей.</span><span class="sxs-lookup"><span data-stu-id="da779-105">The following example shows how to render an image 200 pixels wide.</span></span> <span data-ttu-id="da779-106">В этом примере [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для определения изображения используются как синтаксис атрибута, так и синтаксис тега свойства.</span><span class="sxs-lookup"><span data-stu-id="da779-106">In this [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example, both attribute syntax and property tag syntax are used to define the image.</span></span> <span data-ttu-id="da779-107">Дополнительные сведения о синтаксисе атрибутов и синтаксисе свойств см. в разделе [Общие сведения о свойствах зависимостей](../advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da779-107">For more information on attribute syntax and property syntax, see [Dependency Properties Overview](../advanced/dependency-properties-overview.md).</span></span> <span data-ttu-id="da779-108">Объект <xref:System.Windows.Media.Imaging.BitmapImage> используется для определения исходных данных изображения и явно определен для примера синтаксиса тега свойства.</span><span class="sxs-lookup"><span data-stu-id="da779-108">A <xref:System.Windows.Media.Imaging.BitmapImage> is used to define the image's source data and is explicitly defined for the property tag syntax example.</span></span> <span data-ttu-id="da779-109">Кроме <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> того, <xref:System.Windows.Media.Imaging.BitmapImage> для свойства задается та же <xref:System.Windows.Controls.Image>ширина, что и <xref:System.Windows.FrameworkElement.Width%2A> в свойстве.</span><span class="sxs-lookup"><span data-stu-id="da779-109">In addition, the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> of the <xref:System.Windows.Media.Imaging.BitmapImage> is set to the same width as the <xref:System.Windows.FrameworkElement.Width%2A> of the <xref:System.Windows.Controls.Image>.</span></span> <span data-ttu-id="da779-110">Это позволяет использовать минимальный объем памяти при построении изображения.</span><span class="sxs-lookup"><span data-stu-id="da779-110">This is done to ensure that the minimum amount of memory is used rendering the image.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da779-111">В общем случае, если необходимо указать размер отображаемого изображения, укажите только <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> или, но не оба.</span><span class="sxs-lookup"><span data-stu-id="da779-111">In general, if you want to specify the size of a rendered image, specify only the <xref:System.Windows.FrameworkElement.Width%2A> or the <xref:System.Windows.FrameworkElement.Height%2A> but not both.</span></span> <span data-ttu-id="da779-112">Если задано одно значение, пропорции изображения сохраняются.</span><span class="sxs-lookup"><span data-stu-id="da779-112">If you only specify one, the image's aspect ratio is preserved.</span></span> <span data-ttu-id="da779-113">В противном случае изображение может внезапно оказаться растянутым или искривленным.</span><span class="sxs-lookup"><span data-stu-id="da779-113">Otherwise, the image may unexpectedly appear stretched or warped.</span></span> <span data-ttu-id="da779-114">Чтобы управлять поведением растяжения изображения, используйте <xref:System.Windows.Controls.Image.Stretch%2A> свойства и. <xref:System.Windows.Controls.Image.StretchDirection%2A></span><span class="sxs-lookup"><span data-stu-id="da779-114">To control the image's stretching behavior, use the <xref:System.Windows.Controls.Image.Stretch%2A> and <xref:System.Windows.Controls.Image.StretchDirection%2A> properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da779-115">При <xref:System.Windows.FrameworkElement.Width%2A> указании размера изображения с помощью или <xref:System.Windows.FrameworkElement.Height%2A>необходимо также задать <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> один и <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> тот же размер.</span><span class="sxs-lookup"><span data-stu-id="da779-115">When you specify the size of an image with either <xref:System.Windows.FrameworkElement.Width%2A> or <xref:System.Windows.FrameworkElement.Height%2A>, you should also set either <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> or <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> to the same respective size.</span></span>  
  
 <span data-ttu-id="da779-116"><xref:System.Windows.Controls.Image.Stretch%2A> Свойство определяет способ растяжения источника изображения для заполнения элемента изображения.</span><span class="sxs-lookup"><span data-stu-id="da779-116">The <xref:System.Windows.Controls.Image.Stretch%2A> property determines how the image source is stretched to fill the image element.</span></span> <span data-ttu-id="da779-117">Дополнительные сведения см. в описании перечисления <xref:System.Windows.Media.Stretch>.</span><span class="sxs-lookup"><span data-stu-id="da779-117">For more information, see the <xref:System.Windows.Media.Stretch> enumeration.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="da779-118">Пример</span><span class="sxs-lookup"><span data-stu-id="da779-118">Example</span></span>  
 <span data-ttu-id="da779-119">В следующем примере показано, как построить изображение шириной 200 пикселей с использованием кода.</span><span class="sxs-lookup"><span data-stu-id="da779-119">The following example shows how to render an image 200 pixels wide using code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da779-120">Свойства <xref:System.Windows.Media.Imaging.BitmapImage> установки должны выполняться <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> в блоке и <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> .</span><span class="sxs-lookup"><span data-stu-id="da779-120">Setting <xref:System.Windows.Media.Imaging.BitmapImage> properties must be done within a <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> and <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> block.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="da779-121">См. также</span><span class="sxs-lookup"><span data-stu-id="da779-121">See also</span></span>

- [<span data-ttu-id="da779-122">Общие сведения об обработке изображений</span><span class="sxs-lookup"><span data-stu-id="da779-122">Imaging Overview</span></span>](../graphics-multimedia/imaging-overview.md)
