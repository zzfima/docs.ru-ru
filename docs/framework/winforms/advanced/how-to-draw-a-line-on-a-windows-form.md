---
title: Практическое руководство. Рисование линии в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
ms.openlocfilehash: da83699b1f7a3c2e6c781040ca0be7ec2c9a6df0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523346"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a><span data-ttu-id="8d19e-102">Практическое руководство. Рисование линии в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8d19e-102">How to: Draw a Line on a Windows Form</span></span>
<span data-ttu-id="8d19e-103">В этом примере рисование линии в форме.</span><span class="sxs-lookup"><span data-stu-id="8d19e-103">This example draws a line on a form.</span></span> <span data-ttu-id="8d19e-104">Как правило, при рисовании в форме обработки формы <xref:System.Windows.Forms.Control.Paint> событий и выполнять рисование с помощью <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> свойство <xref:System.Windows.Forms.PaintEventArgs>, как показано в следующем примере</span><span class="sxs-lookup"><span data-stu-id="8d19e-104">Typically, when you draw on a form, you handle the form’s  <xref:System.Windows.Forms.Control.Paint> event and perform the drawing using the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.PaintEventArgs>, as shown in this example</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d19e-105">Пример</span><span class="sxs-lookup"><span data-stu-id="8d19e-105">Example</span></span>  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8d19e-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="8d19e-106">Compiling the Code</span></span>  
 <span data-ttu-id="8d19e-107">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="8d19e-107">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8d19e-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="8d19e-108">Robust Programming</span></span>  
 <span data-ttu-id="8d19e-109">Следует всегда вызывать <xref:System.IDisposable.Dispose%2A> на все объекты, которые потребляют системные ресурсы, такие как <xref:System.Drawing.Pen> объектов.</span><span class="sxs-lookup"><span data-stu-id="8d19e-109">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d19e-110">См. также</span><span class="sxs-lookup"><span data-stu-id="8d19e-110">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawLine%2A>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="8d19e-111">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="8d19e-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="8d19e-112">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="8d19e-112">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="8d19e-113">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8d19e-113">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
