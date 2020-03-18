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
ms.openlocfilehash: f52a844284cf46bcace3f54f8b320d336050a64e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138035"
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a><span data-ttu-id="cb283-102">Практическое руководство. Включение режима отслеживания потоков в SpinLock</span><span class="sxs-lookup"><span data-stu-id="cb283-102">How to: Enable Thread-Tracking Mode in SpinLock</span></span>
<span data-ttu-id="cb283-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> реализует низкоуровневую взаимоисключающую блокировку, которая применима для сценариев с очень коротким временем ожидания.</span><span class="sxs-lookup"><span data-stu-id="cb283-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> is a low-level mutual exclusion lock that you can use for scenarios that have very short wait times.</span></span> <span data-ttu-id="cb283-104"><xref:System.Threading.SpinLock> не допускает повторный вход.</span><span class="sxs-lookup"><span data-stu-id="cb283-104"><xref:System.Threading.SpinLock> is not re-entrant.</span></span> <span data-ttu-id="cb283-105">После входа потока в блокировку он обязан правильно завершить блокировку, прежде чем входить в нее повторно.</span><span class="sxs-lookup"><span data-stu-id="cb283-105">After a thread enters the lock, it must exit the lock correctly before it can enter again.</span></span> <span data-ttu-id="cb283-106">Как правило, любая попытка повторно войти в блокировку приводит к взаимоблокировке, что иногда очень трудно подвергается отладке.</span><span class="sxs-lookup"><span data-stu-id="cb283-106">Typically, any attempt to re-enter the lock would cause deadlock, and deadlocks can be very difficult to debug.</span></span> <span data-ttu-id="cb283-107">Для помощи разработчикам <xref:System.Threading.SpinLock?displayProperty=nameWithType> поддерживает режим отслеживания потоков, в котором создается исключение, когда поток пытается повторно войти в уже открытую блокировку.</span><span class="sxs-lookup"><span data-stu-id="cb283-107">As an aid to development, <xref:System.Threading.SpinLock?displayProperty=nameWithType> supports a thread-tracking mode that causes an exception to be thrown when a thread attempts to re-enter a lock that it already holds.</span></span> <span data-ttu-id="cb283-108">Это позволяет быстрее найти точку, в которой неправильно выполнен выход из блокировки.</span><span class="sxs-lookup"><span data-stu-id="cb283-108">This lets you more easily locate the point at which the lock was not exited correctly.</span></span> <span data-ttu-id="cb283-109">Чтобы включить режим отслеживания потоков, используйте конструктор <xref:System.Threading.SpinLock>, который принимает на вход логический параметр, в котором следует передать значение `true`.</span><span class="sxs-lookup"><span data-stu-id="cb283-109">You can turn on thread-tracking mode by using the <xref:System.Threading.SpinLock> constructor that takes a Boolean input parameter, and passing in an argument of `true`.</span></span> <span data-ttu-id="cb283-110">Завершив все этапы разработки и тестирования, обязательно отключите режим отслеживания потоков, чтобы он не влиял на производительность.</span><span class="sxs-lookup"><span data-stu-id="cb283-110">After you complete the development and testing phases, turn off thread-tracking mode for better performance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb283-111">Пример</span><span class="sxs-lookup"><span data-stu-id="cb283-111">Example</span></span>  
 <span data-ttu-id="cb283-112">В примере ниже демонстрируется режим отслеживания потоков.</span><span class="sxs-lookup"><span data-stu-id="cb283-112">The following example demonstrates thread-tracking mode.</span></span> <span data-ttu-id="cb283-113">Здесь закомментированы строки, в которых блокировка завершена правильно, чтобы смоделировать ошибку, приводящую к одному из следующих результатов:</span><span class="sxs-lookup"><span data-stu-id="cb283-113">The lines that correctly exit the lock are commented out to simulate a coding error that causes one of the following results:</span></span>  
  
- <span data-ttu-id="cb283-114">Создается исключение, если <xref:System.Threading.SpinLock> создан с аргументом `true` (`True` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="cb283-114">An exception is thrown if the <xref:System.Threading.SpinLock> was created by using an argument of `true` (`True` in Visual Basic).</span></span>  
  
- <span data-ttu-id="cb283-115">Возникает взаимоблокировка, если <xref:System.Threading.SpinLock> создан с аргументом `false` (`False` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="cb283-115">Deadlock if the <xref:System.Threading.SpinLock> was created by using an argument of `false` (`False` in Visual Basic).</span></span>  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="cb283-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cb283-116">See also</span></span>

- [<span data-ttu-id="cb283-117">SpinLock</span><span class="sxs-lookup"><span data-stu-id="cb283-117">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)
