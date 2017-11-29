---
title: "Практическое руководство. Управление буферизацией графики"
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
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 678b9ad5e8f9b40f927a35e98973cabc831c5cf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manually-manage-buffered-graphics"></a><span data-ttu-id="7fd9e-102">Практическое руководство. Управление буферизацией графики</span><span class="sxs-lookup"><span data-stu-id="7fd9e-102">How to: Manually Manage Buffered Graphics</span></span>
<span data-ttu-id="7fd9e-103">Для более сложных случаях буферизации, можно использовать [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] классов для реализации собственной логики двойной буферизации.</span><span class="sxs-lookup"><span data-stu-id="7fd9e-103">For more advanced double buffering scenarios, you can use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] classes to implement your own double-buffering logic.</span></span> <span data-ttu-id="7fd9e-104">Этот класс отвечает за выделение и управление отдельных буферов графики является <xref:System.Drawing.BufferedGraphicsContext> класса.</span><span class="sxs-lookup"><span data-stu-id="7fd9e-104">The class responsible for allocating and managing individual graphics buffers is the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="7fd9e-105">Каждое приложение имеет свой собственный по умолчанию <xref:System.Drawing.BufferedGraphicsContext> , управляет всеми двойную буферизацию для этого приложения.</span><span class="sxs-lookup"><span data-stu-id="7fd9e-105">Every application has its own default <xref:System.Drawing.BufferedGraphicsContext> that manages all of the default double buffering for that application.</span></span> <span data-ttu-id="7fd9e-106">Ссылка на этот экземпляр можно получить, вызвав <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fd9e-106">You can retrieve a reference to this instance by calling the <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span></span>  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a><span data-ttu-id="7fd9e-107">Для получения ссылки на значение по умолчанию BufferedGraphicsContext</span><span class="sxs-lookup"><span data-stu-id="7fd9e-107">To obtain a reference to the default BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="7fd9e-108">Задать <xref:System.Drawing.BufferedGraphicsManager.Current%2A> свойства, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="7fd9e-108">Set the <xref:System.Drawing.BufferedGraphicsManager.Current%2A> property, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  <span data-ttu-id="7fd9e-109">Необходимо вызвать `Dispose` метод <xref:System.Drawing.BufferedGraphicsContext> ссылки, полученные из <xref:System.Drawing.BufferedGraphicsManager> класса.</span><span class="sxs-lookup"><span data-stu-id="7fd9e-109">You do not need to call the `Dispose` method on the <xref:System.Drawing.BufferedGraphicsContext> reference that you receive from the <xref:System.Drawing.BufferedGraphicsManager> class.</span></span> <span data-ttu-id="7fd9e-110"><xref:System.Drawing.BufferedGraphicsManager> Обрабатывает все выделение памяти и распространения по умолчанию <xref:System.Drawing.BufferedGraphicsContext> экземпляров.</span><span class="sxs-lookup"><span data-stu-id="7fd9e-110">The <xref:System.Drawing.BufferedGraphicsManager> handles all of the memory allocation and distribution for default <xref:System.Drawing.BufferedGraphicsContext> instances.</span></span>  
  
     <span data-ttu-id="7fd9e-111">Для графические приложения, такие как анимация, иногда могут увеличить производительность с помощью специальной <xref:System.Drawing.BufferedGraphicsContext> вместо <xref:System.Drawing.BufferedGraphicsContext> , предоставляемые <xref:System.Drawing.BufferedGraphicsManager>.</span><span class="sxs-lookup"><span data-stu-id="7fd9e-111">For graphically intensive applications such as animation, you can sometimes improve performance by using a dedicated <xref:System.Drawing.BufferedGraphicsContext> instead of the <xref:System.Drawing.BufferedGraphicsContext> provided by the <xref:System.Drawing.BufferedGraphicsManager>.</span></span> <span data-ttu-id="7fd9e-112">Это позволяет создавать и управлять ими буферы графики по отдельности, без несения издержек производительности управления все другие буферизованной графики связанных с приложением, то, что память, занятая приложения будет больше.</span><span class="sxs-lookup"><span data-stu-id="7fd9e-112">This enables you to create and manage graphics buffers individually, without incurring the performance overhead of managing all the other buffered graphics associated with your application, though the memory consumed by the application will be greater.</span></span>  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a><span data-ttu-id="7fd9e-113">Чтобы создать выделенный BufferedGraphicsContext</span><span class="sxs-lookup"><span data-stu-id="7fd9e-113">To create a dedicated BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="7fd9e-114">Объявите и создайте новый экземпляр <xref:System.Drawing.BufferedGraphicsContext> класса, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="7fd9e-114">Declare and create a new instance of the <xref:System.Drawing.BufferedGraphicsContext> class, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="7fd9e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7fd9e-115">See Also</span></span>  
 <xref:System.Drawing.BufferedGraphicsContext>  
 [<span data-ttu-id="7fd9e-116">Двойная буферизация графики</span><span class="sxs-lookup"><span data-stu-id="7fd9e-116">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [<span data-ttu-id="7fd9e-117">Практическое руководство. Прорисовка буферизированной графики вручную</span><span class="sxs-lookup"><span data-stu-id="7fd9e-117">How to: Manually Render Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)
