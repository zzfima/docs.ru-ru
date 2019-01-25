---
title: Как выполнить Вращать цвета
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 6c4f41504911e94673707d99d804fad5b228599e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503086"
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="0dee6-102">Как выполнить Вращать цвета</span><span class="sxs-lookup"><span data-stu-id="0dee6-102">How to: Rotate Colors</span></span>
<span data-ttu-id="0dee6-103">Поворот в четырехмерный цветовом пространстве сложно представить.</span><span class="sxs-lookup"><span data-stu-id="0dee6-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="0dee6-104">Мы можно упростить, если договориться сохранять один из компонентов цвета неизменным.</span><span class="sxs-lookup"><span data-stu-id="0dee6-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="0dee6-105">Предположим, что требуется сохранить альфа-компонент, составляет 1 (полностью непрозрачный).</span><span class="sxs-lookup"><span data-stu-id="0dee6-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="0dee6-106">Затем мы можете визуализировать трехмерное цветовое пространство с осями красного, зеленого и синего, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="0dee6-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="0dee6-107">![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")</span><span class="sxs-lookup"><span data-stu-id="0dee6-107">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")</span></span>  
  
 <span data-ttu-id="0dee6-108">Цвет может рассматриваться как точка в трехмерном пространстве.</span><span class="sxs-lookup"><span data-stu-id="0dee6-108">A color can be thought of as a point in 3-D space.</span></span> <span data-ttu-id="0dee6-109">Например точка (1, 0, 0) в пространстве представляет красный цвет, а точки (0, 1, 0) в пространстве представляет зеленый цвет.</span><span class="sxs-lookup"><span data-stu-id="0dee6-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="0dee6-110">Ниже показан последствия поворот цвета (1, 0, 0) через угол 60 градусов в плоскости красный-зеленый.</span><span class="sxs-lookup"><span data-stu-id="0dee6-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="0dee6-111">Поворот в плоскости плоскости красный-зеленый может рассматриваться как поворот относительно оси синий.</span><span class="sxs-lookup"><span data-stu-id="0dee6-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 <span data-ttu-id="0dee6-112">![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")</span><span class="sxs-lookup"><span data-stu-id="0dee6-112">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")</span></span>  
  
 <span data-ttu-id="0dee6-113">Ниже показано, как создать матрицу цветов для выполнения поворотов о каждой из трех осей координат (красный, зеленый, синий).</span><span class="sxs-lookup"><span data-stu-id="0dee6-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue).</span></span>  
  
 <span data-ttu-id="0dee6-114">![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")</span><span class="sxs-lookup"><span data-stu-id="0dee6-114">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")</span></span>  
  
## <a name="example"></a><span data-ttu-id="0dee6-115">Пример</span><span class="sxs-lookup"><span data-stu-id="0dee6-115">Example</span></span>  
 <span data-ttu-id="0dee6-116">В следующем примере выполняются изображения, только один цвет (1 0, 0.6) и применяет поворот на 60 градусов относительно оси синий.</span><span class="sxs-lookup"><span data-stu-id="0dee6-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="0dee6-117">Угол поворота заметает плоскость, параллельную плоскости красный зеленый.</span><span class="sxs-lookup"><span data-stu-id="0dee6-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="0dee6-118">Ниже показан исходного изображения в левой части и изображение преобразованное в правой части.</span><span class="sxs-lookup"><span data-stu-id="0dee6-118">The following illustration shows the original image on the left and the color-rotated image on the right.</span></span>  
  
 <span data-ttu-id="0dee6-119">![Поворот цветов](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")</span><span class="sxs-lookup"><span data-stu-id="0dee6-119">![Rotate Colors](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")</span></span>  
  
 <span data-ttu-id="0dee6-120">Следующий рисунок иллюстрирует поворот цветов, выполняемый в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0dee6-120">The following illustration shows a visualization of the color rotation performed in the following code.</span></span>  
  
 <span data-ttu-id="0dee6-121">![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")</span><span class="sxs-lookup"><span data-stu-id="0dee6-121">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")</span></span>  
  
 [!code-csharp[System.Drawing.RotateColors#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0dee6-122">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0dee6-122">Compiling the Code</span></span>  
 <span data-ttu-id="0dee6-123">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="0dee6-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="0dee6-124">Замените `RotationInput.bmp` в вашей системе путь и имя файла изображения.</span><span class="sxs-lookup"><span data-stu-id="0dee6-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dee6-125">См. также</span><span class="sxs-lookup"><span data-stu-id="0dee6-125">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="0dee6-126">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0dee6-126">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="0dee6-127">перекрашивание изображений</span><span class="sxs-lookup"><span data-stu-id="0dee6-127">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
