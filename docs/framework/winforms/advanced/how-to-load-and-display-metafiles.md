---
title: Как выполнить Загрузка и отображение метафайлов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: d0835d7f2c5ffea44f22661a765ab16b1d0130c5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619562"
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="b03fc-102">Как выполнить Загрузка и отображение метафайлов</span><span class="sxs-lookup"><span data-stu-id="b03fc-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="b03fc-103"><xref:System.Drawing.Imaging.Metafile> Класс, унаследованный от <xref:System.Drawing.Image> класса, предоставляет методы для записи, отображения и анализа векторных изображений.</span><span class="sxs-lookup"><span data-stu-id="b03fc-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b03fc-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b03fc-104">Example</span></span>  
 <span data-ttu-id="b03fc-105">Чтобы отобразить векторного изображения (метафайла) на экране, вам потребуется <xref:System.Drawing.Imaging.Metafile> объекта и <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="b03fc-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="b03fc-106">Передать имя файла (или потока) <xref:System.Drawing.Imaging.Metafile> конструктор.</span><span class="sxs-lookup"><span data-stu-id="b03fc-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="b03fc-107">После создания <xref:System.Drawing.Imaging.Metafile> , передать, <xref:System.Drawing.Imaging.Metafile> объект <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="b03fc-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="b03fc-108">В примере создается <xref:System.Drawing.Imaging.Metafile> объект из файла EMF (расширенный метафайл) и затем рисует изображение с его верхнего левого угла в (60, 10).</span><span class="sxs-lookup"><span data-stu-id="b03fc-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="b03fc-109">Ниже показан метафайла, содержащейся в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="b03fc-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="b03fc-110">![Положение изображения](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="b03fc-110">![Image Position](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b03fc-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="b03fc-111">Compiling the Code</span></span>  
 <span data-ttu-id="b03fc-112">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="b03fc-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b03fc-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b03fc-113">See also</span></span>
- [<span data-ttu-id="b03fc-114">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="b03fc-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
