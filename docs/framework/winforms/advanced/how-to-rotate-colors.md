---
title: "Практическое руководство. Поворот цветов"
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
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c82a77ff3d643afc0ddd542868a96c17d31ef336
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="12142-102">Практическое руководство. Поворот цветов</span><span class="sxs-lookup"><span data-stu-id="12142-102">How to: Rotate Colors</span></span>
<span data-ttu-id="12142-103">Угол поворота в четырехмерный цветовое пространство сложно визуализировать.</span><span class="sxs-lookup"><span data-stu-id="12142-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="12142-104">Мы можно упростить, если договориться сохранять один из компонентов цвета неизменным.</span><span class="sxs-lookup"><span data-stu-id="12142-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="12142-105">Предположим, нам требуется сохранить альфа-компонент неизменным и равным 1 (полная непрозрачность).</span><span class="sxs-lookup"><span data-stu-id="12142-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="12142-106">Тогда можно представить трехмерное цветовое пространство с осями красного, зеленого и синего как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="12142-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="12142-107">![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")</span><span class="sxs-lookup"><span data-stu-id="12142-107">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")</span></span>  
  
 <span data-ttu-id="12142-108">Цвет может рассматриваться как точка объема пространства.</span><span class="sxs-lookup"><span data-stu-id="12142-108">A color can be thought of as a point in 3-D space.</span></span> <span data-ttu-id="12142-109">Например точка (1, 0, 0) в пространстве представляет красный цвет, а точки (0, 1, 0) в пространстве представляет зеленый цвет.</span><span class="sxs-lookup"><span data-stu-id="12142-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="12142-110">На следующем рисунке значит поворот цвета (1, 0, 0) через угол 60 градусов в плоскости красный-зеленый.</span><span class="sxs-lookup"><span data-stu-id="12142-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="12142-111">Поворот в плоскости плоскости красный-зеленый может рассматриваться как поворот относительно оси синий.</span><span class="sxs-lookup"><span data-stu-id="12142-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 <span data-ttu-id="12142-112">![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")</span><span class="sxs-lookup"><span data-stu-id="12142-112">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")</span></span>  
  
 <span data-ttu-id="12142-113">Ниже показано, как создать матрицу цветов для выполнения поворотов относительно каждой из трех координатных осей (красный, зеленый, синий).</span><span class="sxs-lookup"><span data-stu-id="12142-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue).</span></span>  
  
 <span data-ttu-id="12142-114">![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")</span><span class="sxs-lookup"><span data-stu-id="12142-114">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")</span></span>  
  
## <a name="example"></a><span data-ttu-id="12142-115">Пример</span><span class="sxs-lookup"><span data-stu-id="12142-115">Example</span></span>  
 <span data-ttu-id="12142-116">В следующем примере выполняются изображения, содержащему только один цвет (1, 0, 0,6), применяется поворот на 60 градусов относительно оси синий.</span><span class="sxs-lookup"><span data-stu-id="12142-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="12142-117">Угол поворота заметает плоскость, параллельную плоскости красный зеленый.</span><span class="sxs-lookup"><span data-stu-id="12142-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="12142-118">На следующем рисунке исходное изображение в левой части и преобразованное изображение справа.</span><span class="sxs-lookup"><span data-stu-id="12142-118">The following illustration shows the original image on the left and the color-rotated image on the right.</span></span>  
  
 <span data-ttu-id="12142-119">![Вращать цвета](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")</span><span class="sxs-lookup"><span data-stu-id="12142-119">![Rotate Colors](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")</span></span>  
  
 <span data-ttu-id="12142-120">Следующий рисунок иллюстрирует поворот цветов, выполняемый в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="12142-120">The following illustration shows a visualization of the color rotation performed in the following code.</span></span>  
  
 <span data-ttu-id="12142-121">![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")</span><span class="sxs-lookup"><span data-stu-id="12142-121">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")</span></span>  
  
 [!code-csharp[System.Drawing.RotateColors#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="12142-122">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="12142-122">Compiling the Code</span></span>  
 <span data-ttu-id="12142-123">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs>`e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="12142-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="12142-124">Замените `RotationInput.bmp` в вашей системе путь и имя файла изображения.</span><span class="sxs-lookup"><span data-stu-id="12142-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12142-125">См. также</span><span class="sxs-lookup"><span data-stu-id="12142-125">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="12142-126">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="12142-126">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="12142-127">перекрашивание изображений</span><span class="sxs-lookup"><span data-stu-id="12142-127">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
