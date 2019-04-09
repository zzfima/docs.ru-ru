---
title: Практическое руководство. Уменьшение эффекта дрожания изображения посредством двойной буферизации для форм и элементов управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: ef05b72b33d3f28d1811389dfae65554a1567d43
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096957"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a><span data-ttu-id="d8b6d-102">Практическое руководство. Уменьшение эффекта дрожания изображения посредством двойной буферизации для форм и элементов управления</span><span class="sxs-lookup"><span data-stu-id="d8b6d-102">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>
<span data-ttu-id="d8b6d-103">Двойная буферизация использует буфер памяти для решения проблем мерцания, связанных с несколькими операциями рисования.</span><span class="sxs-lookup"><span data-stu-id="d8b6d-103">Double buffering uses a memory buffer to address the flicker problems associated with multiple paint operations.</span></span> <span data-ttu-id="d8b6d-104">Если двойная буферизация включена, все операции рисования сначала обрабатываются в буфере памяти вместо области рисования на экране.</span><span class="sxs-lookup"><span data-stu-id="d8b6d-104">When double buffering is enabled, all paint operations are first rendered to a memory buffer instead of the drawing surface on the screen.</span></span> <span data-ttu-id="d8b6d-105">После завершения всех операций рисования буфер памяти копируется непосредственно в связанную с ним область рисования.</span><span class="sxs-lookup"><span data-stu-id="d8b6d-105">After all paint operations are completed, the memory buffer is copied directly to the drawing surface associated with it.</span></span> <span data-ttu-id="d8b6d-106">Поскольку на экране выполняется лишь одна графическая операция, исключается мерцание со сложными операциями рисования. Для большинства приложений по умолчанию двойной буферизации [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] обеспечит лучшие результаты.</span><span class="sxs-lookup"><span data-stu-id="d8b6d-106">Because only one graphics operation is performed on the screen, the image flickering associated with complex painting operations is eliminated.For most applications, the default double buffering provided by the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] will provide the best results.</span></span> <span data-ttu-id="d8b6d-107">Стандартные элементы управления Windows Forms являются двойной буферизации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d8b6d-107">Standard Windows Forms controls are double buffered by default.</span></span> <span data-ttu-id="d8b6d-108">Вы можете включить двойную буферизацию в формах и элементах управления двумя способами.</span><span class="sxs-lookup"><span data-stu-id="d8b6d-108">You can enable default double buffering in your forms and authored controls in two ways.</span></span> <span data-ttu-id="d8b6d-109">Можно либо установить <xref:System.Windows.Forms.Control.DoubleBuffered%2A> свойства `true`, либо путем вызова <xref:System.Windows.Forms.Control.SetStyle%2A> метод, чтобы задать <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> флаг `true`.</span><span class="sxs-lookup"><span data-stu-id="d8b6d-109">You can either set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`, or you can call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span> <span data-ttu-id="d8b6d-110">Оба метода включает двойной буферизации по умолчанию для формы или элемента управления и обеспечения отрисовки графики без мерцания.</span><span class="sxs-lookup"><span data-stu-id="d8b6d-110">Both methods will enable default double buffering for your form or control and provide flicker-free graphics rendering.</span></span> <span data-ttu-id="d8b6d-111">Вызов <xref:System.Windows.Forms.Control.SetStyle%2A> рекомендуется только для пользовательских элементов управления, для которых вы написали весь код отрисовки.</span><span class="sxs-lookup"><span data-stu-id="d8b6d-111">Calling the <xref:System.Windows.Forms.Control.SetStyle%2A> method is recommended only for custom controls for which you have written all the rendering code.</span></span>  
  
 <span data-ttu-id="d8b6d-112">Для более сложных сценариях буферизации, например при анимации или сложном управлении памятью можно реализовать свою собственную логику для двойной буферизации.</span><span class="sxs-lookup"><span data-stu-id="d8b6d-112">For more advanced double buffering scenarios, such as animation or advanced memory management, you can implement your own double buffering logic.</span></span> <span data-ttu-id="d8b6d-113">Дополнительные сведения см. в разделе [Как Управление буферизацией графики](how-to-manually-manage-buffered-graphics.md).</span><span class="sxs-lookup"><span data-stu-id="d8b6d-113">For more information, see [How to: Manually Manage Buffered Graphics](how-to-manually-manage-buffered-graphics.md).</span></span>  
  
### <a name="to-reduce-flicker"></a><span data-ttu-id="d8b6d-114">Чтобы снизить мерцание</span><span class="sxs-lookup"><span data-stu-id="d8b6d-114">To reduce flicker</span></span>  
  
-   <span data-ttu-id="d8b6d-115">Задайте для свойства <xref:System.Windows.Forms.Control.DoubleBuffered%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d8b6d-115">Set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 <span data-ttu-id="d8b6d-116">\- или -</span><span class="sxs-lookup"><span data-stu-id="d8b6d-116">\- or -</span></span>  
  
-   <span data-ttu-id="d8b6d-117">Вызовите <xref:System.Windows.Forms.Control.SetStyle%2A> метод, чтобы задать <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> флаг `true`.</span><span class="sxs-lookup"><span data-stu-id="d8b6d-117">Call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="d8b6d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d8b6d-118">See also</span></span>

- <xref:System.Windows.Forms.Control.DoubleBuffered%2A>
- <xref:System.Windows.Forms.Control.SetStyle%2A>
- [<span data-ttu-id="d8b6d-119">Двойная буферизация графики</span><span class="sxs-lookup"><span data-stu-id="d8b6d-119">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="d8b6d-120">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d8b6d-120">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
