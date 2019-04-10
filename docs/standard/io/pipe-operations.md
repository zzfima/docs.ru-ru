---
title: Операции с каналами в .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ba3690b6642601fd7d777e3ae1d1e34684e3b1dd
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58823562"
---
# <a name="pipe-operations-in-net"></a><span data-ttu-id="f7381-102">Операции с каналами в .NET</span><span class="sxs-lookup"><span data-stu-id="f7381-102">Pipe Operations in .NET</span></span>
<span data-ttu-id="f7381-103">Каналы предоставляют средства для межпроцессного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="f7381-103">Pipes provide a means for interprocess communication.</span></span> <span data-ttu-id="f7381-104">Существует два типа каналов.</span><span class="sxs-lookup"><span data-stu-id="f7381-104">There are two types of pipes:</span></span>  
  
-   <span data-ttu-id="f7381-105">Анонимные каналы.</span><span class="sxs-lookup"><span data-stu-id="f7381-105">Anonymous pipes.</span></span>  
  
     <span data-ttu-id="f7381-106">Анонимные каналы обеспечивают межпроцессное взаимодействие на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f7381-106">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="f7381-107">Анонимные каналы требуют меньше ресурсов, чем именованные каналы, но предоставляют меньше возможностей.</span><span class="sxs-lookup"><span data-stu-id="f7381-107">Anonymous pipes require less overhead than named pipes but offer limited services.</span></span> <span data-ttu-id="f7381-108">Анонимные каналы являются односторонними и их нельзя использовать в сети.</span><span class="sxs-lookup"><span data-stu-id="f7381-108">Anonymous pipes are one-way and cannot be used over a network.</span></span> <span data-ttu-id="f7381-109">Они поддерживают только один экземпляр сервера.</span><span class="sxs-lookup"><span data-stu-id="f7381-109">They support only a single server instance.</span></span> <span data-ttu-id="f7381-110">Анонимные каналы подходят для взаимодействия между потоками или между родительским и дочерним процессами, поскольку в этих сценариях дескриптор канала можно легко передать дочернему процессу при его создании.</span><span class="sxs-lookup"><span data-stu-id="f7381-110">Anonymous pipes are useful for communication between threads, or between parent and child processes where the pipe handles can be easily passed to the child process when it is created.</span></span>  
  
     <span data-ttu-id="f7381-111">В .NET анонимные каналы реализуются с помощью классов <xref:System.IO.Pipes.AnonymousPipeServerStream> и <xref:System.IO.Pipes.AnonymousPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="f7381-111">In .NET, you implement anonymous pipes by using the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="f7381-112">См. практическое руководство по [ Использование анонимных каналов для локального взаимодействия между процессами](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="f7381-112">See [How to: Use Anonymous Pipes for Local Interprocess Communication](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span></span>  
  
-   <span data-ttu-id="f7381-113">Именованные каналы.</span><span class="sxs-lookup"><span data-stu-id="f7381-113">Named pipes.</span></span>  
  
     <span data-ttu-id="f7381-114">Именованные каналы обеспечивают межпроцессное взаимодействие между сервером канала и одним или несколькими клиентами канала.</span><span class="sxs-lookup"><span data-stu-id="f7381-114">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="f7381-115">Именованные каналы могут быть односторонним или дуплексным.</span><span class="sxs-lookup"><span data-stu-id="f7381-115">Named pipes can be one-way or duplex.</span></span> <span data-ttu-id="f7381-116">Они поддерживают связь на основе сообщений и позволяют нескольким клиентам одновременно подключаться к одному серверному процессу через канал с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="f7381-116">They support message-based communication and allow multiple clients to connect simultaneously to the server process using the same pipe name.</span></span> <span data-ttu-id="f7381-117">Именованные каналы также поддерживают олицетворение, при котором подключенные процессы используют на удаленных серверах собственные разрешения доступа.</span><span class="sxs-lookup"><span data-stu-id="f7381-117">Named pipes also support impersonation, which enables connecting processes to use their own permissions on remote servers.</span></span>  
  
     <span data-ttu-id="f7381-118">В .NET именованные каналы реализуются с помощью классов <xref:System.IO.Pipes.NamedPipeServerStream> и <xref:System.IO.Pipes.NamedPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="f7381-118">In .NET, you implement named pipes by using the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="f7381-119">См. практическое руководство по [ Использование именованных каналов для сетевого взаимодействия между процессами](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="f7381-119">See [How to: Use Named Pipes for Network Interprocess Communication](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7381-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f7381-120">See also</span></span>

- [<span data-ttu-id="f7381-121">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="f7381-121">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
- [<span data-ttu-id="f7381-122">Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами</span><span class="sxs-lookup"><span data-stu-id="f7381-122">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
- [<span data-ttu-id="f7381-123">Практическое руководство. Использование именованных каналов для сетевого взаимодействия между процессами</span><span class="sxs-lookup"><span data-stu-id="f7381-123">How to: Use Named Pipes for Network Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
