---
title: Практическое руководство. Получение списка установленных декодеров
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
ms.openlocfilehash: c40bb79dde4a9baf8b84f3cda5fdabc6e30ad0b5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717535"
---
# <a name="how-to-list-installed-decoders"></a><span data-ttu-id="09eb0-102">Практическое руководство. Получение списка установленных декодеров</span><span class="sxs-lookup"><span data-stu-id="09eb0-102">How to: List Installed Decoders</span></span>
<span data-ttu-id="09eb0-103">Может потребоваться списке декодеров на компьютере, чтобы определить, является ли ваше приложение может считывать определенного файла формата изображений.</span><span class="sxs-lookup"><span data-stu-id="09eb0-103">You may want to list the image decoders available on a computer, to determine whether your application can read a particular image file format.</span></span> <span data-ttu-id="09eb0-104"><xref:System.Drawing.Imaging.ImageCodecInfo> Класс предоставляет <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> статические методы, чтобы определить, какой образ декодеров доступны.</span><span class="sxs-lookup"><span data-stu-id="09eb0-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> static methods so that you can determine which image decoders are available.</span></span> <span data-ttu-id="09eb0-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> Возвращает массив <xref:System.Drawing.Imaging.ImageCodecInfo> объектов.</span><span class="sxs-lookup"><span data-stu-id="09eb0-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09eb0-106">Пример</span><span class="sxs-lookup"><span data-stu-id="09eb0-106">Example</span></span>  
 <span data-ttu-id="09eb0-107">В следующем примере кода выводит список установленных декодеров и значения их свойств.</span><span class="sxs-lookup"><span data-stu-id="09eb0-107">The following code example outputs the list of installed decoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#2](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="09eb0-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="09eb0-108">Compiling the Code</span></span>  
 <span data-ttu-id="09eb0-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="09eb0-109">This example requires:</span></span>  
  
-   <span data-ttu-id="09eb0-110">приложение Windows Forms;</span><span class="sxs-lookup"><span data-stu-id="09eb0-110">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="09eb0-111">Объект <xref:System.Windows.Forms.PaintEventArgs>, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="09eb0-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09eb0-112">См. также</span><span class="sxs-lookup"><span data-stu-id="09eb0-112">See also</span></span>
- [<span data-ttu-id="09eb0-113">Практическое руководство. Получение списка установленных кодировщиков</span><span class="sxs-lookup"><span data-stu-id="09eb0-113">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="09eb0-114">Применение кодировщиков и декодеров изображений в управляемом GDI+</span><span class="sxs-lookup"><span data-stu-id="09eb0-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
