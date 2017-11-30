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
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80eb4c3bb98acdd1f83dbf5bcf57b2f7b295742b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="using-threads-and-threading"></a><span data-ttu-id="0eb9a-102">Использование потоков и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="0eb9a-102">Using Threads and Threading</span></span>
<span data-ttu-id="0eb9a-103">В подразделах этого раздела обсуждается создание и управление управляемыми потоками, способы передачи данных в управляемые потоки и получение результатов и уничтожения потоков и обработки <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="0eb9a-103">The topics in this section discuss the creation and management of managed threads, how to pass data to managed threads and get results back, and how to destroy threads and handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0eb9a-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="0eb9a-104">In This Section</span></span>  
 [<span data-ttu-id="0eb9a-105">Создание потоков и передача данных во время запуска</span><span class="sxs-lookup"><span data-stu-id="0eb9a-105">Creating Threads and Passing Data at Start Time</span></span>](../../../docs/standard/threading/creating-threads-and-passing-data-at-start-time.md)  
 <span data-ttu-id="0eb9a-106">Обсуждение и демонстрация создания управляемых потоков, включая способы передачи данных в новые потоки и возврата данных.</span><span class="sxs-lookup"><span data-stu-id="0eb9a-106">Discusses and demonstrates the creation of managed threads, including how to pass data to new threads and how to get data back.</span></span>  
  
 [<span data-ttu-id="0eb9a-107">Приостановка и возобновление потоков</span><span class="sxs-lookup"><span data-stu-id="0eb9a-107">Pausing and Resuming Threads</span></span>](../../../docs/standard/threading/pausing-and-resuming-threads.md)  
 <span data-ttu-id="0eb9a-108">Обсуждение последствий приостановки и возобновления управляемых потоков.</span><span class="sxs-lookup"><span data-stu-id="0eb9a-108">Discusses the ramifications of pausing and resuming managed threads.</span></span>  
  
 [<span data-ttu-id="0eb9a-109">Удаление потоков</span><span class="sxs-lookup"><span data-stu-id="0eb9a-109">Destroying Threads</span></span>](../../../docs/standard/threading/destroying-threads.md)  
 <span data-ttu-id="0eb9a-110">Описание последствий уничтожения управляемых потоков и как обрабатывать <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="0eb9a-110">Discusses the ramifications of destroying managed threads, and how to handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
 [<span data-ttu-id="0eb9a-111">Планирование потоков</span><span class="sxs-lookup"><span data-stu-id="0eb9a-111">Scheduling Threads</span></span>](../../../docs/standard/threading/scheduling-threads.md)  
 <span data-ttu-id="0eb9a-112">Описание свойств потоков и их влиянии на расписание потоков.</span><span class="sxs-lookup"><span data-stu-id="0eb9a-112">Discusses thread priorities and how they affect thread scheduling.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0eb9a-113">Ссылка</span><span class="sxs-lookup"><span data-stu-id="0eb9a-113">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="0eb9a-114">Содержит справочную документацию по <xref:System.Threading.Thread> класс, который представляет управляемый поток, созданный в управляемом приложении или он получен из неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="0eb9a-114">Provides reference documentation for the <xref:System.Threading.Thread> class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.Threading.ThreadStart>  
 <span data-ttu-id="0eb9a-115">Содержит справочную документацию по <xref:System.Threading.ThreadStart> делегат, который представляет процедуры без параметров потока.</span><span class="sxs-lookup"><span data-stu-id="0eb9a-115">Provides reference documentation for the <xref:System.Threading.ThreadStart> delegate that represents parameterless thread procedures.</span></span>  
  
 <xref:System.Threading.ParameterizedThreadStart>  
 <span data-ttu-id="0eb9a-116">Предоставляет простой способ передачи данных в процедуру потока, однако без строгой типизации.</span><span class="sxs-lookup"><span data-stu-id="0eb9a-116">Provides an easy way to pass data to a thread procedure, although without strong typing.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0eb9a-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="0eb9a-117">Related Sections</span></span>  
 [<span data-ttu-id="0eb9a-118">Потоки и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="0eb9a-118">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="0eb9a-119">Знакомство с управляемыми потоками.</span><span class="sxs-lookup"><span data-stu-id="0eb9a-119">Provides an introduction to managed threading.</span></span>
