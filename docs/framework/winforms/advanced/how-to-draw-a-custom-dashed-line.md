---
title: Практическое руководство. Рисование пользовательских пунктирных линий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: 06555309b8432397e754bc9dfa717c89b052343f
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410229"
---
# <a name="how-to-draw-a-custom-dashed-line"></a><span data-ttu-id="4390e-102">Практическое руководство. Рисование пользовательских пунктирных линий</span><span class="sxs-lookup"><span data-stu-id="4390e-102">How to: Draw a Custom Dashed Line</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="4390e-103">предоставляет несколько стили штрихов, которые перечислены в <xref:System.Drawing.Drawing2D.DashStyle> перечисления.</span><span class="sxs-lookup"><span data-stu-id="4390e-103">provides several dash styles that are listed in the <xref:System.Drawing.Drawing2D.DashStyle> enumeration.</span></span> <span data-ttu-id="4390e-104">Если эти стандартные штриха не соответствуют вашим потребностям, можно создать пользовательские штриха.</span><span class="sxs-lookup"><span data-stu-id="4390e-104">If those standard dash styles do not suit your needs, you can create a custom dash pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4390e-105">Пример</span><span class="sxs-lookup"><span data-stu-id="4390e-105">Example</span></span>  
 <span data-ttu-id="4390e-106">Рисование пользовательских пунктирных линий, поместите длины штрихов и промежутков в массиве и назначить массив в качестве значения <xref:System.Drawing.Pen.DashPattern%2A> свойство <xref:System.Drawing.Pen> объекта.</span><span class="sxs-lookup"><span data-stu-id="4390e-106">To draw a custom dashed line, put the lengths of the dashes and spaces in an array and assign the array as the value of the <xref:System.Drawing.Pen.DashPattern%2A> property of a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="4390e-107">В следующем примере рисуется пользовательских пунктирных линий на основе массива `{5, 2, 15, 4}`.</span><span class="sxs-lookup"><span data-stu-id="4390e-107">The following example draws a custom dashed line based on the array `{5, 2, 15, 4}`.</span></span> <span data-ttu-id="4390e-108">Если элементы массива умножить на ширину пера, 5, вы получаете `{25, 10, 75, 20}`.</span><span class="sxs-lookup"><span data-stu-id="4390e-108">If you multiply the elements of the array by the pen width of 5, you get `{25, 10, 75, 20}`.</span></span> <span data-ttu-id="4390e-109">Отображаемые дефисы альтернативный длиной от 25 до 75, и пробелы альтернативные длиной от 10 до 20.</span><span class="sxs-lookup"><span data-stu-id="4390e-109">The displayed dashes alternate in length between 25 and 75, and the spaces alternate in length between 10 and 20.</span></span>  
  
 <span data-ttu-id="4390e-110">Ниже показан итоговый пунктирная линия.</span><span class="sxs-lookup"><span data-stu-id="4390e-110">The following illustration shows the resulting dashed line.</span></span> <span data-ttu-id="4390e-111">Обратите внимание, что это должно быть короче 25 единиц, таким образом, чтобы конец линии в последний штрих (405, 5).</span><span class="sxs-lookup"><span data-stu-id="4390e-111">Note that the final dash has to be shorter than 25 units so that the line can end at (405, 5).</span></span>  
  
 <span data-ttu-id="4390e-112">![Рисунок, показывающий пунктирной линией. ](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")</span><span class="sxs-lookup"><span data-stu-id="4390e-112">![Illustration that shows a dashed line.](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4390e-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="4390e-113">Compiling the Code</span></span>  
 <span data-ttu-id="4390e-114">Создайте форму Windows и обработки формы <xref:System.Windows.Forms.Control.Paint> событий.</span><span class="sxs-lookup"><span data-stu-id="4390e-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="4390e-115">Вставьте приведенный выше код в <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="4390e-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4390e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4390e-116">See also</span></span>
- [<span data-ttu-id="4390e-117">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="4390e-117">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
