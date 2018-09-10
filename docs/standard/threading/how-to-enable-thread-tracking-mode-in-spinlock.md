---
title: Практическое руководство. Включение режима отслеживания потоков в SpinLock
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3b9671c10889287bc22d64df1fb5c3a2984bd55
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44195284"
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a><span data-ttu-id="37054-102">Практическое руководство. Включение режима отслеживания потоков в SpinLock</span><span class="sxs-lookup"><span data-stu-id="37054-102">How to: Enable Thread-Tracking Mode in SpinLock</span></span>
<span data-ttu-id="37054-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> реализует низкоуровневую взаимоисключающую блокировку, которая применима для сценариев с очень коротким временем ожидания.</span><span class="sxs-lookup"><span data-stu-id="37054-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> is a low-level mutual exclusion lock that you can use for scenarios that have very short wait times.</span></span> <span data-ttu-id="37054-104"><xref:System.Threading.SpinLock> не допускает повторный вход.</span><span class="sxs-lookup"><span data-stu-id="37054-104"><xref:System.Threading.SpinLock> is not re-entrant.</span></span> <span data-ttu-id="37054-105">После входа потока в блокировку он обязан правильно завершить блокировку, прежде чем входить в нее повторно.</span><span class="sxs-lookup"><span data-stu-id="37054-105">After a thread enters the lock, it must exit the lock correctly before it can enter again.</span></span> <span data-ttu-id="37054-106">Как правило, любая попытка повторно войти в блокировку приводит к взаимоблокировке, что иногда очень трудно подвергается отладке.</span><span class="sxs-lookup"><span data-stu-id="37054-106">Typically, any attempt to re-enter the lock would cause deadlock, and deadlocks can be very difficult to debug.</span></span> <span data-ttu-id="37054-107">Для помощи разработчикам <xref:System.Threading.SpinLock?displayProperty=nameWithType> поддерживает режим отслеживания потоков, в котором создается исключение, когда поток пытается повторно войти в уже открытую блокировку.</span><span class="sxs-lookup"><span data-stu-id="37054-107">As an aid to development, <xref:System.Threading.SpinLock?displayProperty=nameWithType> supports a thread-tracking mode that causes an exception to be thrown when a thread attempts to re-enter a lock that it already holds.</span></span> <span data-ttu-id="37054-108">Это позволяет быстрее найти точку, в которой неправильно выполнен выход из блокировки.</span><span class="sxs-lookup"><span data-stu-id="37054-108">This lets you more easily locate the point at which the lock was not exited correctly.</span></span> <span data-ttu-id="37054-109">Чтобы включить режим отслеживания потоков, используйте конструктор <xref:System.Threading.SpinLock>, который принимает на вход логический параметр, в котором следует передать значение `true`.</span><span class="sxs-lookup"><span data-stu-id="37054-109">You can turn on thread-tracking mode by using the <xref:System.Threading.SpinLock> constructor that takes a Boolean input parameter, and passing in an argument of `true`.</span></span> <span data-ttu-id="37054-110">Завершив все этапы разработки и тестирования, обязательно отключите режим отслеживания потоков, чтобы он не влиял на производительность.</span><span class="sxs-lookup"><span data-stu-id="37054-110">After you complete the development and testing phases, turn off thread-tracking mode for better performance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37054-111">Пример</span><span class="sxs-lookup"><span data-stu-id="37054-111">Example</span></span>  
 <span data-ttu-id="37054-112">В примере ниже демонстрируется режим отслеживания потоков.</span><span class="sxs-lookup"><span data-stu-id="37054-112">The following example demonstrates thread-tracking mode.</span></span> <span data-ttu-id="37054-113">Здесь закомментированы строки, в которых блокировка завершена правильно, чтобы смоделировать ошибку, приводящую к одному из следующих результатов:</span><span class="sxs-lookup"><span data-stu-id="37054-113">The lines that correctly exit the lock are commented out to simulate a coding error that causes one of the following results:</span></span>  
  
-   <span data-ttu-id="37054-114">Создается исключение, если <xref:System.Threading.SpinLock> создан с аргументом `true` (`True` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="37054-114">An exception is thrown if the <xref:System.Threading.SpinLock> was created by using an argument of `true` (`True` in Visual Basic).</span></span>  
  
-   <span data-ttu-id="37054-115">Возникает взаимоблокировка, если <xref:System.Threading.SpinLock> создан с аргументом `false` (`False` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="37054-115">Deadlock if the <xref:System.Threading.SpinLock> was created by using an argument of `false` (`False` in Visual Basic).</span></span>  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="37054-116">См. также</span><span class="sxs-lookup"><span data-stu-id="37054-116">See also</span></span>

- [<span data-ttu-id="37054-117">SpinLock</span><span class="sxs-lookup"><span data-stu-id="37054-117">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)
