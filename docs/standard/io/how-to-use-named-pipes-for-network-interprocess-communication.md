---
title: "Практическое руководство. Использование именованных каналов для взаимодействия между процессами по сети"
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
- cpp
helpviewer_keywords:
- message-based communication [.NET Framework], named pipes
- named pipes [.NET Framework]
- pipes [.NET Framework]
- multiple connections via named pipes
- network communications [.NET Framework], named pipes
- impersonation [.NET Framework], named pipes
- full duplex communcation [.NET Framework], named pipes
ms.assetid: 4e4d7e64-9f1b-4026-98f7-20488ac7b42b
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 952600e71311184c4a4f906734addbf335d0358a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a><span data-ttu-id="cdbb2-102">Практическое руководство. Использование именованных каналов для взаимодействия между процессами по сети</span><span class="sxs-lookup"><span data-stu-id="cdbb2-102">How to: Use Named Pipes for Network Interprocess Communication</span></span>
<span data-ttu-id="cdbb2-103">Именованные каналы обеспечивают межпроцессное взаимодействие между сервером и одной или несколькими клиентами.</span><span class="sxs-lookup"><span data-stu-id="cdbb2-103">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="cdbb2-104">Они предоставляют больше функциональных возможностей, чем анонимные каналы, которые обеспечивают межпроцессное взаимодействие на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cdbb2-104">They offer more functionality than anonymous pipes, which provide interprocess communication on a local computer.</span></span> <span data-ttu-id="cdbb2-105">Именованные каналы поддерживают полную дуплексную связь по сети и несколько экземпляров сервера, связь на основе сообщений и олицетворение клиента, позволяющее подключающимся процессам использовать собственные наборы разрешений на удаленных серверах.</span><span class="sxs-lookup"><span data-stu-id="cdbb2-105">Named pipes support full duplex communication over a network and multiple server instances, message-based communication, and client impersonation, which enables connecting processes to use their own set of permissions on remote servers.</span></span>  
  
 <span data-ttu-id="cdbb2-106">Для реализации именованных каналов используются классы <xref:System.IO.Pipes.NamedPipeServerStream> и <xref:System.IO.Pipes.NamedPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="cdbb2-106">To implement name pipes, use the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdbb2-107">Пример</span><span class="sxs-lookup"><span data-stu-id="cdbb2-107">Example</span></span>  
 <span data-ttu-id="cdbb2-108">Следующий пример демонстрирует создание именованного канала с помощью <xref:System.IO.Pipes.NamedPipeServerStream> класса.</span><span class="sxs-lookup"><span data-stu-id="cdbb2-108">The following example demonstrates how to create a named pipe by using the <xref:System.IO.Pipes.NamedPipeServerStream> class.</span></span> <span data-ttu-id="cdbb2-109">В этом примере серверный процесс создает четыре потока.</span><span class="sxs-lookup"><span data-stu-id="cdbb2-109">In this example, the server process creates four threads.</span></span> <span data-ttu-id="cdbb2-110">Каждый поток может принимать подключения клиента.</span><span class="sxs-lookup"><span data-stu-id="cdbb2-110">Each thread can accept a client connection.</span></span> <span data-ttu-id="cdbb2-111">Процесс подключенный клиент предоставляет сервера с именем файла.</span><span class="sxs-lookup"><span data-stu-id="cdbb2-111">The connected client process then supplies the server with a file name.</span></span> <span data-ttu-id="cdbb2-112">Если клиент имеет достаточные разрешения, серверный процесс открывает файл и отправляет его содержимое обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="cdbb2-112">If the client has sufficient permissions, the server process opens the file and sends its contents back to the client.</span></span>  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="cdbb2-113">Пример</span><span class="sxs-lookup"><span data-stu-id="cdbb2-113">Example</span></span>  
 <span data-ttu-id="cdbb2-114">В следующем примере показано клиентского процесса, который использует <xref:System.IO.Pipes.NamedPipeClientStream> класса.</span><span class="sxs-lookup"><span data-stu-id="cdbb2-114">The following example shows the client process, which uses the <xref:System.IO.Pipes.NamedPipeClientStream> class.</span></span> <span data-ttu-id="cdbb2-115">Клиент подключается к серверному процессу и отправляет имя файла на сервер.</span><span class="sxs-lookup"><span data-stu-id="cdbb2-115">The client connects to the server process and sends a file name to the server.</span></span> <span data-ttu-id="cdbb2-116">В примере используется олицетворение, поэтому удостоверение, на котором работает клиентское приложение должно иметь разрешение на доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="cdbb2-116">The example uses impersonation, so the identity that is running the client application must have permission to access the file.</span></span> <span data-ttu-id="cdbb2-117">Затем сервер отправляет содержимое файла обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="cdbb2-117">The server then sends the contents of the file back to the client.</span></span> <span data-ttu-id="cdbb2-118">Затем содержимое файла отображаются на консоль.</span><span class="sxs-lookup"><span data-stu-id="cdbb2-118">The file contents are then displayed to the console.</span></span>  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a><span data-ttu-id="cdbb2-119">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="cdbb2-119">Robust Programming</span></span>  
 <span data-ttu-id="cdbb2-120">Клиентские и серверные процессы в этом примере предназначены для запуска на том же компьютере, поэтому предоставленное имя сервера для <xref:System.IO.Pipes.NamedPipeClientStream> объект `"."`.</span><span class="sxs-lookup"><span data-stu-id="cdbb2-120">The client and server processes in this example are intended to run on the same computer, so the server name provided to the <xref:System.IO.Pipes.NamedPipeClientStream> object is `"."`.</span></span> <span data-ttu-id="cdbb2-121">Если клиентские и серверные процессы выполнялись на разных компьютерах, `"."` должно было быть заменено сетевое имя компьютера, на котором запускает серверный процесс.</span><span class="sxs-lookup"><span data-stu-id="cdbb2-121">If the client and server processes were on separate computers, `"."` would be replaced with the network name of the computer that runs the server process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdbb2-122">См. также</span><span class="sxs-lookup"><span data-stu-id="cdbb2-122">See Also</span></span>  
 <xref:System.Security.Principal.TokenImpersonationLevel>  
 <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>  
 [<span data-ttu-id="cdbb2-123">Каналы</span><span class="sxs-lookup"><span data-stu-id="cdbb2-123">Pipes</span></span>](../../../docs/standard/io/pipe-operations.md)  
 [<span data-ttu-id="cdbb2-124">Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами</span><span class="sxs-lookup"><span data-stu-id="cdbb2-124">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
