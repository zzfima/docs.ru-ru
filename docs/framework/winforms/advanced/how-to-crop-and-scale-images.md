---
title: "Практическое руководство. Обрезка и масштабирование изображений"
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
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8fb5d527cd1047197f370c4a9a9b1f8f33461653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-crop-and-scale-images"></a><span data-ttu-id="ad3e1-102">Практическое руководство. Обрезка и масштабирование изображений</span><span class="sxs-lookup"><span data-stu-id="ad3e1-102">How to: Crop and Scale Images</span></span>
<span data-ttu-id="ad3e1-103"><xref:System.Drawing.Graphics> Класс предоставляет несколько <xref:System.Drawing.Graphics.DrawImage%2A> методы, некоторые из которых имеют параметры прямоугольника источника и назначения, которые можно использовать для обрезки и масштабирования изображений.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-103">The <xref:System.Drawing.Graphics> class provides several <xref:System.Drawing.Graphics.DrawImage%2A> methods, some of which have source and destination rectangle parameters that you can use to crop and scale images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad3e1-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ad3e1-104">Example</span></span>  
 <span data-ttu-id="ad3e1-105">В следующем примере создается <xref:System.Drawing.Image> объекта на основе файла Apple.gif.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-105">The following example constructs an <xref:System.Drawing.Image> object from the disk file Apple.gif.</span></span> <span data-ttu-id="ad3e1-106">Код рисует изображение яблока, полностью исходный размер.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-106">The code draws the entire apple image in its original size.</span></span> <span data-ttu-id="ad3e1-107">Затем код вызывает <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта для рисования фрагмента изображения яблока в прямоугольнике назначения, большего, чем исходное изображение apple.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-107">The code then calls the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object to draw a portion of the apple image in a destination rectangle that is larger than the original apple image.</span></span>  
  
 <span data-ttu-id="ad3e1-108"><xref:System.Drawing.Graphics.DrawImage%2A> Метод определяет, какая часть apple для рисования, анализируя исходный прямоугольник, задаваемый третьим, четвертым, пятая и шестая параметрами.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-108">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines which portion of the apple to draw by looking at the source rectangle, which is specified by the third, fourth, fifth, and sixth arguments.</span></span> <span data-ttu-id="ad3e1-109">В этом случае apple обрезается 75% от ширины и 75% высоты.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-109">In this case, the apple is cropped to 75 percent of its width and 75 percent of its height.</span></span>  
  
 <span data-ttu-id="ad3e1-110"><xref:System.Drawing.Graphics.DrawImage%2A> Метод определяет, где рисовать обрезанное изображение яблока и как вносить обрезанное изображение яблока, анализируя прямоугольник назначения, который указан с помощью второго аргумента.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-110">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines where to draw the cropped apple and how big to make the cropped apple by looking at the destination rectangle, which is specified by the second argument.</span></span> <span data-ttu-id="ad3e1-111">В этом случае прямоугольника назначения — 30% шире и 30% выше, чем исходное изображение.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-111">In this case, the destination rectangle is 30 percent wider and 30 percent taller than the original image.</span></span>  
  
 <span data-ttu-id="ad3e1-112">Ниже показан исходный apple и масштабированное обрезанное изображение.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-112">The following illustration shows the original apple and the scaled, cropped apple.</span></span>  
  
 <span data-ttu-id="ad3e1-113">![Обрезка и масштабирование](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")</span><span class="sxs-lookup"><span data-stu-id="ad3e1-113">![Crop & Scale](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ad3e1-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="ad3e1-114">Compiling the Code</span></span>  
 <span data-ttu-id="ad3e1-115">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="ad3e1-116">Обязательно замените `Apple.gif` в вашей системе путь и имя файла изображения.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-116">Make sure to replace `Apple.gif` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad3e1-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ad3e1-117">See Also</span></span>  
 [<span data-ttu-id="ad3e1-118">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="ad3e1-118">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="ad3e1-119">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="ad3e1-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
