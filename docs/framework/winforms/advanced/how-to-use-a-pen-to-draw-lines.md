---
title: "Практическое руководство. Рисование линий с помощью пера"
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
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 481200d1383fd6cc5e95379823af651c78275cb5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-pen-to-draw-lines"></a><span data-ttu-id="a8978-102">Практическое руководство. Рисование линий с помощью пера</span><span class="sxs-lookup"><span data-stu-id="a8978-102">How to: Use a Pen to Draw Lines</span></span>
<span data-ttu-id="a8978-103">Чтобы нарисовать линии, нужно <xref:System.Drawing.Graphics> объекта и <xref:System.Drawing.Pen> объекта.</span><span class="sxs-lookup"><span data-stu-id="a8978-103">To draw lines, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="a8978-104"><xref:System.Drawing.Graphics> Объект предоставляет <xref:System.Drawing.Graphics.DrawLine%2A> метода и <xref:System.Drawing.Pen> объект сохраняет функции строки, таких как цвет и ширину.</span><span class="sxs-lookup"><span data-stu-id="a8978-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawLine%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8978-105">Пример</span><span class="sxs-lookup"><span data-stu-id="a8978-105">Example</span></span>  
 <span data-ttu-id="a8978-106">В следующем примере рисуется строку из (20, 10) для (300, 100).</span><span class="sxs-lookup"><span data-stu-id="a8978-106">The following example draws a line from (20, 10) to (300, 100).</span></span> <span data-ttu-id="a8978-107">В первом операторе используется <xref:System.Drawing.Pen.%23ctor%2A> конструктор класса для создания черного пера.</span><span class="sxs-lookup"><span data-stu-id="a8978-107">The first statement uses the <xref:System.Drawing.Pen.%23ctor%2A> class constructor to create a black pen.</span></span> <span data-ttu-id="a8978-108">Один аргумент, передаваемый <xref:System.Drawing.Pen.%23ctor%2A> конструктор является <xref:System.Drawing.Color> объектом, созданным с помощью <xref:System.Drawing.Color.FromArgb%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="a8978-108">The one argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object created with the <xref:System.Drawing.Color.FromArgb%2A> method.</span></span> <span data-ttu-id="a8978-109">Значения, используемые для создания <xref:System.Drawing.Color> объекта — (255, 0, 0, 0), соответствуют альфа, красного, зеленого и синего компонентов цвета.</span><span class="sxs-lookup"><span data-stu-id="a8978-109">The values used to create the <xref:System.Drawing.Color> object — (255, 0, 0, 0) — correspond to the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="a8978-110">Эти значения определяют непрозрачное черного пера.</span><span class="sxs-lookup"><span data-stu-id="a8978-110">These values define an opaque black pen.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a8978-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a8978-111">Compiling the Code</span></span>  
 <span data-ttu-id="a8978-112">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs>`e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="a8978-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8978-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a8978-113">See Also</span></span>  
 <xref:System.Drawing.Pen>  
 [<span data-ttu-id="a8978-114">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="a8978-114">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="a8978-115">Перья, линии и прямоугольники в GDI+</span><span class="sxs-lookup"><span data-stu-id="a8978-115">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
