---
title: Практическое руководство. Обрезка и масштабирование изображений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
ms.openlocfilehash: 4257431881565f9160f45795111d374cc680dedd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189910"
---
# <a name="how-to-crop-and-scale-images"></a><span data-ttu-id="9c3e4-102">Практическое руководство. Обрезка и масштабирование изображений</span><span class="sxs-lookup"><span data-stu-id="9c3e4-102">How to: Crop and Scale Images</span></span>
<span data-ttu-id="9c3e4-103"><xref:System.Drawing.Graphics> Класс предоставляет несколько <xref:System.Drawing.Graphics.DrawImage%2A> методы, некоторые из которых имеют параметры прямоугольника источника и назначения, которые можно использовать для обрезки и масштабирования изображений.</span><span class="sxs-lookup"><span data-stu-id="9c3e4-103">The <xref:System.Drawing.Graphics> class provides several <xref:System.Drawing.Graphics.DrawImage%2A> methods, some of which have source and destination rectangle parameters that you can use to crop and scale images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c3e4-104">Пример</span><span class="sxs-lookup"><span data-stu-id="9c3e4-104">Example</span></span>  
 <span data-ttu-id="9c3e4-105">В следующем примере создается <xref:System.Drawing.Image> объект из файла Apple.gif.</span><span class="sxs-lookup"><span data-stu-id="9c3e4-105">The following example constructs an <xref:System.Drawing.Image> object from the disk file Apple.gif.</span></span> <span data-ttu-id="9c3e4-106">Код рисует изображение всей apple в его исходном размере.</span><span class="sxs-lookup"><span data-stu-id="9c3e4-106">The code draws the entire apple image in its original size.</span></span> <span data-ttu-id="9c3e4-107">Затем код вызывает <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> для рисования фрагмента изображения apple в прямоугольник назначения, который больше, чем исходное изображение apple.</span><span class="sxs-lookup"><span data-stu-id="9c3e4-107">The code then calls the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object to draw a portion of the apple image in a destination rectangle that is larger than the original apple image.</span></span>  
  
 <span data-ttu-id="9c3e4-108"><xref:System.Drawing.Graphics.DrawImage%2A> Метод определяет, какая часть элемента apple для рисования, просмотрев исходный прямоугольник, который задается в-четвертых, третий, пятая и шестая аргументы.</span><span class="sxs-lookup"><span data-stu-id="9c3e4-108">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines which portion of the apple to draw by looking at the source rectangle, which is specified by the third, fourth, fifth, and sixth arguments.</span></span> <span data-ttu-id="9c3e4-109">В этом случае apple обрезается 75 процентов от его ширины и 75% высоты.</span><span class="sxs-lookup"><span data-stu-id="9c3e4-109">In this case, the apple is cropped to 75 percent of its width and 75 percent of its height.</span></span>  
  
 <span data-ttu-id="9c3e4-110"><xref:System.Drawing.Graphics.DrawImage%2A> Метод определяет, где рисовать обрезанное apple и как осуществлять обрезанное apple, просмотрев целевого прямоугольника, который указан с помощью второго аргумента.</span><span class="sxs-lookup"><span data-stu-id="9c3e4-110">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines where to draw the cropped apple and how big to make the cropped apple by looking at the destination rectangle, which is specified by the second argument.</span></span> <span data-ttu-id="9c3e4-111">В этом случае целевого прямоугольника — 30% шире и 30% выше, чем исходное изображение.</span><span class="sxs-lookup"><span data-stu-id="9c3e4-111">In this case, the destination rectangle is 30 percent wider and 30 percent taller than the original image.</span></span>  
  
 <span data-ttu-id="9c3e4-112">Ниже показан исходный apple и масштабированное обрезанное изображение.</span><span class="sxs-lookup"><span data-stu-id="9c3e4-112">The following illustration shows the original apple and the scaled, cropped apple.</span></span>  
  
 ![Снимок экрана исходный образ и то же изображение обрезается.](./media/how-to-crop-and-scale-images/original-image-cropped-image.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9c3e4-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="9c3e4-114">Compiling the Code</span></span>  
 <span data-ttu-id="9c3e4-115">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="9c3e4-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="9c3e4-116">Не забудьте заменить `Apple.gif` путь, допустимые в вашей системе и имя файла изображения.</span><span class="sxs-lookup"><span data-stu-id="9c3e4-116">Make sure to replace `Apple.gif` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c3e4-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9c3e4-117">See also</span></span>

- [<span data-ttu-id="9c3e4-118">Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile</span><span class="sxs-lookup"><span data-stu-id="9c3e4-118">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="9c3e4-119">Работа с растровыми и векторными изображениями</span><span class="sxs-lookup"><span data-stu-id="9c3e4-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
