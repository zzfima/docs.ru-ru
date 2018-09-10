---
title: Операции с каналами в .NET Framework
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
ms.openlocfilehash: fdc12091a377a118dc533e5f299fa4833af64baf
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44081873"
---
# <a name="pipe-operations-in-the-net-framework"></a><span data-ttu-id="6569d-102">Операции с каналами в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6569d-102">Pipe Operations in the .NET Framework</span></span>
<span data-ttu-id="6569d-103">Каналы предоставляют средства для межпроцессного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="6569d-103">Pipes provide a means for interprocess communication.</span></span> <span data-ttu-id="6569d-104">Существует два типа каналов.</span><span class="sxs-lookup"><span data-stu-id="6569d-104">There are two types of pipes:</span></span>  
  
-   <span data-ttu-id="6569d-105">Анонимные каналы.</span><span class="sxs-lookup"><span data-stu-id="6569d-105">Anonymous pipes.</span></span>  
  
     <span data-ttu-id="6569d-106">Анонимные каналы обеспечивают межпроцессное взаимодействие на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6569d-106">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="6569d-107">Анонимные каналы требуют меньше ресурсов, чем именованные каналы, но предоставляют меньше возможностей.</span><span class="sxs-lookup"><span data-stu-id="6569d-107">Anonymous pipes require less overhead than named pipes but offer limited services.</span></span> <span data-ttu-id="6569d-108">Анонимные каналы являются односторонними и их нельзя использовать в сети.</span><span class="sxs-lookup"><span data-stu-id="6569d-108">Anonymous pipes are one-way and cannot be used over a network.</span></span> <span data-ttu-id="6569d-109">Они поддерживают только один экземпляр сервера.</span><span class="sxs-lookup"><span data-stu-id="6569d-109">They support only a single server instance.</span></span> <span data-ttu-id="6569d-110">Анонимные каналы подходят для взаимодействия между потоками или между родительским и дочерним процессами, поскольку в этих сценариях дескриптор канала можно легко передать дочернему процессу при его создании.</span><span class="sxs-lookup"><span data-stu-id="6569d-110">Anonymous pipes are useful for communication between threads, or between parent and child processes where the pipe handles can be easily passed to the child process when it is created.</span></span>  
  
     <span data-ttu-id="6569d-111">На платформе .NET Framework анонимные каналы реализуются через классы <xref:System.IO.Pipes.AnonymousPipeServerStream> и <xref:System.IO.Pipes.AnonymousPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="6569d-111">In the .NET Framework, you implement anonymous pipes by using the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="6569d-112">Дополнительные сведения см. в статье [Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="6569d-112">See [How to: Use Anonymous Pipes for Local Interprocess Communication](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span></span>  
  
-   <span data-ttu-id="6569d-113">Именованные каналы.</span><span class="sxs-lookup"><span data-stu-id="6569d-113">Named pipes.</span></span>  
  
     <span data-ttu-id="6569d-114">Именованные каналы обеспечивают межпроцессное взаимодействие между сервером канала и одним или несколькими клиентами канала.</span><span class="sxs-lookup"><span data-stu-id="6569d-114">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="6569d-115">Именованные каналы могут быть односторонним или дуплексным.</span><span class="sxs-lookup"><span data-stu-id="6569d-115">Named pipes can be one-way or duplex.</span></span> <span data-ttu-id="6569d-116">Они поддерживают связь на основе сообщений и позволяют нескольким клиентам одновременно подключаться к одному серверному процессу через канал с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="6569d-116">They support message-based communication and allow multiple clients to connect simultaneously to the server process using the same pipe name.</span></span> <span data-ttu-id="6569d-117">Именованные каналы также поддерживают олицетворение, при котором подключенные процессы используют на удаленных серверах собственные разрешения доступа.</span><span class="sxs-lookup"><span data-stu-id="6569d-117">Named pipes also support impersonation, which enables connecting processes to use their own permissions on remote servers.</span></span>  
  
     <span data-ttu-id="6569d-118">На платформе .NET Framework именованные каналы реализуются через классы <xref:System.IO.Pipes.NamedPipeServerStream> и <xref:System.IO.Pipes.NamedPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="6569d-118">In the .NET Framework, you implement named pipes by using the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="6569d-119">Дополнительные сведения см. в статье [Практическое руководство. Использование именованных каналов для взаимодействия между процессами по сети](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="6569d-119">See [How to: Use Named Pipes for Network Interprocess Communication](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6569d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6569d-120">See also</span></span>

- [<span data-ttu-id="6569d-121">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="6569d-121">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)  
- [<span data-ttu-id="6569d-122">Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами</span><span class="sxs-lookup"><span data-stu-id="6569d-122">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)  
- [<span data-ttu-id="6569d-123">Практическое руководство. Использование именованных каналов для сетевого взаимодействия между процессами</span><span class="sxs-lookup"><span data-stu-id="6569d-123">How to: Use Named Pipes for Network Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
