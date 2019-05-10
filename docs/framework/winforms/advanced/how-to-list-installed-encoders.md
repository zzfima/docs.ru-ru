---
title: Практическое руководство. Получение списка установленных кодировщиков
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
ms.openlocfilehash: 2634dd96b3aa5edcecde092919eb328b7f3dadc3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626841"
---
# <a name="how-to-list-installed-encoders"></a><span data-ttu-id="9ecdf-102">Практическое руководство. Получение списка установленных кодировщиков</span><span class="sxs-lookup"><span data-stu-id="9ecdf-102">How to: List Installed Encoders</span></span>
<span data-ttu-id="9ecdf-103">Вы можете получить кодировщики изображений, доступных на компьютере, чтобы определить, может ли приложение сохранять для определенного файла формата изображений.</span><span class="sxs-lookup"><span data-stu-id="9ecdf-103">You may want to list the image encoders available on a computer, to determine whether your application can save to a particular image file format.</span></span> <span data-ttu-id="9ecdf-104"><xref:System.Drawing.Imaging.ImageCodecInfo> Класс предоставляет <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> статические методы, чтобы определить, какой образ кодировщики доступны.</span><span class="sxs-lookup"><span data-stu-id="9ecdf-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> static methods so that you can determine which image encoders are available.</span></span> <span data-ttu-id="9ecdf-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> Возвращает массив <xref:System.Drawing.Imaging.ImageCodecInfo> объектов.</span><span class="sxs-lookup"><span data-stu-id="9ecdf-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ecdf-106">Пример</span><span class="sxs-lookup"><span data-stu-id="9ecdf-106">Example</span></span>  
 <span data-ttu-id="9ecdf-107">В следующем примере кода выводит список установленных кодировщиков и значения их свойств.</span><span class="sxs-lookup"><span data-stu-id="9ecdf-107">The following code example outputs the list of installed encoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#1](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9ecdf-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="9ecdf-108">Compiling the Code</span></span>  
 <span data-ttu-id="9ecdf-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="9ecdf-109">This example requires:</span></span>  
  
- <span data-ttu-id="9ecdf-110">приложение Windows Forms;</span><span class="sxs-lookup"><span data-stu-id="9ecdf-110">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="9ecdf-111">Объект <xref:System.Windows.Forms.PaintEventArgs>, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="9ecdf-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ecdf-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9ecdf-112">See also</span></span>

- [<span data-ttu-id="9ecdf-113">Практическое руководство. Получение списка установленных декодеров</span><span class="sxs-lookup"><span data-stu-id="9ecdf-113">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)
- [<span data-ttu-id="9ecdf-114">Применение кодировщиков и декодеров изображений в управляемом GDI+</span><span class="sxs-lookup"><span data-stu-id="9ecdf-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
