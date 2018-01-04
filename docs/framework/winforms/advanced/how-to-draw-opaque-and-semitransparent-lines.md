---
title: "Практическое руководство. Рисование непрозрачных и полупрозрачных линий"
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
- drawing [Windows Forms], lines
- transparency [Windows Forms], lines
- lines [Windows Forms], drawing alpha blended
- alpha blending [Windows Forms], drawing lines
ms.assetid: 8f2508af-f495-4223-b5cc-646cbbb520eb
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a298458489968cf680a9d5f935d98afb470859ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-opaque-and-semitransparent-lines"></a><span data-ttu-id="267e8-102">Практическое руководство. Рисование непрозрачных и полупрозрачных линий</span><span class="sxs-lookup"><span data-stu-id="267e8-102">How to: Draw Opaque and Semitransparent Lines</span></span>
<span data-ttu-id="267e8-103">При рисовании линии необходимо передать методу <xref:System.Drawing.Graphics.DrawLine%2A> класса <xref:System.Drawing.Graphics> объект <xref:System.Drawing.Pen>.</span><span class="sxs-lookup"><span data-stu-id="267e8-103">When you draw a line, you must pass a <xref:System.Drawing.Pen> object to the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="267e8-104">Одним из параметров конструктора <xref:System.Drawing.Pen.%23ctor%2A> является объект <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="267e8-104">One of the parameters of the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="267e8-105">Чтобы нарисовать непрозрачную линию, установите альфа-компонент цвета равным 255.</span><span class="sxs-lookup"><span data-stu-id="267e8-105">To draw an opaque line, set the alpha component of the color to 255.</span></span> <span data-ttu-id="267e8-106">Чтобы нарисовать полупрозрачную линию, установите значение альфа-компонента в диапазоне от 1 до 254.</span><span class="sxs-lookup"><span data-stu-id="267e8-106">To draw a semitransparent line, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="267e8-107">При рисовании полупрозрачной линии на некотором фоне цвет линии смешивается с цветами фона.</span><span class="sxs-lookup"><span data-stu-id="267e8-107">When you draw a semitransparent line over a background, the color of the line is blended with the colors of the background.</span></span> <span data-ttu-id="267e8-108">Альфа-компонент определяет результат смешивания цветов линии и фона. При близких к нулю значениях альфа цвета фона выделяются в большей степени, а при значениях альфа, близких к 255, в большей степени выделяется цвет линии.</span><span class="sxs-lookup"><span data-stu-id="267e8-108">The alpha component specifies how the line and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the line color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="267e8-109">Пример</span><span class="sxs-lookup"><span data-stu-id="267e8-109">Example</span></span>  
 <span data-ttu-id="267e8-110">В примере ниже рисуется растровое изображение, а затем рисуются три линии, использующие растровое изображение в качестве фона.</span><span class="sxs-lookup"><span data-stu-id="267e8-110">The following example draws a bitmap and then draws three lines that use the bitmap as a background.</span></span> <span data-ttu-id="267e8-111">Цвет первой линии имеет альфа-компонент, равный 255, поэтому она является непрозрачной.</span><span class="sxs-lookup"><span data-stu-id="267e8-111">The first line uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="267e8-112">Для второй и третьей линий используется альфа-компонент, равный 128, поэтому они являются полупрозрачными и сквозь них можно видеть фоновое изображение.</span><span class="sxs-lookup"><span data-stu-id="267e8-112">The second and third lines use an alpha component of 128, so they are semitransparent; you can see the background image through the lines.</span></span> <span data-ttu-id="267e8-113">Оператор, устанавливающий значение свойства <xref:System.Drawing.Graphics.CompositingQuality%2A>, указывает, что смешивание цветов для третьей линии должно совмещаться с гамма-коррекцией.</span><span class="sxs-lookup"><span data-stu-id="267e8-113">The statement that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third line to be done in conjunction with gamma correction.</span></span>  
  
 <span data-ttu-id="267e8-114">На рисунке ниже показан результат выполнения следующего кода.</span><span class="sxs-lookup"><span data-stu-id="267e8-114">The following illustration shows the output of the following code.</span></span>  
  
 <span data-ttu-id="267e8-115">![Непрозрачный и частично прозрачный](../../../../docs/framework/winforms/advanced/media/compqualline.png "compqualline")</span><span class="sxs-lookup"><span data-stu-id="267e8-115">![Opaque and Semitransparent](../../../../docs/framework/winforms/advanced/media/compqualline.png "compqualline")</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.AlphaBlending#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="267e8-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="267e8-116">Compiling the Code</span></span>  
 <span data-ttu-id="267e8-117">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="267e8-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="267e8-118">См. также</span><span class="sxs-lookup"><span data-stu-id="267e8-118">See Also</span></span>  
 [<span data-ttu-id="267e8-119">Альфа-смешение цвета для линий и заливок</span><span class="sxs-lookup"><span data-stu-id="267e8-119">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)  
 [<span data-ttu-id="267e8-120">Практическое руководство. Установка степени прозрачности фона элемента управления</span><span class="sxs-lookup"><span data-stu-id="267e8-120">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 [<span data-ttu-id="267e8-121">Практическое руководство. Рисование непрозрачными и полупрозрачными кистями</span><span class="sxs-lookup"><span data-stu-id="267e8-121">How to: Draw with Opaque and Semitransparent Brushes</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)
