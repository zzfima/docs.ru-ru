---
title: Практическое руководство. Управление буферизацией графики вручную
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: 6010d52750b20c07db51917621f8643e9d9b47d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968600"
---
# <a name="how-to-manually-manage-buffered-graphics"></a><span data-ttu-id="e694a-102">Практическое руководство. Управление буферизацией графики вручную</span><span class="sxs-lookup"><span data-stu-id="e694a-102">How to: Manually Manage Buffered Graphics</span></span>
<span data-ttu-id="e694a-103">Для более сложных сценариев двойного буферизации можно использовать классы .NET Framework для реализации собственной логики двойной буферизации.</span><span class="sxs-lookup"><span data-stu-id="e694a-103">For more advanced double buffering scenarios, you can use the .NET Framework classes to implement your own double-buffering logic.</span></span> <span data-ttu-id="e694a-104">Класс, ответственный за выделение отдельных графических буферов и управление ими <xref:System.Drawing.BufferedGraphicsContext> , является классом.</span><span class="sxs-lookup"><span data-stu-id="e694a-104">The class responsible for allocating and managing individual graphics buffers is the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="e694a-105">Каждое приложение имеет собственное значение по <xref:System.Drawing.BufferedGraphicsContext> умолчанию, которое управляет всей двойной буферизацией приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e694a-105">Every application has its own default <xref:System.Drawing.BufferedGraphicsContext> that manages all of the default double buffering for that application.</span></span> <span data-ttu-id="e694a-106">Ссылку на этот экземпляр можно получить, вызвав метод <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="e694a-106">You can retrieve a reference to this instance by calling the <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span></span>  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a><span data-ttu-id="e694a-107">Получение ссылки на BufferedGraphicsContext по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e694a-107">To obtain a reference to the default BufferedGraphicsContext</span></span>  
  
- <span data-ttu-id="e694a-108"><xref:System.Drawing.BufferedGraphicsManager.Current%2A> Задайте свойство, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="e694a-108">Set the <xref:System.Drawing.BufferedGraphicsManager.Current%2A> property, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    > <span data-ttu-id="e694a-109">Вам не нужно вызывать `Dispose` метод <xref:System.Drawing.BufferedGraphicsContext> для ссылки <xref:System.Drawing.BufferedGraphicsManager> , полученной из класса.</span><span class="sxs-lookup"><span data-stu-id="e694a-109">You do not need to call the `Dispose` method on the <xref:System.Drawing.BufferedGraphicsContext> reference that you receive from the <xref:System.Drawing.BufferedGraphicsManager> class.</span></span> <span data-ttu-id="e694a-110">Обработчик обрабатывает все операции выделения и распределения памяти для экземпляров по умолчанию <xref:System.Drawing.BufferedGraphicsContext>. <xref:System.Drawing.BufferedGraphicsManager></span><span class="sxs-lookup"><span data-stu-id="e694a-110">The <xref:System.Drawing.BufferedGraphicsManager> handles all of the memory allocation and distribution for default <xref:System.Drawing.BufferedGraphicsContext> instances.</span></span>  
  
     <span data-ttu-id="e694a-111">Для ресурсоемких графических приложений, таких как анимация, иногда можно повысить производительность, используя выделенный <xref:System.Drawing.BufferedGraphicsContext> вместо, <xref:System.Drawing.BufferedGraphicsContext> предоставленный <xref:System.Drawing.BufferedGraphicsManager>.</span><span class="sxs-lookup"><span data-stu-id="e694a-111">For graphically intensive applications such as animation, you can sometimes improve performance by using a dedicated <xref:System.Drawing.BufferedGraphicsContext> instead of the <xref:System.Drawing.BufferedGraphicsContext> provided by the <xref:System.Drawing.BufferedGraphicsManager>.</span></span> <span data-ttu-id="e694a-112">Это позволяет создавать графические буферы и управлять ими по отдельности без снижения производительности при управлении всеми другими буферизованными графиками, связанными с приложением, хотя объем памяти, потребляемый приложением, будет больше.</span><span class="sxs-lookup"><span data-stu-id="e694a-112">This enables you to create and manage graphics buffers individually, without incurring the performance overhead of managing all the other buffered graphics associated with your application, though the memory consumed by the application will be greater.</span></span>  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a><span data-ttu-id="e694a-113">Создание выделенного BufferedGraphicsContext</span><span class="sxs-lookup"><span data-stu-id="e694a-113">To create a dedicated BufferedGraphicsContext</span></span>  
  
- <span data-ttu-id="e694a-114">Объявите и создайте новый экземпляр <xref:System.Drawing.BufferedGraphicsContext> класса, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="e694a-114">Declare and create a new instance of the <xref:System.Drawing.BufferedGraphicsContext> class, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="e694a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e694a-115">See also</span></span>

- <xref:System.Drawing.BufferedGraphicsContext>
- [<span data-ttu-id="e694a-116">Двойная буферизация графики</span><span class="sxs-lookup"><span data-stu-id="e694a-116">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="e694a-117">Практическое руководство. Ручная прорисовка буферизованной графики</span><span class="sxs-lookup"><span data-stu-id="e694a-117">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)
