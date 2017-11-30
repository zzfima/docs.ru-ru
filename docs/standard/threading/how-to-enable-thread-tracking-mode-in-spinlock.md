---
title: "Практическое руководство. Включение режима отслеживания потоков в SpinLock"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca5f1b6eace7a24a6bbb7fd541858246828fa757
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a><span data-ttu-id="48dbf-102">Практическое руководство. Включение режима отслеживания потоков в SpinLock</span><span class="sxs-lookup"><span data-stu-id="48dbf-102">How to: Enable Thread-Tracking Mode in SpinLock</span></span>
<span data-ttu-id="48dbf-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType>Это низкоуровневая взаимно исключающая блокировка, который можно использовать для сценариев с очень короткими временами ожидания.</span><span class="sxs-lookup"><span data-stu-id="48dbf-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> is a low-level mutual exclusion lock that you can use for scenarios that have very short wait times.</span></span> <span data-ttu-id="48dbf-104"><xref:System.Threading.SpinLock>не является реентерабельным.</span><span class="sxs-lookup"><span data-stu-id="48dbf-104"><xref:System.Threading.SpinLock> is not re-entrant.</span></span> <span data-ttu-id="48dbf-105">После поток вошел в блокировку, его необходимо закрыть блокировки правильно, прежде чем он сможет войти повторно.</span><span class="sxs-lookup"><span data-stu-id="48dbf-105">After a thread enters the lock, it must exit the lock correctly before it can enter again.</span></span> <span data-ttu-id="48dbf-106">Как правило любая попытка повторно войти в блокировку может привести к взаимоблокировке и взаимоблокировки может быть очень трудно отлаживать.</span><span class="sxs-lookup"><span data-stu-id="48dbf-106">Typically, any attempt to re-enter the lock would cause deadlock, and deadlocks can be very difficult to debug.</span></span> <span data-ttu-id="48dbf-107">Как вспомогательное средство для разработки <xref:System.Threading.SpinLock?displayProperty=nameWithType> поддерживает режим отслеживания потоков, который вызывает исключение, если поток пытается повторно войти, уже удерживает блокировку.</span><span class="sxs-lookup"><span data-stu-id="48dbf-107">As an aid to development, <xref:System.Threading.SpinLock?displayProperty=nameWithType> supports a thread-tracking mode that causes an exception to be thrown when a thread attempts to re-enter a lock that it already holds.</span></span> <span data-ttu-id="48dbf-108">Это позволяет более легко обнаружить точку с которой блокировка была не завершен правильно.</span><span class="sxs-lookup"><span data-stu-id="48dbf-108">This lets you more easily locate the point at which the lock was not exited correctly.</span></span> <span data-ttu-id="48dbf-109">Режим отслеживания потоков можно включить с помощью <xref:System.Threading.SpinLock> конструктора, принимающего логический входной параметр и передачи аргумента `true`.</span><span class="sxs-lookup"><span data-stu-id="48dbf-109">You can turn on thread-tracking mode by using the <xref:System.Threading.SpinLock> constructor that takes a Boolean input parameter, and passing in an argument of `true`.</span></span> <span data-ttu-id="48dbf-110">После завершения разработки и тестирования, отключите режим отслеживания потоков для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="48dbf-110">After you complete the development and testing phases, turn off thread-tracking mode for better performance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48dbf-111">Пример</span><span class="sxs-lookup"><span data-stu-id="48dbf-111">Example</span></span>  
 <span data-ttu-id="48dbf-112">Ниже приведен пример режима отслеживания потоков.</span><span class="sxs-lookup"><span data-stu-id="48dbf-112">The following example demonstrates thread-tracking mode.</span></span> <span data-ttu-id="48dbf-113">Строки, которые правильно выходит из нее, закомментированы, чтобы сымитировать ошибку кода, приводящую к одному из следующих результатов:</span><span class="sxs-lookup"><span data-stu-id="48dbf-113">The lines that correctly exit the lock are commented out to simulate a coding error that causes one of the following results:</span></span>  
  
-   <span data-ttu-id="48dbf-114">Исключение возникает, если <xref:System.Threading.SpinLock> была создана с помощью аргумента `true` (`True` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="48dbf-114">An exception is thrown if the <xref:System.Threading.SpinLock> was created by using an argument of `true` (`True` in Visual Basic).</span></span>  
  
-   <span data-ttu-id="48dbf-115">Взаимоблокировки <xref:System.Threading.SpinLock> была создана с помощью аргумента `false` (`False` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="48dbf-115">Deadlock if the <xref:System.Threading.SpinLock> was created by using an argument of `false` (`False` in Visual Basic).</span></span>  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="48dbf-116">См. также</span><span class="sxs-lookup"><span data-stu-id="48dbf-116">See Also</span></span>  
 [<span data-ttu-id="48dbf-117">SpinLock</span><span class="sxs-lookup"><span data-stu-id="48dbf-117">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)
