---
title: Практическое руководство. Вращать цвета
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: d3fa49e6129c93df93378fb2b607a87a5a0be087
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58125893"
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="4bb3f-102">Практическое руководство. Вращать цвета</span><span class="sxs-lookup"><span data-stu-id="4bb3f-102">How to: Rotate Colors</span></span>
<span data-ttu-id="4bb3f-103">Поворот в четырехмерный цветовом пространстве сложно представить.</span><span class="sxs-lookup"><span data-stu-id="4bb3f-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="4bb3f-104">Мы можно упростить, если договориться сохранять один из компонентов цвета неизменным.</span><span class="sxs-lookup"><span data-stu-id="4bb3f-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="4bb3f-105">Предположим, что требуется сохранить альфа-компонент, составляет 1 (полностью непрозрачный).</span><span class="sxs-lookup"><span data-stu-id="4bb3f-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="4bb3f-106">Затем мы можете визуализировать трехмерное цветовое пространство с осями красного, зеленого и синего, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="4bb3f-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 ![Рисунок, показывающий поворота оси красного, зеленого и синего.](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 <span data-ttu-id="4bb3f-108">Цвет может рассматриваться как точка в трехмерном пространстве.</span><span class="sxs-lookup"><span data-stu-id="4bb3f-108">A color can be thought of as a point in 3-D space.</span></span> <span data-ttu-id="4bb3f-109">Например точка (1, 0, 0) в пространстве представляет красный цвет, а точки (0, 1, 0) в пространстве представляет зеленый цвет.</span><span class="sxs-lookup"><span data-stu-id="4bb3f-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="4bb3f-110">Ниже показан последствия поворот цвета (1, 0, 0) через угол 60 градусов в плоскости красный-зеленый.</span><span class="sxs-lookup"><span data-stu-id="4bb3f-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="4bb3f-111">Поворот в плоскости плоскости красный-зеленый может рассматриваться как поворот относительно оси синий.</span><span class="sxs-lookup"><span data-stu-id="4bb3f-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 ![Рисунок, показывающий Поворот относительно оси синий.](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 <span data-ttu-id="4bb3f-113">Ниже показано, как создать матрицу цветов для выполнения поворотов о каждой из трех осей координат (красный, зеленый, синий):</span><span class="sxs-lookup"><span data-stu-id="4bb3f-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue):</span></span>  
  
 ![Инициализируйте матрицы цветов для выполнения поворотов относительно трем осям.](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a><span data-ttu-id="4bb3f-115">Пример</span><span class="sxs-lookup"><span data-stu-id="4bb3f-115">Example</span></span>  
 <span data-ttu-id="4bb3f-116">В следующем примере выполняются изображения, только один цвет (1 0, 0.6) и применяет поворот на 60 градусов относительно оси синий.</span><span class="sxs-lookup"><span data-stu-id="4bb3f-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="4bb3f-117">Угол поворота заметает плоскость, параллельную плоскости красный зеленый.</span><span class="sxs-lookup"><span data-stu-id="4bb3f-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="4bb3f-118">На следующем рисунке показано исходное изображение в левой части и преобразованное изображение справа:</span><span class="sxs-lookup"><span data-stu-id="4bb3f-118">The following illustration shows the original image on the left and the color-rotated image on the right:</span></span>  
  
 ![Иллюстрацию исходное изображение, преобразованное изображение.](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 <span data-ttu-id="4bb3f-120">На следующем рисунке показан поворот цвета, выполняемые в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="4bb3f-120">The following illustration shows a visualization of the color rotation performed in the following code:</span></span>
  
 ![Рисунок, показывающий визуализации поворот цветов.](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4bb3f-122">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="4bb3f-122">Compiling the Code</span></span>  
 <span data-ttu-id="4bb3f-123">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром обработчика события <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="4bb3f-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="4bb3f-124">Замените `RotationInput.bmp` в вашей системе путь и имя файла изображения.</span><span class="sxs-lookup"><span data-stu-id="4bb3f-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bb3f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="4bb3f-125">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="4bb3f-126">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4bb3f-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="4bb3f-127">перекрашивание изображений</span><span class="sxs-lookup"><span data-stu-id="4bb3f-127">Recoloring Images</span></span>](recoloring-images.md)
