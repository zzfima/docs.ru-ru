---
title: Практическое руководство. Определение параметров, поддерживаемых кодировщиком
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: 2626eee239d9876125340dd133c5a9b3e45c3d7e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204579"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="18246-102">Практическое руководство. Определение параметров, поддерживаемых кодировщиком</span><span class="sxs-lookup"><span data-stu-id="18246-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="18246-103">Можно настроить параметры изображения, такие как качество и уровня сжатия, но необходимо знать, какие параметры поддерживаются кодировщиком заданного изображения.</span><span class="sxs-lookup"><span data-stu-id="18246-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="18246-104"><xref:System.Drawing.Image> Класс предоставляет <xref:System.Drawing.Image.GetEncoderParameterList%2A> метод, чтобы можно было определить, какие параметров, поддерживаемых для конкретного кодировщика.</span><span class="sxs-lookup"><span data-stu-id="18246-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="18246-105">Укажите кодировщик с идентификатором GUID.</span><span class="sxs-lookup"><span data-stu-id="18246-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="18246-106"><xref:System.Drawing.Image.GetEncoderParameterList%2A> Метод возвращает массив <xref:System.Drawing.Imaging.EncoderParameter> объектов.</span><span class="sxs-lookup"><span data-stu-id="18246-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18246-107">Пример</span><span class="sxs-lookup"><span data-stu-id="18246-107">Example</span></span>  
 <span data-ttu-id="18246-108">Следующий пример кода выводит поддерживаемые параметры для кодировщику JPEG.</span><span class="sxs-lookup"><span data-stu-id="18246-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="18246-109">Используйте список категорий параметров и связанные идентификаторы GUID в <xref:System.Drawing.Imaging.Encoder> Общие сведения о классе для определения категории для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="18246-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="18246-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="18246-110">Compiling the Code</span></span>  
 <span data-ttu-id="18246-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="18246-111">This example requires:</span></span>  
  
-   <span data-ttu-id="18246-112">приложение Windows Forms;</span><span class="sxs-lookup"><span data-stu-id="18246-112">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="18246-113">Объект <xref:System.Windows.Forms.PaintEventArgs>, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="18246-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18246-114">См. также</span><span class="sxs-lookup"><span data-stu-id="18246-114">See also</span></span>

- [<span data-ttu-id="18246-115">Практическое руководство. Получение списка установленных кодировщиков</span><span class="sxs-lookup"><span data-stu-id="18246-115">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="18246-116">Типы растровых изображений</span><span class="sxs-lookup"><span data-stu-id="18246-116">Types of Bitmaps</span></span>](types-of-bitmaps.md)
- [<span data-ttu-id="18246-117">Применение кодировщиков и декодеров изображений в управляемом GDI+</span><span class="sxs-lookup"><span data-stu-id="18246-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
