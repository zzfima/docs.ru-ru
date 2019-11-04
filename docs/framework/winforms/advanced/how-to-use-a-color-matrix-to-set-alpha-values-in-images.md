---
title: Практическое руководство. Использование матрицы цветов для задания значений прозрачности в изображениях
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
ms.openlocfilehash: 73e820845d040856a0ae367da8b9371ad6afa142
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423744"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a><span data-ttu-id="86e54-102">Практическое руководство. Использование матрицы цветов для задания значений прозрачности в изображениях</span><span class="sxs-lookup"><span data-stu-id="86e54-102">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>
<span data-ttu-id="86e54-103">Класс <xref:System.Drawing.Bitmap> (который наследует от класса <xref:System.Drawing.Image>) и класс <xref:System.Drawing.Imaging.ImageAttributes> предоставляют функциональные возможности для получения и установки значений пикселей.</span><span class="sxs-lookup"><span data-stu-id="86e54-103">The <xref:System.Drawing.Bitmap> class (which inherits from the <xref:System.Drawing.Image> class) and the <xref:System.Drawing.Imaging.ImageAttributes> class provide functionality for getting and setting pixel values.</span></span> <span data-ttu-id="86e54-104">Можно использовать класс <xref:System.Drawing.Imaging.ImageAttributes>, чтобы изменить альфа-значения для всего изображения, или можно вызвать метод <xref:System.Drawing.Bitmap.SetPixel%2A> класса <xref:System.Drawing.Bitmap>, чтобы изменить отдельные значения пикселей.</span><span class="sxs-lookup"><span data-stu-id="86e54-104">You can use the <xref:System.Drawing.Imaging.ImageAttributes> class to modify the alpha values for an entire image, or you can call the <xref:System.Drawing.Bitmap.SetPixel%2A> method of the <xref:System.Drawing.Bitmap> class to modify individual pixel values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86e54-105">Пример</span><span class="sxs-lookup"><span data-stu-id="86e54-105">Example</span></span>  
 <span data-ttu-id="86e54-106">Класс <xref:System.Drawing.Imaging.ImageAttributes> имеет множество свойств, которые можно использовать для изменения изображений во время подготовки к просмотру.</span><span class="sxs-lookup"><span data-stu-id="86e54-106">The <xref:System.Drawing.Imaging.ImageAttributes> class has many properties that you can use to modify images during rendering.</span></span> <span data-ttu-id="86e54-107">В следующем примере объект <xref:System.Drawing.Imaging.ImageAttributes> используется для установки всех альфа-значений равными 80 процентам от того, что они имели.</span><span class="sxs-lookup"><span data-stu-id="86e54-107">In the following example, an <xref:System.Drawing.Imaging.ImageAttributes> object is used to set all the alpha values to 80 percent of what they were.</span></span> <span data-ttu-id="86e54-108">Это делается путем инициализации матрицы цветов и установки значения масштабирования альфа в матрице в 0,8.</span><span class="sxs-lookup"><span data-stu-id="86e54-108">This is done by initializing a color matrix and setting the alpha scaling value in the matrix to 0.8.</span></span> <span data-ttu-id="86e54-109">Адрес матрицы цветов передается методу <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> объекта <xref:System.Drawing.Imaging.ImageAttributes>, а объект <xref:System.Drawing.Imaging.ImageAttributes> передается методу <xref:System.Drawing.Graphics.DrawString%2A> объекта <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="86e54-109">The address of the color matrix is passed to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object, and the <xref:System.Drawing.Imaging.ImageAttributes> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="86e54-110">Во время отрисовки альфа-значения в точечном рисунке преобразуются в 80 процентов от того, что они имели.</span><span class="sxs-lookup"><span data-stu-id="86e54-110">During rendering, the alpha values in the bitmap are converted to 80 percent of what they were.</span></span> <span data-ttu-id="86e54-111">В результате получается изображение, которое смешивается с фоном.</span><span class="sxs-lookup"><span data-stu-id="86e54-111">This results in an image that is blended with the background.</span></span> <span data-ttu-id="86e54-112">Как показано на рисунке ниже, точечный рисунок выглядит прозрачным. можно увидеть сплошную черную линию.</span><span class="sxs-lookup"><span data-stu-id="86e54-112">As the following illustration shows, the bitmap image looks transparent; you can see the solid black line through it.</span></span>  
  
 <span data-ttu-id="86e54-113">![Снимок экрана альфа-смешения с использованием матрицы.](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "изображение 2")</span><span class="sxs-lookup"><span data-stu-id="86e54-113">![Screenshot of alpha blending using a matrix.](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "image2")</span></span>  
  
 <span data-ttu-id="86e54-114">Когда изображение находится над белой частью фона, изображение смешивается с белым цветом.</span><span class="sxs-lookup"><span data-stu-id="86e54-114">Where the image is over the white portion of the background, the image has been blended with the color white.</span></span> <span data-ttu-id="86e54-115">Когда изображение пересекает черную линию, изображение смешивается с черным цветом.</span><span class="sxs-lookup"><span data-stu-id="86e54-115">Where the image crosses the black line, the image is blended with the color black.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="86e54-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="86e54-116">Compiling the Code</span></span>  
 <span data-ttu-id="86e54-117">Предыдущий пример предназначен для использования с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="86e54-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86e54-118">См. также</span><span class="sxs-lookup"><span data-stu-id="86e54-118">See also</span></span>

- [<span data-ttu-id="86e54-119">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="86e54-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="86e54-120">Альфа-смешение цвета для линий и заливок</span><span class="sxs-lookup"><span data-stu-id="86e54-120">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
