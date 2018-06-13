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
ms.openlocfilehash: c1eb090bebcced125193c1db16087b6165d27ff3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523294"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a><span data-ttu-id="73cf0-102">Практическое руководство. Заливка фигуры текстурой, созданной на основе изображения</span><span class="sxs-lookup"><span data-stu-id="73cf0-102">How to: Fill a Shape with an Image Texture</span></span>
<span data-ttu-id="73cf0-103">Можно заполнить замкнутую фигуру текстуры с помощью <xref:System.Drawing.Image> класса и <xref:System.Drawing.TextureBrush> класса.</span><span class="sxs-lookup"><span data-stu-id="73cf0-103">You can fill a closed shape with a texture by using the <xref:System.Drawing.Image> class and the <xref:System.Drawing.TextureBrush> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73cf0-104">Пример</span><span class="sxs-lookup"><span data-stu-id="73cf0-104">Example</span></span>  
 <span data-ttu-id="73cf0-105">В следующем примере заполняется эллипса с изображением.</span><span class="sxs-lookup"><span data-stu-id="73cf0-105">The following example fills an ellipse with an image.</span></span> <span data-ttu-id="73cf0-106">Код создает <xref:System.Drawing.Image> объекта, а затем передает адрес объекта <xref:System.Drawing.Image> объект в качестве аргумента для <xref:System.Drawing.TextureBrush.%23ctor%2A> конструктор.</span><span class="sxs-lookup"><span data-stu-id="73cf0-106">The code constructs an <xref:System.Drawing.Image> object, and then passes the address of that <xref:System.Drawing.Image> object as an argument to a <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="73cf0-107">Третья инструкция выполняет изменение масштаба изображения, а Четвертая инструкция выполняет заливку эллипса повторяющиеся копии масштабированного изображения.</span><span class="sxs-lookup"><span data-stu-id="73cf0-107">The third statement scales the image, and the fourth statement fills the ellipse with repeated copies of the scaled image.</span></span>  
  
 <span data-ttu-id="73cf0-108">В следующем коде <xref:System.Drawing.TextureBrush.Transform%2A> свойство содержит преобразование, которое применяется к изображению перед его прорисовкой.</span><span class="sxs-lookup"><span data-stu-id="73cf0-108">In the following code, the <xref:System.Drawing.TextureBrush.Transform%2A> property contains the transformation that is applied to the image before it is drawn.</span></span> <span data-ttu-id="73cf0-109">Предположим, что исходное изображение имеет ширину 640 пикселей и высотой 480 пикселей.</span><span class="sxs-lookup"><span data-stu-id="73cf0-109">Assume that the original image has a width of 640 pixels and a height of 480 pixels.</span></span> <span data-ttu-id="73cf0-110">Преобразование уменьшает изображение до 75 × 75, задав значения горизонтальные и вертикальные масштабирования.</span><span class="sxs-lookup"><span data-stu-id="73cf0-110">The transform shrinks the image to 75×75 by setting the horizontal and vertical scaling values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73cf0-111">В следующем примере составляет 75 × 75 и размер эллипса, который составляет 150 × 250.</span><span class="sxs-lookup"><span data-stu-id="73cf0-111">In the following example, the image size is 75×75, and the ellipse size is 150×250.</span></span> <span data-ttu-id="73cf0-112">Так как изображение меньше заполняемой эллипса, выполняется мозаичное заполнение эллипса с изображением.</span><span class="sxs-lookup"><span data-stu-id="73cf0-112">Because the image is smaller than the ellipse it is filling, the ellipse is tiled with the image.</span></span> <span data-ttu-id="73cf0-113">Достигнут мозаичное заполнение означает, что изображение повторяется горизонтально и вертикально до границы фигуры.</span><span class="sxs-lookup"><span data-stu-id="73cf0-113">Tiling means that the image is repeated horizontally and vertically until the boundary of the shape is reached.</span></span> <span data-ttu-id="73cf0-114">Дополнительные сведения о мозаичное заполнение см. в разделе [как: мозаичное заполнение фигуры с изображением](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).</span><span class="sxs-lookup"><span data-stu-id="73cf0-114">For more information about tiling, see [How to: Tile a Shape with an Image](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="73cf0-115">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="73cf0-115">Compiling the Code</span></span>  
 <span data-ttu-id="73cf0-116">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="73cf0-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73cf0-117">См. также</span><span class="sxs-lookup"><span data-stu-id="73cf0-117">See Also</span></span>  
 [<span data-ttu-id="73cf0-118">Использование кисти для заливки фигур</span><span class="sxs-lookup"><span data-stu-id="73cf0-118">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
