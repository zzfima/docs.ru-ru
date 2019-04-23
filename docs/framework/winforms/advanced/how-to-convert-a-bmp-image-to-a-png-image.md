---
title: Практическое руководство. Преобразование изображение из формата BMP в формат PNG
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BMP images [Windows Forms], converting to PNG
- image formats [Windows Forms], converting between
ms.assetid: 9d4a692d-73ac-4ce3-9e05-9ec321e8fbd6
ms.openlocfilehash: 3072c07781a8e8e57b64b48e5b4c304c2a0a0efb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217020"
---
# <a name="how-to-convert-a-bmp-image-to-a-png-image"></a><span data-ttu-id="e37a4-102">Практическое руководство. Преобразование изображение из формата BMP в формат PNG</span><span class="sxs-lookup"><span data-stu-id="e37a4-102">How to: Convert a BMP image to a PNG image</span></span>
<span data-ttu-id="e37a4-103">Очень часто необходимо преобразовать изображение из одного формата в другой.</span><span class="sxs-lookup"><span data-stu-id="e37a4-103">Oftentimes, you will want to convert from one image file format to another.</span></span> <span data-ttu-id="e37a4-104">Это легко сделать, вызвав метод <xref:System.Drawing.Image.Save%2A> класса <xref:System.Drawing.Image> и указав в качестве параметра <xref:System.Drawing.Imaging.ImageFormat> нужный формат файла.</span><span class="sxs-lookup"><span data-stu-id="e37a4-104">You can do this conversion easily by calling the <xref:System.Drawing.Image.Save%2A> method of the <xref:System.Drawing.Image> class and specifying the <xref:System.Drawing.Imaging.ImageFormat> for the desired image file format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e37a4-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e37a4-105">Example</span></span>  
 <span data-ttu-id="e37a4-106">В примере ниже изображение в формате BMP загружается из типа и сохраняется в формате PNG.</span><span class="sxs-lookup"><span data-stu-id="e37a4-106">The following example loads a BMP image from a type, and saves the image in the PNG format.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#4](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e37a4-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e37a4-107">Compiling the Code</span></span>  
 <span data-ttu-id="e37a4-108">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="e37a4-108">This example requires:</span></span>  
  
-   <span data-ttu-id="e37a4-109">приложение Windows Forms;</span><span class="sxs-lookup"><span data-stu-id="e37a4-109">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="e37a4-110">ссылка на пространство имен `System.Drawing.Imaging`.</span><span class="sxs-lookup"><span data-stu-id="e37a4-110">A reference to the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e37a4-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e37a4-111">See also</span></span>

- [<span data-ttu-id="e37a4-112">Практическое руководство. Получение списка установленных кодировщиков</span><span class="sxs-lookup"><span data-stu-id="e37a4-112">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="e37a4-113">Применение кодировщиков и декодеров изображений в управляемом GDI+</span><span class="sxs-lookup"><span data-stu-id="e37a4-113">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
- [<span data-ttu-id="e37a4-114">Типы растровых изображений</span><span class="sxs-lookup"><span data-stu-id="e37a4-114">Types of Bitmaps</span></span>](types-of-bitmaps.md)
