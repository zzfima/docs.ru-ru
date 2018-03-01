---
title: "Использование потоков и работа с потоками"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 9b5ec2cd-121b-4d49-b075-222cf26f2344
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5bed13950a29cfa787ef8c9eb2608c6d74dfd49f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="using-threads-and-threading"></a><span data-ttu-id="476f2-102">Использование потоков и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="476f2-102">Using Threads and Threading</span></span>
<span data-ttu-id="476f2-103">В статьях этого раздела мы обсуждаем создание управляемых потоков и управление ими, передачу данных в управляемые потоки и получение из них результатов, а также уничтожение потоков и обработку <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="476f2-103">The topics in this section discuss the creation and management of managed threads, how to pass data to managed threads and get results back, and how to destroy threads and handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="476f2-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="476f2-104">In This Section</span></span>  
 [<span data-ttu-id="476f2-105">Создание потоков и передача данных во время запуска</span><span class="sxs-lookup"><span data-stu-id="476f2-105">Creating Threads and Passing Data at Start Time</span></span>](../../../docs/standard/threading/creating-threads-and-passing-data-at-start-time.md)  
 <span data-ttu-id="476f2-106">Обсуждается и демонстрируется создание управляемых потоков, в том числе способы передать данные в новые потоки и получить данные из них.</span><span class="sxs-lookup"><span data-stu-id="476f2-106">Discusses and demonstrates the creation of managed threads, including how to pass data to new threads and how to get data back.</span></span>  
  
 [<span data-ttu-id="476f2-107">Приостановка и возобновление потоков</span><span class="sxs-lookup"><span data-stu-id="476f2-107">Pausing and Resuming Threads</span></span>](../../../docs/standard/threading/pausing-and-resuming-threads.md)  
 <span data-ttu-id="476f2-108">Обсуждаются сложности при приостановке и возобновлении управляемых потоков.</span><span class="sxs-lookup"><span data-stu-id="476f2-108">Discusses the ramifications of pausing and resuming managed threads.</span></span>  
  
 [<span data-ttu-id="476f2-109">Удаление потоков</span><span class="sxs-lookup"><span data-stu-id="476f2-109">Destroying Threads</span></span>](../../../docs/standard/threading/destroying-threads.md)  
 <span data-ttu-id="476f2-110">Обсуждаются сложности при уничтожении управляемых потоков и обработка <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="476f2-110">Discusses the ramifications of destroying managed threads, and how to handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
 [<span data-ttu-id="476f2-111">Планирование потоков</span><span class="sxs-lookup"><span data-stu-id="476f2-111">Scheduling Threads</span></span>](../../../docs/standard/threading/scheduling-threads.md)  
 <span data-ttu-id="476f2-112">Обсуждаются приоритеты потоков и их влияние на выполнение потоков.</span><span class="sxs-lookup"><span data-stu-id="476f2-112">Discusses thread priorities and how they affect thread scheduling.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="476f2-113">Ссылка</span><span class="sxs-lookup"><span data-stu-id="476f2-113">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="476f2-114">Справочная документация по классу <xref:System.Threading.Thread>, который представляет управляемый поток, созданный из неуправляемого кода или в управляемом приложении.</span><span class="sxs-lookup"><span data-stu-id="476f2-114">Provides reference documentation for the <xref:System.Threading.Thread> class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.Threading.ThreadStart>  
 <span data-ttu-id="476f2-115">Справочная документация по делегату <xref:System.Threading.ThreadStart>, который представляет процедуры потоков без параметров.</span><span class="sxs-lookup"><span data-stu-id="476f2-115">Provides reference documentation for the <xref:System.Threading.ThreadStart> delegate that represents parameterless thread procedures.</span></span>  
  
 <xref:System.Threading.ParameterizedThreadStart>  
 <span data-ttu-id="476f2-116">Предоставляет простой способ передать данные в процедуру потока, но не поддерживает строгую типизацию.</span><span class="sxs-lookup"><span data-stu-id="476f2-116">Provides an easy way to pass data to a thread procedure, although without strong typing.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="476f2-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="476f2-117">Related Sections</span></span>  
 [<span data-ttu-id="476f2-118">Потоки и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="476f2-118">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="476f2-119">Общие сведения о работе с управляемыми потоками.</span><span class="sxs-lookup"><span data-stu-id="476f2-119">Provides an introduction to managed threading.</span></span>
