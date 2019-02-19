---
title: Практическое руководство. Рисований линий в Windows Forms
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
ms.openlocfilehash: 4274072b55c79cfe88e906d1401d275b414ebe97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586752"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a><span data-ttu-id="e8872-102">Практическое руководство. Рисований линий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e8872-102">How to: Draw a Line on a Windows Form</span></span>
<span data-ttu-id="e8872-103">Этот пример рисует линию на форме.</span><span class="sxs-lookup"><span data-stu-id="e8872-103">This example draws a line on a form.</span></span> <span data-ttu-id="e8872-104">Как правило, рисование на форме осуществляют, обрабатывая событие <xref:System.Windows.Forms.Control.Paint> формы и выполняя отрисовку с использованием свойства <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> объекта <xref:System.Windows.Forms.PaintEventArgs>, как показано в следующем примере</span><span class="sxs-lookup"><span data-stu-id="e8872-104">Typically, when you draw on a form, you handle the form’s  <xref:System.Windows.Forms.Control.Paint> event and perform the drawing using the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.PaintEventArgs>, as shown in this example</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8872-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e8872-105">Example</span></span>  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e8872-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e8872-106">Compiling the Code</span></span>  
 <span data-ttu-id="e8872-107">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром обработчика события <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="e8872-107">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e8872-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="e8872-108">Robust Programming</span></span>  
 <span data-ttu-id="e8872-109">Следует всегда вызывать <xref:System.IDisposable.Dispose%2A> для любых объектов, которые потребляют системные ресурсы, например объектов <xref:System.Drawing.Pen>.</span><span class="sxs-lookup"><span data-stu-id="e8872-109">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8872-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e8872-110">See also</span></span>
- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="e8872-111">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="e8872-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [<span data-ttu-id="e8872-112">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="e8872-112">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="e8872-113">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e8872-113">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
