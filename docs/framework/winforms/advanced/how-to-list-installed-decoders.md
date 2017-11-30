---
title: "Практическое руководство. Получение списка установленных декодеров"
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
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 17cbdebfa6cbb0cacacd923de4bd22125c812938
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-list-installed-decoders"></a><span data-ttu-id="7aff8-102">Практическое руководство. Получение списка установленных декодеров</span><span class="sxs-lookup"><span data-stu-id="7aff8-102">How to: List Installed Decoders</span></span>
<span data-ttu-id="7aff8-103">Можно перечислить декодеров изображений, доступных на компьютере, для определения, является ли ваше приложение сможет считать определенного файла формата изображений.</span><span class="sxs-lookup"><span data-stu-id="7aff8-103">You may want to list the image decoders available on a computer, to determine whether your application can read a particular image file format.</span></span> <span data-ttu-id="7aff8-104"><xref:System.Drawing.Imaging.ImageCodecInfo> Класс предоставляет <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> статические методы, чтобы определить, какой образ декодеров доступны.</span><span class="sxs-lookup"><span data-stu-id="7aff8-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> static methods so that you can determine which image decoders are available.</span></span> <span data-ttu-id="7aff8-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A>Возвращает массив <xref:System.Drawing.Imaging.ImageCodecInfo> объектов.</span><span class="sxs-lookup"><span data-stu-id="7aff8-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7aff8-106">Пример</span><span class="sxs-lookup"><span data-stu-id="7aff8-106">Example</span></span>  
 <span data-ttu-id="7aff8-107">В следующем примере кода возвращает список установленных декодеров и значения их свойств.</span><span class="sxs-lookup"><span data-stu-id="7aff8-107">The following code example outputs the list of installed decoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7aff8-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="7aff8-108">Compiling the Code</span></span>  
 <span data-ttu-id="7aff8-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="7aff8-109">This example requires:</span></span>  
  
-   <span data-ttu-id="7aff8-110">приложение Windows Forms;</span><span class="sxs-lookup"><span data-stu-id="7aff8-110">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="7aff8-111">Объект <xref:System.Windows.Forms.PaintEventArgs>, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="7aff8-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aff8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="7aff8-112">See Also</span></span>  
 [<span data-ttu-id="7aff8-113">Практическое руководство. Получение списка установленных кодировщиков</span><span class="sxs-lookup"><span data-stu-id="7aff8-113">How to: List Installed Encoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [<span data-ttu-id="7aff8-114">Применение кодировщиков и декодеров изображений в управляемом GDI+</span><span class="sxs-lookup"><span data-stu-id="7aff8-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
