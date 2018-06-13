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
ms.openlocfilehash: 39dde3bb45165783171326b79e98744807350952
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521619"
---
# <a name="how-to-draw-a-custom-dashed-line"></a><span data-ttu-id="1d58c-102">Практическое руководство. Рисование пользовательских пунктирных линий</span><span class="sxs-lookup"><span data-stu-id="1d58c-102">How to: Draw a Custom Dashed Line</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="1d58c-103"> предоставляет несколько стили штрихов, которые перечислены в <xref:System.Drawing.Drawing2D.DashStyle> перечисления.</span><span class="sxs-lookup"><span data-stu-id="1d58c-103"> provides several dash styles that are listed in the <xref:System.Drawing.Drawing2D.DashStyle> enumeration.</span></span> <span data-ttu-id="1d58c-104">Если эти стандартные стили пунктирных линий не подходят, можно создать пользовательский шаблон пунктирной линии.</span><span class="sxs-lookup"><span data-stu-id="1d58c-104">If those standard dash styles do not suit your needs, you can create a custom dash pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d58c-105">Пример</span><span class="sxs-lookup"><span data-stu-id="1d58c-105">Example</span></span>  
 <span data-ttu-id="1d58c-106">Рисование пользовательских пунктирных линий, поместите длины штрихов и промежутков в массив и присвойте его значение <xref:System.Drawing.Pen.DashPattern%2A> свойство <xref:System.Drawing.Pen> объекта.</span><span class="sxs-lookup"><span data-stu-id="1d58c-106">To draw a custom dashed line, put the lengths of the dashes and spaces in an array and assign the array as the value of the <xref:System.Drawing.Pen.DashPattern%2A> property of a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="1d58c-107">В следующем примере рисуется пользовательская пунктирная линия на основе массива `{5, 2, 15, 4}`.</span><span class="sxs-lookup"><span data-stu-id="1d58c-107">The following example draws a custom dashed line based on the array `{5, 2, 15, 4}`.</span></span> <span data-ttu-id="1d58c-108">Если умножить ширину пера 5 элементов массива, можно получить `{25, 10, 75, 20}`.</span><span class="sxs-lookup"><span data-stu-id="1d58c-108">If you multiply the elements of the array by the pen width of 5, you get `{25, 10, 75, 20}`.</span></span> <span data-ttu-id="1d58c-109">Альтернативные отображаемых дефисы длиной от 25 до 75 и альтернативные пробелы в расстояние от 10 до 20.</span><span class="sxs-lookup"><span data-stu-id="1d58c-109">The displayed dashes alternate in length between 25 and 75, and the spaces alternate in length between 10 and 20.</span></span>  
  
 <span data-ttu-id="1d58c-110">Ниже показан результирующий пунктирной линией.</span><span class="sxs-lookup"><span data-stu-id="1d58c-110">The following illustration shows the resulting dashed line.</span></span> <span data-ttu-id="1d58c-111">Обратите внимание, что последний штрих должен быть короче 25 единиц, чтобы заканчиваться на строке (405, 5).</span><span class="sxs-lookup"><span data-stu-id="1d58c-111">Note that the final dash has to be shorter than 25 units so that the line can end at (405, 5).</span></span>  
  
 <span data-ttu-id="1d58c-112">![Перья](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")</span><span class="sxs-lookup"><span data-stu-id="1d58c-112">![Pens](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1d58c-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="1d58c-113">Compiling the Code</span></span>  
 <span data-ttu-id="1d58c-114">Создайте форму Windows Form и обработки формы <xref:System.Windows.Forms.Control.Paint> событий.</span><span class="sxs-lookup"><span data-stu-id="1d58c-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="1d58c-115">Вставьте приведенный выше код в <xref:System.Windows.Forms.Control.Paint> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="1d58c-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d58c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1d58c-116">See Also</span></span>  
 [<span data-ttu-id="1d58c-117">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="1d58c-117">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
