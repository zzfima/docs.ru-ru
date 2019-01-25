---
title: Как выполнить Использование матрицы цветов для задания значений прозрачности в изображениях
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: 0e62bee55938e79d1555c463ac770f7b35be20f2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54578819"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a><span data-ttu-id="65a68-102">Как выполнить Использование матрицы цветов для задания значений прозрачности в изображениях</span><span class="sxs-lookup"><span data-stu-id="65a68-102">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>
<span data-ttu-id="65a68-103"><xref:System.Drawing.Bitmap> Класс (который наследуется от <xref:System.Drawing.Image> класс) и <xref:System.Drawing.Imaging.ImageAttributes> предоставляют функциональные возможности для получения и установки значения в пикселях.</span><span class="sxs-lookup"><span data-stu-id="65a68-103">The <xref:System.Drawing.Bitmap> class (which inherits from the <xref:System.Drawing.Image> class) and the <xref:System.Drawing.Imaging.ImageAttributes> class provide functionality for getting and setting pixel values.</span></span> <span data-ttu-id="65a68-104">Можно использовать <xref:System.Drawing.Imaging.ImageAttributes> значений для изменения альфа-канал для всего изображения, или можно вызвать <xref:System.Drawing.Bitmap.SetPixel%2A> метод <xref:System.Drawing.Bitmap> класса для изменения значений отдельных пикселей.</span><span class="sxs-lookup"><span data-stu-id="65a68-104">You can use the <xref:System.Drawing.Imaging.ImageAttributes> class to modify the alpha values for an entire image, or you can call the <xref:System.Drawing.Bitmap.SetPixel%2A> method of the <xref:System.Drawing.Bitmap> class to modify individual pixel values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65a68-105">Пример</span><span class="sxs-lookup"><span data-stu-id="65a68-105">Example</span></span>  
 <span data-ttu-id="65a68-106"><xref:System.Drawing.Imaging.ImageAttributes> Класс имеет множество свойств, которые можно использовать для изменения образов во время отрисовки.</span><span class="sxs-lookup"><span data-stu-id="65a68-106">The <xref:System.Drawing.Imaging.ImageAttributes> class has many properties that you can use to modify images during rendering.</span></span> <span data-ttu-id="65a68-107">В следующем примере <xref:System.Drawing.Imaging.ImageAttributes> объект используется для задания альфа-значения до 80 процентов от они были.</span><span class="sxs-lookup"><span data-stu-id="65a68-107">In the following example, an <xref:System.Drawing.Imaging.ImageAttributes> object is used to set all the alpha values to 80 percent of what they were.</span></span> <span data-ttu-id="65a68-108">Это делается путем инициализации матрицы цветов и альфа-канал, значение в матрице 0,8 масштабирования.</span><span class="sxs-lookup"><span data-stu-id="65a68-108">This is done by initializing a color matrix and setting the alpha scaling value in the matrix to 0.8.</span></span> <span data-ttu-id="65a68-109">Передается адрес цветовой матрице <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> метод <xref:System.Drawing.Imaging.ImageAttributes> объекта и <xref:System.Drawing.Imaging.ImageAttributes> объект передается <xref:System.Drawing.Graphics.DrawString%2A> метод <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="65a68-109">The address of the color matrix is passed to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object, and the <xref:System.Drawing.Imaging.ImageAttributes> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="65a68-110">Во время отрисовки, до 80 процентов от их первоначальных преобразуются альфа-значения в точечном рисунке.</span><span class="sxs-lookup"><span data-stu-id="65a68-110">During rendering, the alpha values in the bitmap are converted to 80 percent of what they were.</span></span> <span data-ttu-id="65a68-111">Результатом в образ, который смешивается с фоном.</span><span class="sxs-lookup"><span data-stu-id="65a68-111">This results in an image that is blended with the background.</span></span> <span data-ttu-id="65a68-112">Как показано на следующем рисунке, растровое изображение выглядит прозрачным; Появится сплошная черная линия через него.</span><span class="sxs-lookup"><span data-stu-id="65a68-112">As the following illustration shows, the bitmap image looks transparent; you can see the solid black line through it.</span></span>  
  
 <span data-ttu-id="65a68-113">![Альфа-смешение цвета с помощью матрицы](../../../../docs/framework/winforms/advanced/media/image2.png "изображение2")</span><span class="sxs-lookup"><span data-stu-id="65a68-113">![Alpha Blending Using a Matrix](../../../../docs/framework/winforms/advanced/media/image2.png "image2")</span></span>  
  
 <span data-ttu-id="65a68-114">Когда изображение на белой части в фоновом режиме, оно смешивается с белым цветом.</span><span class="sxs-lookup"><span data-stu-id="65a68-114">Where the image is over the white portion of the background, the image has been blended with the color white.</span></span> <span data-ttu-id="65a68-115">Пересечения черная линия, изображение изображения смешивается с черным цветом.</span><span class="sxs-lookup"><span data-stu-id="65a68-115">Where the image crosses the black line, the image is blended with the color black.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="65a68-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="65a68-116">Compiling the Code</span></span>  
 <span data-ttu-id="65a68-117">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="65a68-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a68-118">См. также</span><span class="sxs-lookup"><span data-stu-id="65a68-118">See also</span></span>
- [<span data-ttu-id="65a68-119">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="65a68-119">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="65a68-120">Альфа-смешение цвета для линий и заливок</span><span class="sxs-lookup"><span data-stu-id="65a68-120">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
