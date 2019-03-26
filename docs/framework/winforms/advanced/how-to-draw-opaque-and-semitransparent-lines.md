---
title: Практическое руководство. Рисование непрозрачных и полупрозрачных линий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- transparency [Windows Forms], lines
- lines [Windows Forms], drawing alpha blended
- alpha blending [Windows Forms], drawing lines
ms.assetid: 8f2508af-f495-4223-b5cc-646cbbb520eb
ms.openlocfilehash: 210916bbaf437d8f71b07e8107eb0cdc0989ea42
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2019
ms.locfileid: "58465624"
---
# <a name="how-to-draw-opaque-and-semitransparent-lines"></a><span data-ttu-id="d2f74-102">Практическое руководство. Рисование непрозрачных и полупрозрачных линий</span><span class="sxs-lookup"><span data-stu-id="d2f74-102">How to: Draw Opaque and Semitransparent Lines</span></span>
<span data-ttu-id="d2f74-103">При рисовании линии необходимо передать методу <xref:System.Drawing.Graphics.DrawLine%2A> класса <xref:System.Drawing.Graphics> объект <xref:System.Drawing.Pen>.</span><span class="sxs-lookup"><span data-stu-id="d2f74-103">When you draw a line, you must pass a <xref:System.Drawing.Pen> object to the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="d2f74-104">Одним из параметров конструктора <xref:System.Drawing.Pen.%23ctor%2A> является объект <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="d2f74-104">One of the parameters of the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="d2f74-105">Чтобы нарисовать непрозрачную линию, установите альфа-компонент цвета равным 255.</span><span class="sxs-lookup"><span data-stu-id="d2f74-105">To draw an opaque line, set the alpha component of the color to 255.</span></span> <span data-ttu-id="d2f74-106">Чтобы нарисовать полупрозрачную линию, установите значение альфа-компонента в диапазоне от 1 до 254.</span><span class="sxs-lookup"><span data-stu-id="d2f74-106">To draw a semitransparent line, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="d2f74-107">При рисовании полупрозрачной линии на некотором фоне цвет линии смешивается с цветами фона.</span><span class="sxs-lookup"><span data-stu-id="d2f74-107">When you draw a semitransparent line over a background, the color of the line is blended with the colors of the background.</span></span> <span data-ttu-id="d2f74-108">Альфа-компонент определяет результат смешивания цветов линии и фона. При близких к нулю значениях альфа цвета фона выделяются в большей степени, а при значениях альфа, близких к 255, в большей степени выделяется цвет линии.</span><span class="sxs-lookup"><span data-stu-id="d2f74-108">The alpha component specifies how the line and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the line color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2f74-109">Пример</span><span class="sxs-lookup"><span data-stu-id="d2f74-109">Example</span></span>  
 <span data-ttu-id="d2f74-110">В примере ниже рисуется растровое изображение, а затем рисуются три линии, использующие растровое изображение в качестве фона.</span><span class="sxs-lookup"><span data-stu-id="d2f74-110">The following example draws a bitmap and then draws three lines that use the bitmap as a background.</span></span> <span data-ttu-id="d2f74-111">Цвет первой линии имеет альфа-компонент, равный 255, поэтому она является непрозрачной.</span><span class="sxs-lookup"><span data-stu-id="d2f74-111">The first line uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="d2f74-112">Для второй и третьей линий используется альфа-компонент, равный 128, поэтому они являются полупрозрачными и сквозь них можно видеть фоновое изображение.</span><span class="sxs-lookup"><span data-stu-id="d2f74-112">The second and third lines use an alpha component of 128, so they are semitransparent; you can see the background image through the lines.</span></span> <span data-ttu-id="d2f74-113">Оператор, устанавливающий значение свойства <xref:System.Drawing.Graphics.CompositingQuality%2A>, указывает, что смешивание цветов для третьей линии должно совмещаться с гамма-коррекцией.</span><span class="sxs-lookup"><span data-stu-id="d2f74-113">The statement that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third line to be done in conjunction with gamma correction.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.AlphaBlending#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#11)]  
  
 <span data-ttu-id="d2f74-114">На следующем рисунке показан вывода следующего кода:</span><span class="sxs-lookup"><span data-stu-id="d2f74-114">The following illustration shows the output of the following code:</span></span>  
  
 ![Рисунок, показывающий непрозрачных и полупрозрачных выходных данных](./media/how-to-draw-opaque-and-semitransparent-lines/opaque-semitransparent-lines.png)  

## <a name="compiling-the-code"></a><span data-ttu-id="d2f74-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="d2f74-116">Compiling the Code</span></span>  
 <span data-ttu-id="d2f74-117">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром обработчика события <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="d2f74-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2f74-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d2f74-118">See also</span></span>
- [<span data-ttu-id="d2f74-119">Альфа-смешение цвета для линий и заливок</span><span class="sxs-lookup"><span data-stu-id="d2f74-119">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
- [<span data-ttu-id="d2f74-120">Практическое руководство. Установка степени прозрачности фона элемента управления</span><span class="sxs-lookup"><span data-stu-id="d2f74-120">How to: Give Your Control a Transparent Background</span></span>](../controls/how-to-give-your-control-a-transparent-background.md)
- [<span data-ttu-id="d2f74-121">Практическое руководство. Рисование непрозрачными и полупрозрачными кистями</span><span class="sxs-lookup"><span data-stu-id="d2f74-121">How to: Draw with Opaque and Semitransparent Brushes</span></span>](how-to-draw-with-opaque-and-semitransparent-brushes.md)
