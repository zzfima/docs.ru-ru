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
ms.openlocfilehash: ce297cb6d183bc63c8b276e30100aa4e864cd90d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61722956"
---
# <a name="how-to-list-installed-encoders"></a><span data-ttu-id="1d44e-102">Практическое руководство. Получение списка установленных кодировщиков</span><span class="sxs-lookup"><span data-stu-id="1d44e-102">How to: List Installed Encoders</span></span>
<span data-ttu-id="1d44e-103">Вы можете получить кодировщики изображений, доступных на компьютере, чтобы определить, может ли приложение сохранять для определенного файла формата изображений.</span><span class="sxs-lookup"><span data-stu-id="1d44e-103">You may want to list the image encoders available on a computer, to determine whether your application can save to a particular image file format.</span></span> <span data-ttu-id="1d44e-104"><xref:System.Drawing.Imaging.ImageCodecInfo> Класс предоставляет <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> статические методы, чтобы определить, какой образ кодировщики доступны.</span><span class="sxs-lookup"><span data-stu-id="1d44e-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> static methods so that you can determine which image encoders are available.</span></span> <span data-ttu-id="1d44e-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> Возвращает массив <xref:System.Drawing.Imaging.ImageCodecInfo> объектов.</span><span class="sxs-lookup"><span data-stu-id="1d44e-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d44e-106">Пример</span><span class="sxs-lookup"><span data-stu-id="1d44e-106">Example</span></span>  
 <span data-ttu-id="1d44e-107">В следующем примере кода выводит список установленных кодировщиков и значения их свойств.</span><span class="sxs-lookup"><span data-stu-id="1d44e-107">The following code example outputs the list of installed encoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#1](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1d44e-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="1d44e-108">Compiling the Code</span></span>  
 <span data-ttu-id="1d44e-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="1d44e-109">This example requires:</span></span>  
  
- <span data-ttu-id="1d44e-110">приложение Windows Forms;</span><span class="sxs-lookup"><span data-stu-id="1d44e-110">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="1d44e-111">Объект <xref:System.Windows.Forms.PaintEventArgs>, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="1d44e-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d44e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="1d44e-112">See also</span></span>

- [<span data-ttu-id="1d44e-113">Практическое руководство. Получение списка установленных декодеров</span><span class="sxs-lookup"><span data-stu-id="1d44e-113">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)
- [<span data-ttu-id="1d44e-114">Применение кодировщиков и декодеров изображений в управляемом GDI+</span><span class="sxs-lookup"><span data-stu-id="1d44e-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
