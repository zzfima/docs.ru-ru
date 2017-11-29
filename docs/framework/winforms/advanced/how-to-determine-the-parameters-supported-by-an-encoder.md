---
title: "Практическое руководство. Определение параметров, поддерживаемых кодировщиком"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3e041434e9ace24618dbdc45341a0e8468721c3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="acb9d-102">Практическое руководство. Определение параметров, поддерживаемых кодировщиком</span><span class="sxs-lookup"><span data-stu-id="acb9d-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="acb9d-103">Можно настроить параметры изображения, такие как качество и уровня сжатия, но необходимо знать, какие параметры поддерживаются кодировщиком заданного изображения.</span><span class="sxs-lookup"><span data-stu-id="acb9d-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="acb9d-104"><xref:System.Drawing.Image> Класс предоставляет <xref:System.Drawing.Image.GetEncoderParameterList%2A> метод, чтобы определить, какие параметров, поддерживаемых для определенного кодировщика.</span><span class="sxs-lookup"><span data-stu-id="acb9d-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="acb9d-105">Укажите кодировщика с кодом GUID.</span><span class="sxs-lookup"><span data-stu-id="acb9d-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="acb9d-106"><xref:System.Drawing.Image.GetEncoderParameterList%2A> Метод возвращает массив <xref:System.Drawing.Imaging.EncoderParameter> объектов.</span><span class="sxs-lookup"><span data-stu-id="acb9d-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acb9d-107">Пример</span><span class="sxs-lookup"><span data-stu-id="acb9d-107">Example</span></span>  
 <span data-ttu-id="acb9d-108">В следующем примере кода выводит параметры, поддерживаемые кодировщиком JPEG.</span><span class="sxs-lookup"><span data-stu-id="acb9d-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="acb9d-109">В списке категорий параметров и связанные GUID в <xref:System.Drawing.Imaging.Encoder> Общие сведения о классе для определения категории для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="acb9d-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="acb9d-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="acb9d-110">Compiling the Code</span></span>  
 <span data-ttu-id="acb9d-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="acb9d-111">This example requires:</span></span>  
  
-   <span data-ttu-id="acb9d-112">приложение Windows Forms;</span><span class="sxs-lookup"><span data-stu-id="acb9d-112">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="acb9d-113">Объект <xref:System.Windows.Forms.PaintEventArgs>, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="acb9d-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb9d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="acb9d-114">See Also</span></span>  
 [<span data-ttu-id="acb9d-115">Практическое руководство. Получение списка установленных кодировщиков</span><span class="sxs-lookup"><span data-stu-id="acb9d-115">How to: List Installed Encoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [<span data-ttu-id="acb9d-116">Типы растровых изображений</span><span class="sxs-lookup"><span data-stu-id="acb9d-116">Types of Bitmaps</span></span>](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)  
 [<span data-ttu-id="acb9d-117">Применение кодировщиков и декодеров изображений в управляемом GDI+</span><span class="sxs-lookup"><span data-stu-id="acb9d-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
