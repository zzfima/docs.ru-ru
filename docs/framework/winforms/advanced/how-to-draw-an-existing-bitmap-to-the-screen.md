---
title: Практическое руководство. Рисование существующего точечного рисунка на экране
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
ms.openlocfilehash: 2c66c1e2cdd0ee3f1a189b9a27284566210ef480
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a><span data-ttu-id="31e9b-102">Практическое руководство. Рисование существующего точечного рисунка на экране</span><span class="sxs-lookup"><span data-stu-id="31e9b-102">How to: Draw an Existing Bitmap to the Screen</span></span>
<span data-ttu-id="31e9b-103">Можно легко нарисовать существующее изображение на экране.</span><span class="sxs-lookup"><span data-stu-id="31e9b-103">You can easily draw an existing image on the screen.</span></span> <span data-ttu-id="31e9b-104">Сначала необходимо создать <xref:System.Drawing.Bitmap> объекта, используя конструктор точечного рисунка, который принимает имя файла, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="31e9b-104">First you need to create a <xref:System.Drawing.Bitmap> object by using the bitmap constructor that takes a file name, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>.</span></span> <span data-ttu-id="31e9b-105">Этот конструктор поддерживает изображения нескольких форматов, включая BMP, GIF, JPEG, PNG и TIFF.</span><span class="sxs-lookup"><span data-stu-id="31e9b-105">This constructor accepts images with several different file formats, including BMP, GIF, JPEG, PNG, and TIFF.</span></span> <span data-ttu-id="31e9b-106">После создания <xref:System.Drawing.Bitmap> объекта, передать этот <xref:System.Drawing.Bitmap> объект <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="31e9b-106">After you have created the <xref:System.Drawing.Bitmap> object, pass that <xref:System.Drawing.Bitmap> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31e9b-107">Пример</span><span class="sxs-lookup"><span data-stu-id="31e9b-107">Example</span></span>  
 <span data-ttu-id="31e9b-108">В этом примере создается <xref:System.Drawing.Bitmap> объекта из файла в формате JPEG и рисуется растровое изображение, с его верхнего левого угла в (60, 10).</span><span class="sxs-lookup"><span data-stu-id="31e9b-108">This example creates a <xref:System.Drawing.Bitmap> object from a JPEG file and then draws the bitmap with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="31e9b-109">На следующем рисунке точечный рисунок рисуется в указанном месте.</span><span class="sxs-lookup"><span data-stu-id="31e9b-109">The following illustration shows the bitmap drawn at the specified location.</span></span>  
  
 <span data-ttu-id="31e9b-110">![Положение изображения](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")</span><span class="sxs-lookup"><span data-stu-id="31e9b-110">![Image Position](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="31e9b-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="31e9b-111">Compiling the Code</span></span>  
 <span data-ttu-id="31e9b-112">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="31e9b-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31e9b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="31e9b-113">See Also</span></span>  
 [<span data-ttu-id="31e9b-114">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="31e9b-114">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="31e9b-115">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="31e9b-115">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
