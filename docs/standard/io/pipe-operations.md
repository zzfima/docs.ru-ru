---
title: "Операции с каналами в .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 879e5a73417f9347224bc22b397814b83972751c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="pipe-operations-in-the-net-framework"></a><span data-ttu-id="cead2-102">Операции с каналами в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cead2-102">Pipe Operations in the .NET Framework</span></span>
<span data-ttu-id="cead2-103">Каналы предоставляют средства для межпроцессного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="cead2-103">Pipes provide a means for interprocess communication.</span></span> <span data-ttu-id="cead2-104">Существует два типа каналов:</span><span class="sxs-lookup"><span data-stu-id="cead2-104">There are two types of pipes:</span></span>  
  
-   <span data-ttu-id="cead2-105">Анонимные каналы.</span><span class="sxs-lookup"><span data-stu-id="cead2-105">Anonymous pipes.</span></span>  
  
     <span data-ttu-id="cead2-106">Анонимные каналы обеспечивают межпроцессное взаимодействие на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cead2-106">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="cead2-107">Анонимные каналы требует меньше ресурсов, чем именованные каналы, но возможности ограничены.</span><span class="sxs-lookup"><span data-stu-id="cead2-107">Anonymous pipes require less overhead than named pipes but offer limited services.</span></span> <span data-ttu-id="cead2-108">Анонимные каналы являются односторонними и не может использоваться в сети.</span><span class="sxs-lookup"><span data-stu-id="cead2-108">Anonymous pipes are one-way and cannot be used over a network.</span></span> <span data-ttu-id="cead2-109">Они поддерживают только один экземпляр сервера.</span><span class="sxs-lookup"><span data-stu-id="cead2-109">They support only a single server instance.</span></span> <span data-ttu-id="cead2-110">Анонимные каналы полезны для взаимодействия между потоками или между родительским и дочерним процессами, где дескриптор канала можно легко передать дочернему процессу при его создании.</span><span class="sxs-lookup"><span data-stu-id="cead2-110">Anonymous pipes are useful for communication between threads, or between parent and child processes where the pipe handles can be easily passed to the child process when it is created.</span></span>  
  
     <span data-ttu-id="cead2-111">В платформе .NET Framework с помощью реализации анонимных каналов <xref:System.IO.Pipes.AnonymousPipeServerStream> и <xref:System.IO.Pipes.AnonymousPipeClientStream> классы.</span><span class="sxs-lookup"><span data-stu-id="cead2-111">In the .NET Framework, you implement anonymous pipes by using the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="cead2-112">В разделе [как: использование анонимных каналов для локального взаимодействия между процессами](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="cead2-112">See [How to: Use Anonymous Pipes for Local Interprocess Communication](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span></span>  
  
-   <span data-ttu-id="cead2-113">Именованные каналы.</span><span class="sxs-lookup"><span data-stu-id="cead2-113">Named pipes.</span></span>  
  
     <span data-ttu-id="cead2-114">Именованные каналы обеспечивают межпроцессное взаимодействие между сервером и одной или несколькими клиентами.</span><span class="sxs-lookup"><span data-stu-id="cead2-114">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="cead2-115">Именованные каналы могут быть односторонним или дуплексным.</span><span class="sxs-lookup"><span data-stu-id="cead2-115">Named pipes can be one-way or duplex.</span></span> <span data-ttu-id="cead2-116">Они поддерживают связь на основе сообщений и разрешить нескольким клиентам одновременно подключаться к серверному процессу, используя то же имя канала.</span><span class="sxs-lookup"><span data-stu-id="cead2-116">They support message-based communication and allow multiple clients to connect simultaneously to the server process using the same pipe name.</span></span> <span data-ttu-id="cead2-117">Именованные каналы также поддерживают олицетворение, позволяющее подключающимся процессам использовать собственные разрешения на удаленных серверах.</span><span class="sxs-lookup"><span data-stu-id="cead2-117">Named pipes also support impersonation, which enables connecting processes to use their own permissions on remote servers.</span></span>  
  
     <span data-ttu-id="cead2-118">В .NET Framework, именованные каналы реализуются с помощью <xref:System.IO.Pipes.NamedPipeServerStream> и <xref:System.IO.Pipes.NamedPipeClientStream> классы.</span><span class="sxs-lookup"><span data-stu-id="cead2-118">In the .NET Framework, you implement named pipes by using the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="cead2-119">В разделе [как: использование именованных каналов для сетевого взаимодействия между процессами](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="cead2-119">See [How to: Use Named Pipes for Network Interprocess Communication](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cead2-120">См. также</span><span class="sxs-lookup"><span data-stu-id="cead2-120">See Also</span></span>  
 [<span data-ttu-id="cead2-121">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="cead2-121">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)  
 [<span data-ttu-id="cead2-122">Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами</span><span class="sxs-lookup"><span data-stu-id="cead2-122">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)  
 [<span data-ttu-id="cead2-123">Практическое руководство. Использование именованных каналов для сетевого взаимодействия между процессами</span><span class="sxs-lookup"><span data-stu-id="cead2-123">How to: Use Named Pipes for Network Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
