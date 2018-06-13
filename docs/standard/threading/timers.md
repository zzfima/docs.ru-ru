---
title: таймеры
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 478484651bf839f842148f0b4164c9387db3b98a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584961"
---
# <a name="timers"></a><span data-ttu-id="529ee-102">таймеры</span><span class="sxs-lookup"><span data-stu-id="529ee-102">Timers</span></span>
<span data-ttu-id="529ee-103">Таймеры являются простыми объектами, которые позволяют указать делегат для вызова в заданное время.</span><span class="sxs-lookup"><span data-stu-id="529ee-103">Timers are lightweight objects that enable you to specify a delegate to be called at a specified time.</span></span> <span data-ttu-id="529ee-104">Поток в пуле потоков выполняет операцию ожидания.</span><span class="sxs-lookup"><span data-stu-id="529ee-104">A thread in the thread pool performs the wait operation.</span></span>  
  
 <span data-ttu-id="529ee-105">Работа с классом <xref:System.Threading.Timer?displayProperty=nameWithType> не имеет никаких сложностей.</span><span class="sxs-lookup"><span data-stu-id="529ee-105">Using the <xref:System.Threading.Timer?displayProperty=nameWithType> class is straightforward.</span></span> <span data-ttu-id="529ee-106">Вы создаете **таймер**, передав делегат <xref:System.Threading.TimerCallback> для метода обратного вызова, объект состояния, который будет передан при обратном вызове, время первого вызова и длительность периода между последующими обратными вызовами.</span><span class="sxs-lookup"><span data-stu-id="529ee-106">You create a **Timer**, passing a <xref:System.Threading.TimerCallback> delegate to the callback method, an object representing state that will be passed to the callback, an initial raise time, and a time representing the period between callback invocations.</span></span> <span data-ttu-id="529ee-107">Чтобы отменить ожидающий таймер, вызовите функцию **Timer.Dispose**.</span><span class="sxs-lookup"><span data-stu-id="529ee-107">To cancel a pending timer, call the **Timer.Dispose** function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="529ee-108">Есть еще два класса таймера с другими возможностями.</span><span class="sxs-lookup"><span data-stu-id="529ee-108">There are two other timer classes.</span></span> <span data-ttu-id="529ee-109">Класс <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> представляет собой элемент управления, который используется в визуальных конструкторах, то есть в контекстах пользовательского интерфейса. Он создает события в потоке пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="529ee-109">The <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> class is a control that works with visual designers and is meant to be used in user interface contexts; it raises events on the user interface thread.</span></span> <span data-ttu-id="529ee-110">Класс <xref:System.Timers.Timer?displayProperty=nameWithType> является производным от <xref:System.ComponentModel.Component>, а значит может использоваться в визуальных конструкторах. Он также создает события, но уже в потоке <xref:System.Threading.ThreadPool>.</span><span class="sxs-lookup"><span data-stu-id="529ee-110">The <xref:System.Timers.Timer?displayProperty=nameWithType> class derives from <xref:System.ComponentModel.Component>, so it can be used with visual designers; it also raises events, but it raises them on a <xref:System.Threading.ThreadPool> thread.</span></span> <span data-ttu-id="529ee-111">Класс <xref:System.Threading.Timer?displayProperty=nameWithType> выполняет обратные вызовы в потоке <xref:System.Threading.ThreadPool> и никак не использует модель события.</span><span class="sxs-lookup"><span data-stu-id="529ee-111">The <xref:System.Threading.Timer?displayProperty=nameWithType> class makes callbacks on a <xref:System.Threading.ThreadPool> thread and does not use the event model at all.</span></span> <span data-ttu-id="529ee-112">Он также передает в метод обратного вызова объект состояния, чего не делают другие таймеры.</span><span class="sxs-lookup"><span data-stu-id="529ee-112">It also provides a state object to the callback method, which the other timers do not.</span></span> <span data-ttu-id="529ee-113">Он требует совсем немного ресурсов.</span><span class="sxs-lookup"><span data-stu-id="529ee-113">It is extremely lightweight.</span></span>  
  
 <span data-ttu-id="529ee-114">В следующем примере кода запускается таймер, который начинает работу через одну секунду (1000 миллисекунд) и срабатывает каждую секунду, пока пользователь не нажмет клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="529ee-114">The following code example starts a timer that starts after one second (1000 milliseconds) and ticks every second until you press the **Enter** key.</span></span> <span data-ttu-id="529ee-115">Переменная со ссылкой на таймер является полем уровня класса, чтобы таймер не пострадал от сборки мусора, пока не закончит свою работу.</span><span class="sxs-lookup"><span data-stu-id="529ee-115">The variable containing the reference to the timer is a class-level field, to ensure that the timer is not subject to garbage collection while it is still running.</span></span> <span data-ttu-id="529ee-116">Дополнительные сведения об агрессивной сборке мусора см. в статье <xref:System.GC.KeepAlive%2A>.</span><span class="sxs-lookup"><span data-stu-id="529ee-116">For more information on aggressive garbage collection, see <xref:System.GC.KeepAlive%2A>.</span></span>  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="529ee-117">См. также</span><span class="sxs-lookup"><span data-stu-id="529ee-117">See Also</span></span>  
 <xref:System.Threading.Timer>  
 [<span data-ttu-id="529ee-118">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="529ee-118">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
