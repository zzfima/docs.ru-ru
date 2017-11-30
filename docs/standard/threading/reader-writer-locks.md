---
title: "Блокировки чтения и записи"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df06e83165906199774f99de4140ace9b7396cbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="reader-writer-locks"></a><span data-ttu-id="d7495-102">Блокировки чтения и записи</span><span class="sxs-lookup"><span data-stu-id="d7495-102">Reader-Writer Locks</span></span>
<span data-ttu-id="d7495-103"><xref:System.Threading.ReaderWriterLockSlim> Класс позволяет нескольким потокам чтение ресурса, но требует поток ждать монопольную блокировку для записи ресурса.</span><span class="sxs-lookup"><span data-stu-id="d7495-103">The <xref:System.Threading.ReaderWriterLockSlim> class enables multiple threads to read a resource concurrently, but requires a thread to wait for an exclusive lock in order to write to the resource.</span></span>  
  
 <span data-ttu-id="d7495-104">Можно использовать <xref:System.Threading.ReaderWriterLockSlim> в приложении для обеспечения синхронизации доступа к общему ресурсу между потоками.</span><span class="sxs-lookup"><span data-stu-id="d7495-104">You might use a <xref:System.Threading.ReaderWriterLockSlim> in your application to provide cooperative synchronization among threads that access a shared resource.</span></span> <span data-ttu-id="d7495-105">Блокировки <xref:System.Threading.ReaderWriterLockSlim> сам.</span><span class="sxs-lookup"><span data-stu-id="d7495-105">Locks are taken on the <xref:System.Threading.ReaderWriterLockSlim> itself.</span></span>  
  
 <span data-ttu-id="d7495-106">Как в любом механизме синхронизации, необходимо убедиться, что потоки не обходят блокировку, предоставляемая <xref:System.Threading.ReaderWriterLockSlim>.</span><span class="sxs-lookup"><span data-stu-id="d7495-106">As with any thread synchronization mechanism, you must ensure that no threads bypass the locking that is provided by <xref:System.Threading.ReaderWriterLockSlim>.</span></span> <span data-ttu-id="d7495-107">Один из способов сделать это является разработка класса, который инкапсулирует общий ресурс.</span><span class="sxs-lookup"><span data-stu-id="d7495-107">One way to ensure this is to design a class that encapsulates the shared resource.</span></span> <span data-ttu-id="d7495-108">Этот класс должен предоставлять элементы, доступ к закрытому общему ресурсу и используют закрытый <xref:System.Threading.ReaderWriterLockSlim> для синхронизации.</span><span class="sxs-lookup"><span data-stu-id="d7495-108">This class would provide members that access the private shared resource and that use a private <xref:System.Threading.ReaderWriterLockSlim> for synchronization.</span></span> <span data-ttu-id="d7495-109">Например, см. пример кода для <xref:System.Threading.ReaderWriterLockSlim> класса.</span><span class="sxs-lookup"><span data-stu-id="d7495-109">For an example, see the code example for the <xref:System.Threading.ReaderWriterLockSlim> class.</span></span> <span data-ttu-id="d7495-110"><xref:System.Threading.ReaderWriterLockSlim>является эффективным, который будет использоваться для синхронизации отдельных объектов.</span><span class="sxs-lookup"><span data-stu-id="d7495-110"><xref:System.Threading.ReaderWriterLockSlim> is efficient enough to be used to synchronize individual objects.</span></span>  
  
 <span data-ttu-id="d7495-111">Приложение для уменьшить время чтения и записи операций.</span><span class="sxs-lookup"><span data-stu-id="d7495-111">Structure your application to minimize the duration of read and write operations.</span></span> <span data-ttu-id="d7495-112">Длительные операции записи непосредственно влияет пропускной способности, поскольку блокировка записи является взаимоисключающей.</span><span class="sxs-lookup"><span data-stu-id="d7495-112">Long write operations affect throughput directly because the write lock is exclusive.</span></span> <span data-ttu-id="d7495-113">Длинная чтение операций блокируют ожидающие средства записи, а если хотя бы один поток для записи, потоки, запрашивающие доступ для чтения также будут заблокированы.</span><span class="sxs-lookup"><span data-stu-id="d7495-113">Long read operations block waiting writers, and if at least one thread is waiting for write access, threads that request read access will be blocked as well.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7495-114">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Имеет два блокировки чтения и записи, <xref:System.Threading.ReaderWriterLockSlim> и <xref:System.Threading.ReaderWriterLock>.</span><span class="sxs-lookup"><span data-stu-id="d7495-114">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] has two reader-writer locks, <xref:System.Threading.ReaderWriterLockSlim> and <xref:System.Threading.ReaderWriterLock>.</span></span> <span data-ttu-id="d7495-115"><xref:System.Threading.ReaderWriterLockSlim>рекомендуется для всех новых разработках.</span><span class="sxs-lookup"><span data-stu-id="d7495-115"><xref:System.Threading.ReaderWriterLockSlim> is recommended for all new development.</span></span> <span data-ttu-id="d7495-116"><xref:System.Threading.ReaderWriterLockSlim>Аналогично <xref:System.Threading.ReaderWriterLock>, но использует упрощенные правила рекурсии и повышения или понижения уровня состояния блокировки.</span><span class="sxs-lookup"><span data-stu-id="d7495-116"><xref:System.Threading.ReaderWriterLockSlim> is similar to <xref:System.Threading.ReaderWriterLock>, but it has simplified rules for recursion and for upgrading and downgrading lock state.</span></span> <span data-ttu-id="d7495-117"><xref:System.Threading.ReaderWriterLockSlim>позволяет избежать многих случаях потенциальной взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="d7495-117"><xref:System.Threading.ReaderWriterLockSlim> avoids many cases of potential deadlock.</span></span> <span data-ttu-id="d7495-118">Кроме того, производительность <xref:System.Threading.ReaderWriterLockSlim> значительно лучше, чем <xref:System.Threading.ReaderWriterLock>.</span><span class="sxs-lookup"><span data-stu-id="d7495-118">In addition, the performance of <xref:System.Threading.ReaderWriterLockSlim> is significantly better than <xref:System.Threading.ReaderWriterLock>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7495-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d7495-119">See Also</span></span>  
 <xref:System.Threading.ReaderWriterLockSlim>  
 <xref:System.Threading.ReaderWriterLock>  
 [<span data-ttu-id="d7495-120">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="d7495-120">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="d7495-121">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="d7495-121">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
