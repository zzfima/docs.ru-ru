---
title: Как выполнить Соединение линий
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
ms.openlocfilehash: 55551a78f37a5179b24eda28a9fc5d0a0c640a9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543387"
---
# <a name="how-to-join-lines"></a><span data-ttu-id="56605-102">Как выполнить Соединение линий</span><span class="sxs-lookup"><span data-stu-id="56605-102">How to: Join Lines</span></span>
<span data-ttu-id="56605-103">Соединение линий — это общая область, сформированное две строки, в которых заканчивается достигают или перекрываться.</span><span class="sxs-lookup"><span data-stu-id="56605-103">A line join is the common area that is formed by two lines whose ends meet or overlap.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="56605-104">предоставляет три стиля соединения линий: фацетное соединение, рельеф и округления.</span><span class="sxs-lookup"><span data-stu-id="56605-104">provides three line join styles: miter, bevel, and round.</span></span> <span data-ttu-id="56605-105">Стиль соединения линий — это свойство <xref:System.Drawing.Pen> класса.</span><span class="sxs-lookup"><span data-stu-id="56605-105">Line join style is a property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="56605-106">При указании стиль соединения линий для <xref:System.Drawing.Pen> объекта, что стиль будет применяться для всех соединенных линий в любом <xref:System.Drawing.Drawing2D.GraphicsPath> объекта, отображаются с помощью этого пера.</span><span class="sxs-lookup"><span data-stu-id="56605-106">When you specify a line join style for a <xref:System.Drawing.Pen> object, that join style will be applied to all the connected lines in any <xref:System.Drawing.Drawing2D.GraphicsPath> object drawn using that pen.</span></span>  
  
 <span data-ttu-id="56605-107">Ниже показаны результаты в примере скошенные строки соединения.</span><span class="sxs-lookup"><span data-stu-id="56605-107">The following illustration shows the results of the beveled line join example.</span></span>  
  
 <span data-ttu-id="56605-108">![Перья](../../../../docs/framework/winforms/advanced/media/pens5.gif "pens5")</span><span class="sxs-lookup"><span data-stu-id="56605-108">![Pens](../../../../docs/framework/winforms/advanced/media/pens5.gif "pens5")</span></span>  
  
## <a name="example"></a><span data-ttu-id="56605-109">Пример</span><span class="sxs-lookup"><span data-stu-id="56605-109">Example</span></span>  
 <span data-ttu-id="56605-110">Можно указать стиль соединения линий с помощью <xref:System.Drawing.Pen.LineJoin%2A> свойство <xref:System.Drawing.Pen> класса.</span><span class="sxs-lookup"><span data-stu-id="56605-110">You can specify the line join style by using the <xref:System.Drawing.Pen.LineJoin%2A> property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="56605-111">В примере скошенное соединение линий между горизонтальной и вертикальной линией.</span><span class="sxs-lookup"><span data-stu-id="56605-111">The example demonstrates a beveled line join between a horizontal line and a vertical line.</span></span> <span data-ttu-id="56605-112">В следующем коде значение <xref:System.Drawing.Drawing2D.LineJoin.Bevel> назначенные <xref:System.Drawing.Pen.LineJoin%2A> свойства является членом <xref:System.Drawing.Drawing2D.LineJoin> перечисления.</span><span class="sxs-lookup"><span data-stu-id="56605-112">In the following code, the value <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assigned to the <xref:System.Drawing.Pen.LineJoin%2A> property is a member of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration.</span></span> <span data-ttu-id="56605-113">Другие члены <xref:System.Drawing.Drawing2D.LineJoin> перечисления являются <xref:System.Drawing.Drawing2D.LineJoin.Miter> и <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span><span class="sxs-lookup"><span data-stu-id="56605-113">The other members of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration are <xref:System.Drawing.Drawing2D.LineJoin.Miter> and <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="56605-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="56605-114">Compiling the Code</span></span>  
 <span data-ttu-id="56605-115">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="56605-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56605-116">См. также</span><span class="sxs-lookup"><span data-stu-id="56605-116">See also</span></span>
- [<span data-ttu-id="56605-117">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="56605-117">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
