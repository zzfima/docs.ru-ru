---
title: Как выполнить Визуализация буферизированной графики вручную
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually rendering graphics
- graphics [Windows Forms], rendering
ms.assetid: 5192295e-bd8e-45f7-8bd6-5c4f6bd21e61
ms.openlocfilehash: f901350b1cb63f385eba52665785c8d0f7fd7e5f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636356"
---
# <a name="how-to-manually-render-buffered-graphics"></a><span data-ttu-id="52216-102">Как выполнить Визуализация буферизированной графики вручную</span><span class="sxs-lookup"><span data-stu-id="52216-102">How to: Manually Render Buffered Graphics</span></span>
<span data-ttu-id="52216-103">При управлении собственной буферизованной графикой необходимо иметь возможность создавать буферы графики и визуализировать их.</span><span class="sxs-lookup"><span data-stu-id="52216-103">If you are managing your own buffered graphics, you will need to be able to create and render graphics buffers.</span></span> <span data-ttu-id="52216-104">Чтобы создать экземпляр класса <xref:System.Drawing.BufferedGraphics>, связанный с поверхностью рисования на экране, можно вызвать метод <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A>.</span><span class="sxs-lookup"><span data-stu-id="52216-104">You can create instances of the <xref:System.Drawing.BufferedGraphics> class that is associated with drawing surfaces on your screen by calling the <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> method.</span></span> <span data-ttu-id="52216-105">Этот метод создает экземпляр <xref:System.Drawing.BufferedGraphics>, связанный с определенной поверхностью отрисовки, например формой или элементом управления.</span><span class="sxs-lookup"><span data-stu-id="52216-105">This method creates a <xref:System.Drawing.BufferedGraphics> instance that is associated with a particular rendering surface, such as a form or control.</span></span> <span data-ttu-id="52216-106">После создания экземпляра <xref:System.Drawing.BufferedGraphics> можно добавлять графические объекты в представляемый им буфер через свойство <xref:System.Drawing.BufferedGraphics.Graphics%2A>.</span><span class="sxs-lookup"><span data-stu-id="52216-106">After you have created a <xref:System.Drawing.BufferedGraphics> instance, you can draw graphics to the buffer it represents through the <xref:System.Drawing.BufferedGraphics.Graphics%2A> property.</span></span> <span data-ttu-id="52216-107">После выполнения всех операций с графикой можно скопировать содержимое буфера на экран, вызвав метод <xref:System.Drawing.BufferedGraphics.Render%2A>.</span><span class="sxs-lookup"><span data-stu-id="52216-107">After you have performed all graphics operations, you can copy the contents of the buffer to the screen by calling the <xref:System.Drawing.BufferedGraphics.Render%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52216-108">При выполнении собственной отрисовки потребление памяти увеличится, хотя это увеличение может быть и незначительным.</span><span class="sxs-lookup"><span data-stu-id="52216-108">If you perform your own rendering, memory consumption will increase, though the increase may only be slight.</span></span>  
  
### <a name="to-manually-display-buffered-graphics"></a><span data-ttu-id="52216-109">Вывод буферизованной графики вручную</span><span class="sxs-lookup"><span data-stu-id="52216-109">To manually display buffered graphics</span></span>  
  
1.  <span data-ttu-id="52216-110">Получите ссылку на экземпляр класса <xref:System.Drawing.BufferedGraphicsContext>.</span><span class="sxs-lookup"><span data-stu-id="52216-110">Obtain a reference to an instance of the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="52216-111">Дополнительные сведения см. в разделе [Как Управление буферизацией графики](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).</span><span class="sxs-lookup"><span data-stu-id="52216-111">For more information, see [How to: Manually Manage Buffered Graphics](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).</span></span>  
  
2.  <span data-ttu-id="52216-112">Создайте экземпляр класса <xref:System.Drawing.BufferedGraphics>, вызвав метод <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A>, как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="52216-112">Create an instance of the <xref:System.Drawing.BufferedGraphics> class by calling the <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> method, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#21)]  
  
3.  <span data-ttu-id="52216-113">С помощью свойства <xref:System.Drawing.BufferedGraphics.Graphics%2A> поместите в буфер графические объекты.</span><span class="sxs-lookup"><span data-stu-id="52216-113">Draw graphics to the graphics buffer by setting the <xref:System.Drawing.BufferedGraphics.Graphics%2A> property.</span></span> <span data-ttu-id="52216-114">Пример:</span><span class="sxs-lookup"><span data-stu-id="52216-114">For example:</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#22)]  
  
4.  <span data-ttu-id="52216-115">Завершив операции рисования в графическом буфере, вызовите метод <xref:System.Drawing.BufferedGraphics.Render%2A>, чтобы отрисовать содержимое буфера на связанной с ним поверхности рисования или на указанной поверхности, как показано в примере кода ниже.</span><span class="sxs-lookup"><span data-stu-id="52216-115">When you have completed all of your drawing operations to the graphics buffer, call the <xref:System.Drawing.BufferedGraphics.Render%2A> method to render the buffer, either to the drawing surface associated with that buffer, or to a specified drawing surface, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#23)]  
  
5.  <span data-ttu-id="52216-116">Выполнив отрисовку графики, вызовите метод `Dispose` экземпляра <xref:System.Drawing.BufferedGraphics>, чтобы освободить ресурсы системы.</span><span class="sxs-lookup"><span data-stu-id="52216-116">After you are finished rendering graphics, call the `Dispose` method on the <xref:System.Drawing.BufferedGraphics> instance to free system resources.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#24](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#24)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#24](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#24)]  
  
## <a name="see-also"></a><span data-ttu-id="52216-117">См. также</span><span class="sxs-lookup"><span data-stu-id="52216-117">See also</span></span>
- <xref:System.Drawing.BufferedGraphicsContext>
- <xref:System.Drawing.BufferedGraphics>
- [<span data-ttu-id="52216-118">Двойная буферизация графики</span><span class="sxs-lookup"><span data-stu-id="52216-118">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)
- [<span data-ttu-id="52216-119">Практическое руководство. Управление буферизацией графики</span><span class="sxs-lookup"><span data-stu-id="52216-119">How to: Manually Manage Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)
