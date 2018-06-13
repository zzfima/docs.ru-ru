---
title: Практическое руководство. Загрузка и отображение метафайлов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: c2b0a89966100077d5a72edc11822c356d2de1b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522774"
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="6f34e-102">Практическое руководство. Загрузка и отображение метафайлов</span><span class="sxs-lookup"><span data-stu-id="6f34e-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="6f34e-103"><xref:System.Drawing.Imaging.Metafile> Класс, унаследованный от класса <xref:System.Drawing.Image> класса, предоставляет методы для записи, отображения и анализа векторных изображений.</span><span class="sxs-lookup"><span data-stu-id="6f34e-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f34e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="6f34e-104">Example</span></span>  
 <span data-ttu-id="6f34e-105">Для отображения векторного изображения (метафайла) на экране, следует <xref:System.Drawing.Imaging.Metafile> объекта и <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="6f34e-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="6f34e-106">Передайте имя файла (или потока) в <xref:System.Drawing.Imaging.Metafile> конструктора.</span><span class="sxs-lookup"><span data-stu-id="6f34e-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="6f34e-107">После создания <xref:System.Drawing.Imaging.Metafile> объекта, передать этот <xref:System.Drawing.Imaging.Metafile> объект <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="6f34e-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="6f34e-108">В примере создается <xref:System.Drawing.Imaging.Metafile> объекта из файла EMF (расширенный метафайл) и рисуется изображение с его верхнего левого угла в (60, 10).</span><span class="sxs-lookup"><span data-stu-id="6f34e-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="6f34e-109">На следующем рисунке метафайла, нарисованная в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="6f34e-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="6f34e-110">![Положение изображения](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="6f34e-110">![Image Position](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6f34e-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="6f34e-111">Compiling the Code</span></span>  
 <span data-ttu-id="6f34e-112">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="6f34e-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f34e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6f34e-113">See Also</span></span>  
 [<span data-ttu-id="6f34e-114">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="6f34e-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
