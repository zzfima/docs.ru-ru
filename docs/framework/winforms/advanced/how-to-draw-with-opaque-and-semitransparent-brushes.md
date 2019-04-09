---
title: Практическое руководство. Рисование непрозрачными и полупрозрачными кистями
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- semi-transparent shapes [Windows Forms], drawing
- transparency [Windows Forms], semi-transparent shapes
- alpha blending [Windows Forms], brush
- brushes [Windows Forms], using semi-transparent
ms.assetid: a4f6f6b8-3bc8-440a-84af-d62ef0f8ff40
ms.openlocfilehash: a302b8bf978afcead5768fadeb6336c1ece986ec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100936"
---
# <a name="how-to-draw-with-opaque-and-semitransparent-brushes"></a><span data-ttu-id="2ebb1-102">Практическое руководство. Рисование непрозрачными и полупрозрачными кистями</span><span class="sxs-lookup"><span data-stu-id="2ebb1-102">How to: Draw with Opaque and Semitransparent Brushes</span></span>
<span data-ttu-id="2ebb1-103">При заливке формы необходимо передать объект <xref:System.Drawing.Brush> одному из методов заливки класса <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="2ebb1-103">When you fill a shape, you must pass a <xref:System.Drawing.Brush> object to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="2ebb1-104">Единственным параметром конструктора <xref:System.Drawing.SolidBrush.%23ctor%2A> является объект <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="2ebb1-104">The one parameter of the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="2ebb1-105">Чтобы залить непрозрачную фигуру, следует установить значение альфа-компонента цвета в 255.</span><span class="sxs-lookup"><span data-stu-id="2ebb1-105">To fill an opaque shape, set the alpha component of the color to 255.</span></span> <span data-ttu-id="2ebb1-106">Чтобы залить полупрозрачную фигуру, установите значение альфа-компонента в интервале от 1 до 254.</span><span class="sxs-lookup"><span data-stu-id="2ebb1-106">To fill a semitransparent shape, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="2ebb1-107">При заполнении полупрозрачной фигуры цвет фигуры смешивается с цветами фона.</span><span class="sxs-lookup"><span data-stu-id="2ebb1-107">When you fill a semitransparent shape, the color of the shape is blended with the colors of the background.</span></span> <span data-ttu-id="2ebb1-108">Альфа-компонент определяет степень смешивания цветов фигуры и фона. При значениях альфа, близких к 0, цвет фона имеет больший приоритет, при значениях альфа, близких к 255, больший приоритет имеет цвет фигуры.</span><span class="sxs-lookup"><span data-stu-id="2ebb1-108">The alpha component specifies how the shape and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the shape color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ebb1-109">Пример</span><span class="sxs-lookup"><span data-stu-id="2ebb1-109">Example</span></span>  
 <span data-ttu-id="2ebb1-110">В следующем примере рисуется растровое изображение, а затем осуществляется заливка трех эллипсов, перекрывающих растровое изображение.</span><span class="sxs-lookup"><span data-stu-id="2ebb1-110">The following example draws a bitmap and then fills three ellipses that overlap the bitmap.</span></span> <span data-ttu-id="2ebb1-111">Для первого эллипса используется значение альфа-компонента, равное 255, поэтому он непрозрачен.</span><span class="sxs-lookup"><span data-stu-id="2ebb1-111">The first ellipse uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="2ebb1-112">Для второго и третьего эллипсов используется значение альфа-компонента, равное 128, поэтому они полупрозрачные и сквозь эллипсы видно фоновое изображение.</span><span class="sxs-lookup"><span data-stu-id="2ebb1-112">The second and third ellipses use an alpha component of 128, so they are semitransparent; you can see the background image through the ellipses.</span></span> <span data-ttu-id="2ebb1-113">Вызов, который устанавливает свойство <xref:System.Drawing.Graphics.CompositingQuality%2A>, вынуждает выполнить наложение для третьего эллипса совместно с гамма-коррекцией.</span><span class="sxs-lookup"><span data-stu-id="2ebb1-113">The call that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third ellipse to be done in conjunction with gamma correction.</span></span>  

 [!code-csharp[System.Drawing.AlphaBlending#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.AlphaBlending#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#31)]  

 <span data-ttu-id="2ebb1-114">На следующем рисунке показан вывода следующего кода:</span><span class="sxs-lookup"><span data-stu-id="2ebb1-114">The following illustration shows the output of the following code:</span></span> 
  
 ![Рисунок, показывающий непрозрачных и полупрозрачных выходных данных.](./media/how-to-draw-with-opaque-and-semitransparent-brushes/compositingquality-ellipse-semitransparent.png)  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2ebb1-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="2ebb1-116">Compiling the Code</span></span>  
 <span data-ttu-id="2ebb1-117">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs>`e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="2ebb1-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ebb1-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2ebb1-118">See also</span></span>

- [<span data-ttu-id="2ebb1-119">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ebb1-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="2ebb1-120">Альфа-смешение цвета для линий и заливок</span><span class="sxs-lookup"><span data-stu-id="2ebb1-120">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
- [<span data-ttu-id="2ebb1-121">Практическое руководство. Установка степени прозрачности фона элемента управления</span><span class="sxs-lookup"><span data-stu-id="2ebb1-121">How to: Give Your Control a Transparent Background</span></span>](../controls/how-to-give-your-control-a-transparent-background.md)
- [<span data-ttu-id="2ebb1-122">Практическое руководство. Рисование непрозрачных и полупрозрачных линий</span><span class="sxs-lookup"><span data-stu-id="2ebb1-122">How to: Draw Opaque and Semitransparent Lines</span></span>](how-to-draw-opaque-and-semitransparent-lines.md)
