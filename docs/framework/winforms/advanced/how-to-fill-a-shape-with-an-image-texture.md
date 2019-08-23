---
title: Практическое руководство. Заливка фигуры текстурой, созданной на основе изображения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: 42c456137f84c6fa657ba5a09727eae052a45376
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911680"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a><span data-ttu-id="61277-102">Практическое руководство. Заливка фигуры текстурой, созданной на основе изображения</span><span class="sxs-lookup"><span data-stu-id="61277-102">How to: Fill a Shape with an Image Texture</span></span>
<span data-ttu-id="61277-103">Замкнутую фигуру можно заполнить текстурой с помощью <xref:System.Drawing.Image> класса <xref:System.Drawing.TextureBrush> и класса.</span><span class="sxs-lookup"><span data-stu-id="61277-103">You can fill a closed shape with a texture by using the <xref:System.Drawing.Image> class and the <xref:System.Drawing.TextureBrush> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61277-104">Пример</span><span class="sxs-lookup"><span data-stu-id="61277-104">Example</span></span>  
 <span data-ttu-id="61277-105">В следующем примере заливка эллипса осуществляется с помощью изображения.</span><span class="sxs-lookup"><span data-stu-id="61277-105">The following example fills an ellipse with an image.</span></span> <span data-ttu-id="61277-106">Код конструирует <xref:System.Drawing.Image> объект, а затем передает адрес этого <xref:System.Drawing.Image> объекта в <xref:System.Drawing.TextureBrush.%23ctor%2A> качестве аргумента в конструктор.</span><span class="sxs-lookup"><span data-stu-id="61277-106">The code constructs an <xref:System.Drawing.Image> object, and then passes the address of that <xref:System.Drawing.Image> object as an argument to a <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="61277-107">Третья инструкция масштабирует изображение, а четвертый оператор заполняет эллипс повторяющимися копиями масштабированного изображения.</span><span class="sxs-lookup"><span data-stu-id="61277-107">The third statement scales the image, and the fourth statement fills the ellipse with repeated copies of the scaled image.</span></span>  
  
 <span data-ttu-id="61277-108">В следующем коде <xref:System.Drawing.TextureBrush.Transform%2A> свойство содержит преобразование, которое применяется к изображению перед его прорисовкой.</span><span class="sxs-lookup"><span data-stu-id="61277-108">In the following code, the <xref:System.Drawing.TextureBrush.Transform%2A> property contains the transformation that is applied to the image before it is drawn.</span></span> <span data-ttu-id="61277-109">Предположим, что исходное изображение имеет ширину 640 пикселей и высоту 480 пикселей.</span><span class="sxs-lookup"><span data-stu-id="61277-109">Assume that the original image has a width of 640 pixels and a height of 480 pixels.</span></span> <span data-ttu-id="61277-110">Преобразование сжимает изображение до 75 × 75, устанавливая горизонтальные и вертикальные значения масштабирования.</span><span class="sxs-lookup"><span data-stu-id="61277-110">The transform shrinks the image to 75×75 by setting the horizontal and vertical scaling values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="61277-111">В следующем примере размер изображения составляет 75 × 75, а размер эллипса — 150 × 250.</span><span class="sxs-lookup"><span data-stu-id="61277-111">In the following example, the image size is 75×75, and the ellipse size is 150×250.</span></span> <span data-ttu-id="61277-112">Поскольку изображение меньше, чем заливка, эллипс заполняется изображением.</span><span class="sxs-lookup"><span data-stu-id="61277-112">Because the image is smaller than the ellipse it is filling, the ellipse is tiled with the image.</span></span> <span data-ttu-id="61277-113">Мозаичное заполнение означает, что изображение повторяется горизонтально и вертикально до тех пор, пока не будет достигнута граница фигуры.</span><span class="sxs-lookup"><span data-stu-id="61277-113">Tiling means that the image is repeated horizontally and vertically until the boundary of the shape is reached.</span></span> <span data-ttu-id="61277-114">Дополнительные сведения о мозаичном заполнении [см. в разделе как Мозаичное заполнение фигуры изображением](how-to-tile-a-shape-with-an-image.md).</span><span class="sxs-lookup"><span data-stu-id="61277-114">For more information about tiling, see [How to: Tile a Shape with an Image](how-to-tile-a-shape-with-an-image.md).</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="61277-115">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="61277-115">Compiling the Code</span></span>  
 <span data-ttu-id="61277-116">Предыдущий пример предназначен для использования с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, что <xref:System.Windows.Forms.Control.Paint> является параметром обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="61277-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61277-117">См. также</span><span class="sxs-lookup"><span data-stu-id="61277-117">See also</span></span>

- [<span data-ttu-id="61277-118">Использование кисти для заливки фигур</span><span class="sxs-lookup"><span data-stu-id="61277-118">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
