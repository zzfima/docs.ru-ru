---
title: Практическое руководство. Поворот цветов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 8d2717dd7b819e963126072279b361fda02188bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111339"
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="f8830-102">Практическое руководство. Поворот цветов</span><span class="sxs-lookup"><span data-stu-id="f8830-102">How to: Rotate Colors</span></span>
<span data-ttu-id="f8830-103">Вращение в четырехмерном цветовом пространстве трудно визуализировать.</span><span class="sxs-lookup"><span data-stu-id="f8830-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="f8830-104">Мы можем упростить визуализацию вращения, согласившись сохранить один из компонентов цвета фиксированной.</span><span class="sxs-lookup"><span data-stu-id="f8830-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="f8830-105">Предположим, мы согласны сохранить альфа-компонент фиксированной на 1 (полностью непрозрачный).</span><span class="sxs-lookup"><span data-stu-id="f8830-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="f8830-106">Затем мы можем визуализировать трехмерное цветовое пространство с красными, зелеными и синими топорами, как показано на следующей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="f8830-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 ![Иллюстрация, которая показывает вращение с красными, зелеными и синими осями.](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 <span data-ttu-id="f8830-108">Цвет можно рассматривать как точку в 3D пространстве.</span><span class="sxs-lookup"><span data-stu-id="f8830-108">A color can be thought of as a point in 3D space.</span></span> <span data-ttu-id="f8830-109">Например, точка (1, 0, 0) в пространстве представляет красный цвет, а точка (0, 1, 0) в пространстве представляет зеленый цвет.</span><span class="sxs-lookup"><span data-stu-id="f8830-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="f8830-110">На следующей иллюстрации показано, что значит вращать цвет (1, 0, 0) под углом 60 градусов в красно-зеленой плоскости.</span><span class="sxs-lookup"><span data-stu-id="f8830-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="f8830-111">Вращение в плоскости параллельно красно-зеленой плоскости можно рассматривать как вращение вокруг синей оси.</span><span class="sxs-lookup"><span data-stu-id="f8830-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 ![Иллюстрация, которая показывает вращение о синей оси.](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 <span data-ttu-id="f8830-113">На следующей иллюстрации показано, как инициализировать цветовую матрицу для выполнения вращений о каждой из трех осей координат (красный, зеленый, синий):</span><span class="sxs-lookup"><span data-stu-id="f8830-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue):</span></span>  
  
 ![Инициализируем цветовую матрицу для выполнения вращений около трех осей.](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a><span data-ttu-id="f8830-115">Пример</span><span class="sxs-lookup"><span data-stu-id="f8830-115">Example</span></span>  
 <span data-ttu-id="f8830-116">Следующий пример приводит изображение, которое является одним цветом (1, 0, 0,6) и применяет 60-градусное вращение вокруг синей оси.</span><span class="sxs-lookup"><span data-stu-id="f8830-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="f8830-117">Угол вращения сметен в плоскости, параллельной красно-зеленой плоскости.</span><span class="sxs-lookup"><span data-stu-id="f8830-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="f8830-118">На следующей иллюстрации показано исходное изображение слева и повернутое в цвет изображение справа:</span><span class="sxs-lookup"><span data-stu-id="f8830-118">The following illustration shows the original image on the left and the color-rotated image on the right:</span></span>  
  
 ![Иллюстрация, которая показывает исходное изображение и цвет-повернутое изображение.](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 <span data-ttu-id="f8830-120">Следующая иллюстрация показывает визуализацию вращения цвета, выполненную в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="f8830-120">The following illustration shows a visualization of the color rotation performed in the following code:</span></span>
  
 ![Иллюстрация, которая показывает визуализацию вращения цвета.](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f8830-122">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f8830-122">Compiling the Code</span></span>  
 <span data-ttu-id="f8830-123">Предыдущий пример предназначен для использования с формами Windows, и он требует, <xref:System.Windows.Forms.PaintEventArgs> `e`который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="f8830-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="f8830-124">Замените `RotationInput.bmp` имя файла изображения и путь, действительный в вашей системе.</span><span class="sxs-lookup"><span data-stu-id="f8830-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8830-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f8830-125">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="f8830-126">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8830-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="f8830-127">Перекрашивание изображений</span><span class="sxs-lookup"><span data-stu-id="f8830-127">Recoloring Images</span></span>](recoloring-images.md)
