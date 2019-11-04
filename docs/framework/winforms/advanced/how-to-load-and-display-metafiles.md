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
ms.openlocfilehash: 6c17e0b2d023ccf80b0d32301b7ee6765edcae9f
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424818"
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="87a9e-102">Практическое руководство. Загрузка и отображение метафайлов</span><span class="sxs-lookup"><span data-stu-id="87a9e-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="87a9e-103">Класс <xref:System.Drawing.Imaging.Metafile>, который наследует от класса <xref:System.Drawing.Image>, предоставляет методы для записи, отображения и проверки векторных изображений.</span><span class="sxs-lookup"><span data-stu-id="87a9e-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87a9e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="87a9e-104">Example</span></span>  
 <span data-ttu-id="87a9e-105">Для отображения векторного изображения (метафайла) на экране необходим объект <xref:System.Drawing.Imaging.Metafile> и объект <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="87a9e-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="87a9e-106">Передайте имя файла (или потока) в конструктор <xref:System.Drawing.Imaging.Metafile>.</span><span class="sxs-lookup"><span data-stu-id="87a9e-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="87a9e-107">После создания объекта <xref:System.Drawing.Imaging.Metafile> передайте этот <xref:System.Drawing.Imaging.Metafile> объект в метод <xref:System.Drawing.Graphics.DrawImage%2A> объекта <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="87a9e-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="87a9e-108">В примере создается объект <xref:System.Drawing.Imaging.Metafile> из файла EMF (расширенный метафайл), а затем изображение рисуется с помощью левого верхнего угла в точке (60, 10).</span><span class="sxs-lookup"><span data-stu-id="87a9e-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="87a9e-109">На следующем рисунке показан метафайл, рисуемый в указанном месте.</span><span class="sxs-lookup"><span data-stu-id="87a9e-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="87a9e-110">![Снимок экрана, показывающий расположение изображения.](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="87a9e-110">![Screenshot showing image position.](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="87a9e-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="87a9e-111">Compiling the Code</span></span>  
 <span data-ttu-id="87a9e-112">Предыдущий пример предназначен для использования с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром обработчика событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="87a9e-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87a9e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="87a9e-113">See also</span></span>

- [<span data-ttu-id="87a9e-114">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="87a9e-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
