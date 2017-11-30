---
title: "Практическое руководство. Рисование пользовательских пунктирных линий"
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
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 90fcc99414e8d5c9542d643677c85d4ff670f50f
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-draw-a-custom-dashed-line"></a><span data-ttu-id="bbe12-102">Практическое руководство. Рисование пользовательских пунктирных линий</span><span class="sxs-lookup"><span data-stu-id="bbe12-102">How to: Draw a Custom Dashed Line</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="bbe12-103">предоставляет несколько стили штрихов, которые перечислены в <xref:System.Drawing.Drawing2D.DashStyle> перечисления.</span><span class="sxs-lookup"><span data-stu-id="bbe12-103"> provides several dash styles that are listed in the <xref:System.Drawing.Drawing2D.DashStyle> enumeration.</span></span> <span data-ttu-id="bbe12-104">Если эти стандартные стили пунктирных линий не подходят, можно создать пользовательский шаблон пунктирной линии.</span><span class="sxs-lookup"><span data-stu-id="bbe12-104">If those standard dash styles do not suit your needs, you can create a custom dash pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbe12-105">Пример</span><span class="sxs-lookup"><span data-stu-id="bbe12-105">Example</span></span>  
 <span data-ttu-id="bbe12-106">Рисование пользовательских пунктирных линий, поместите длины штрихов и промежутков в массив и присвойте его значение <xref:System.Drawing.Pen.DashPattern%2A> свойство <xref:System.Drawing.Pen> объекта.</span><span class="sxs-lookup"><span data-stu-id="bbe12-106">To draw a custom dashed line, put the lengths of the dashes and spaces in an array and assign the array as the value of the <xref:System.Drawing.Pen.DashPattern%2A> property of a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="bbe12-107">В следующем примере рисуется пользовательская пунктирная линия на основе массива `{5, 2, 15, 4}`.</span><span class="sxs-lookup"><span data-stu-id="bbe12-107">The following example draws a custom dashed line based on the array `{5, 2, 15, 4}`.</span></span> <span data-ttu-id="bbe12-108">Если умножить ширину пера 5 элементов массива, можно получить `{25, 10, 75, 20}`.</span><span class="sxs-lookup"><span data-stu-id="bbe12-108">If you multiply the elements of the array by the pen width of 5, you get `{25, 10, 75, 20}`.</span></span> <span data-ttu-id="bbe12-109">Альтернативные отображаемых дефисы длиной от 25 до 75 и альтернативные пробелы в расстояние от 10 до 20.</span><span class="sxs-lookup"><span data-stu-id="bbe12-109">The displayed dashes alternate in length between 25 and 75, and the spaces alternate in length between 10 and 20.</span></span>  
  
 <span data-ttu-id="bbe12-110">Ниже показан результирующий пунктирной линией.</span><span class="sxs-lookup"><span data-stu-id="bbe12-110">The following illustration shows the resulting dashed line.</span></span> <span data-ttu-id="bbe12-111">Обратите внимание, что последний штрих должен быть короче 25 единиц, чтобы заканчиваться на строке (405, 5).</span><span class="sxs-lookup"><span data-stu-id="bbe12-111">Note that the final dash has to be shorter than 25 units so that the line can end at (405, 5).</span></span>  
  
 <span data-ttu-id="bbe12-112">![Перья](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")</span><span class="sxs-lookup"><span data-stu-id="bbe12-112">![Pens](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bbe12-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="bbe12-113">Compiling the Code</span></span>  
 <span data-ttu-id="bbe12-114">Создайте форму Windows Form и обработки формы <xref:System.Windows.Forms.Control.Paint> событий.</span><span class="sxs-lookup"><span data-stu-id="bbe12-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="bbe12-115">Вставьте приведенный выше код в <xref:System.Windows.Forms.Control.Paint> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="bbe12-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe12-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bbe12-116">See Also</span></span>  
 [<span data-ttu-id="bbe12-117">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="bbe12-117">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
