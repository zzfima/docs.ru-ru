---
title: Практическое руководство. Обрезка изображения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
ms.openlocfilehash: 189cb92d581ccc9209ebdb4de18487951d17818a
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44199288"
---
# <a name="how-to-crop-an-image"></a><span data-ttu-id="837e2-102">Практическое руководство. Обрезка изображения</span><span class="sxs-lookup"><span data-stu-id="837e2-102">How to: Crop an Image</span></span>
<span data-ttu-id="837e2-103">В этом примере показано, как обрезать изображение с помощью <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span><span class="sxs-lookup"><span data-stu-id="837e2-103">This example shows how to crop an image using <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span></span>  
  
 <span data-ttu-id="837e2-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> используется главным образом при кодировании обрезанной версии изображения для сохранения файла.</span><span class="sxs-lookup"><span data-stu-id="837e2-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> is primarily used when encoding a cropped version of an image to save out to a file.</span></span> <span data-ttu-id="837e2-105">Чтобы обрезать изображение для отображения см. в целях [Создание области отсечения](https://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376) раздела.</span><span class="sxs-lookup"><span data-stu-id="837e2-105">To crop an image for display purposes see the [Create a Clip Region](https://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="837e2-106">Пример</span><span class="sxs-lookup"><span data-stu-id="837e2-106">Example</span></span>  
 <span data-ttu-id="837e2-107">Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] определяет ресурсы, используемые в примерах ниже.</span><span class="sxs-lookup"><span data-stu-id="837e2-107">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] defines resources used within the samples below.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 <span data-ttu-id="837e2-108">В следующем примере создается образ с помощью <xref:System.Windows.Media.Imaging.CroppedBitmap> в качестве источника.</span><span class="sxs-lookup"><span data-stu-id="837e2-108">The following example creates an image using a <xref:System.Windows.Media.Imaging.CroppedBitmap> as its source.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <span data-ttu-id="837e2-109"><xref:System.Windows.Media.Imaging.CroppedBitmap> Также может использоваться как источник другого <xref:System.Windows.Media.Imaging.CroppedBitmap>, цепочки обрезки.</span><span class="sxs-lookup"><span data-stu-id="837e2-109">The <xref:System.Windows.Media.Imaging.CroppedBitmap> can also be used as the source of another <xref:System.Windows.Media.Imaging.CroppedBitmap>, chaining the cropping.</span></span> <span data-ttu-id="837e2-110">Обратите внимание, что <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> использует значения, которые задаются относительно источника обрезается растровое изображение и не начальный образ.</span><span class="sxs-lookup"><span data-stu-id="837e2-110">Note that the <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> uses values that are relative to the source cropped bitmap and not the initial image.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a><span data-ttu-id="837e2-111">См. также</span><span class="sxs-lookup"><span data-stu-id="837e2-111">See Also</span></span>  
 [<span data-ttu-id="837e2-112">Создание области отсечения</span><span class="sxs-lookup"><span data-stu-id="837e2-112">Create a Clip Region</span></span>](https://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376)
