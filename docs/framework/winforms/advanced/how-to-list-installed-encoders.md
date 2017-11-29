---
title: "Практическое руководство. Получение списка установленных кодировщиков"
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
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 70f913acb2620b5c01e1aec1f1eb98b041b82a59
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-list-installed-encoders"></a><span data-ttu-id="b079b-102">Практическое руководство. Получение списка установленных кодировщиков</span><span class="sxs-lookup"><span data-stu-id="b079b-102">How to: List Installed Encoders</span></span>
<span data-ttu-id="b079b-103">Можно перечислить кодировщики изображений, доступных на компьютере, для определения ли приложение сохранять в файл формата конкретный образ.</span><span class="sxs-lookup"><span data-stu-id="b079b-103">You may want to list the image encoders available on a computer, to determine whether your application can save to a particular image file format.</span></span> <span data-ttu-id="b079b-104"><xref:System.Drawing.Imaging.ImageCodecInfo> Класс предоставляет <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> статические методы, чтобы определить, какой образ доступных кодировщиков.</span><span class="sxs-lookup"><span data-stu-id="b079b-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> static methods so that you can determine which image encoders are available.</span></span> <span data-ttu-id="b079b-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A>Возвращает массив <xref:System.Drawing.Imaging.ImageCodecInfo> объектов.</span><span class="sxs-lookup"><span data-stu-id="b079b-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b079b-106">Пример</span><span class="sxs-lookup"><span data-stu-id="b079b-106">Example</span></span>  
 <span data-ttu-id="b079b-107">В следующем примере кода возвращает список установленных кодировщиков и значения их свойств.</span><span class="sxs-lookup"><span data-stu-id="b079b-107">The following code example outputs the list of installed encoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b079b-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="b079b-108">Compiling the Code</span></span>  
 <span data-ttu-id="b079b-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="b079b-109">This example requires:</span></span>  
  
-   <span data-ttu-id="b079b-110">приложение Windows Forms;</span><span class="sxs-lookup"><span data-stu-id="b079b-110">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="b079b-111">Объект <xref:System.Windows.Forms.PaintEventArgs>, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="b079b-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b079b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b079b-112">See Also</span></span>  
 [<span data-ttu-id="b079b-113">Практическое руководство. Получение списка установленных декодеров</span><span class="sxs-lookup"><span data-stu-id="b079b-113">How to: List Installed Decoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 [<span data-ttu-id="b079b-114">Применение кодировщиков и декодеров изображений в управляемом GDI+</span><span class="sxs-lookup"><span data-stu-id="b079b-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
