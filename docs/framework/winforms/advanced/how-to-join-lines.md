---
title: Практическое руководство. Соединение линий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
ms.openlocfilehash: 445d7f12f57137c6b06a074eeaf0574eb027a723
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723307"
---
# <a name="how-to-join-lines"></a><span data-ttu-id="face2-102">Практическое руководство. Соединение линий</span><span class="sxs-lookup"><span data-stu-id="face2-102">How to: Join Lines</span></span>
<span data-ttu-id="face2-103">Соединение линий — это общая область, сформированное две строки, в которых заканчивается достигают или перекрываться.</span><span class="sxs-lookup"><span data-stu-id="face2-103">A line join is the common area that is formed by two lines whose ends meet or overlap.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="face2-104">предоставляет три стиля соединения линий: фацетное соединение, рельеф и округления.</span><span class="sxs-lookup"><span data-stu-id="face2-104">provides three line join styles: miter, bevel, and round.</span></span> <span data-ttu-id="face2-105">Стиль соединения линий — это свойство <xref:System.Drawing.Pen> класса.</span><span class="sxs-lookup"><span data-stu-id="face2-105">Line join style is a property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="face2-106">При указании стиль соединения линий для <xref:System.Drawing.Pen> объекта, что стиль будет применяться для всех соединенных линий в любом <xref:System.Drawing.Drawing2D.GraphicsPath> объекта, отображаются с помощью этого пера.</span><span class="sxs-lookup"><span data-stu-id="face2-106">When you specify a line join style for a <xref:System.Drawing.Pen> object, that join style will be applied to all the connected lines in any <xref:System.Drawing.Drawing2D.GraphicsPath> object drawn using that pen.</span></span>  
  
 <span data-ttu-id="face2-107">Ниже показаны результаты в примере скошенные строки соединения.</span><span class="sxs-lookup"><span data-stu-id="face2-107">The following illustration shows the results of the beveled line join example.</span></span>  
  
 ![Рисунок, показывающий соединяемых строк.](./media/how-to-join-lines/joined-beveled-lines.gif)  
  
## <a name="example"></a><span data-ttu-id="face2-109">Пример</span><span class="sxs-lookup"><span data-stu-id="face2-109">Example</span></span>  
 <span data-ttu-id="face2-110">Можно указать стиль соединения линий с помощью <xref:System.Drawing.Pen.LineJoin%2A> свойство <xref:System.Drawing.Pen> класса.</span><span class="sxs-lookup"><span data-stu-id="face2-110">You can specify the line join style by using the <xref:System.Drawing.Pen.LineJoin%2A> property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="face2-111">В примере скошенное соединение линий между горизонтальной и вертикальной линией.</span><span class="sxs-lookup"><span data-stu-id="face2-111">The example demonstrates a beveled line join between a horizontal line and a vertical line.</span></span> <span data-ttu-id="face2-112">В следующем коде значение <xref:System.Drawing.Drawing2D.LineJoin.Bevel> назначенные <xref:System.Drawing.Pen.LineJoin%2A> свойства является членом <xref:System.Drawing.Drawing2D.LineJoin> перечисления.</span><span class="sxs-lookup"><span data-stu-id="face2-112">In the following code, the value <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assigned to the <xref:System.Drawing.Pen.LineJoin%2A> property is a member of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration.</span></span> <span data-ttu-id="face2-113">Другие члены <xref:System.Drawing.Drawing2D.LineJoin> перечисления являются <xref:System.Drawing.Drawing2D.LineJoin.Miter> и <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span><span class="sxs-lookup"><span data-stu-id="face2-113">The other members of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration are <xref:System.Drawing.Drawing2D.LineJoin.Miter> and <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="face2-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="face2-114">Compiling the Code</span></span>  
 <span data-ttu-id="face2-115">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="face2-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="face2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="face2-116">See also</span></span>

- [<span data-ttu-id="face2-117">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="face2-117">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
