---
title: Практическое руководство. Использование именованных каналов для сетевого взаимодействия между процессами
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
- full duplex communication [.NET Framework], named pipes
ms.assetid: 4e4d7e64-9f1b-4026-98f7-20488ac7b42b
ms.openlocfilehash: 71f3a8d38b46993762b2673ea5fe735d8d54d351
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706638"
---
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a><span data-ttu-id="e324e-102">Практическое руководство. Использование именованных каналов для сетевого взаимодействия между процессами</span><span class="sxs-lookup"><span data-stu-id="e324e-102">How to: Use Named Pipes for Network Interprocess Communication</span></span>
<span data-ttu-id="e324e-103">Именованные каналы обеспечивают межпроцессное взаимодействие между сервером канала и одним или несколькими клиентами канала.</span><span class="sxs-lookup"><span data-stu-id="e324e-103">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="e324e-104">Они предоставляют больше функциональных возможностей, чем анонимные каналы, которые обеспечивают межпроцессное взаимодействие на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e324e-104">They offer more functionality than anonymous pipes, which provide interprocess communication on a local computer.</span></span> <span data-ttu-id="e324e-105">Именованные каналы поддерживают полную дуплексную связь по сети и несколько экземпляров сервера, связь на основе сообщений и олицетворение клиента, позволяющее подключающимся процессам использовать собственные наборы разрешений на удаленных серверах.</span><span class="sxs-lookup"><span data-stu-id="e324e-105">Named pipes support full duplex communication over a network and multiple server instances, message-based communication, and client impersonation, which enables connecting processes to use their own set of permissions on remote servers.</span></span>  
  
 <span data-ttu-id="e324e-106">Для реализации именованных каналов используются классы <xref:System.IO.Pipes.NamedPipeServerStream> и <xref:System.IO.Pipes.NamedPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="e324e-106">To implement name pipes, use the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e324e-107">Пример</span><span class="sxs-lookup"><span data-stu-id="e324e-107">Example</span></span>  
 <span data-ttu-id="e324e-108">В примере ниже показано, как создать именованный канал с помощью класса <xref:System.IO.Pipes.NamedPipeServerStream>.</span><span class="sxs-lookup"><span data-stu-id="e324e-108">The following example demonstrates how to create a named pipe by using the <xref:System.IO.Pipes.NamedPipeServerStream> class.</span></span> <span data-ttu-id="e324e-109">В этом примере серверный процесс создает четыре потока.</span><span class="sxs-lookup"><span data-stu-id="e324e-109">In this example, the server process creates four threads.</span></span> <span data-ttu-id="e324e-110">Каждый поток может принимать подключение клиента.</span><span class="sxs-lookup"><span data-stu-id="e324e-110">Each thread can accept a client connection.</span></span> <span data-ttu-id="e324e-111">Процесс подключения клиента передает серверу имя файла.</span><span class="sxs-lookup"><span data-stu-id="e324e-111">The connected client process then supplies the server with a file name.</span></span> <span data-ttu-id="e324e-112">Если клиенту имеет необходимые разрешения, серверный процесс открывает указанный файл и отправляет клиенту его содержимое.</span><span class="sxs-lookup"><span data-stu-id="e324e-112">If the client has sufficient permissions, the server process opens the file and sends its contents back to the client.</span></span>  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="e324e-113">Пример</span><span class="sxs-lookup"><span data-stu-id="e324e-113">Example</span></span>  
 <span data-ttu-id="e324e-114">В примере ниже представлен клиентский процесс, основанный на классе <xref:System.IO.Pipes.NamedPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="e324e-114">The following example shows the client process, which uses the <xref:System.IO.Pipes.NamedPipeClientStream> class.</span></span> <span data-ttu-id="e324e-115">Клиент подключается к серверному процессу и передает серверу имя файла.</span><span class="sxs-lookup"><span data-stu-id="e324e-115">The client connects to the server process and sends a file name to the server.</span></span> <span data-ttu-id="e324e-116">В этом примере используется олицетворение. Это означает, что у идентификатора, от имени которого выполняется клиентское приложение, должны быть разрешения на доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="e324e-116">The example uses impersonation, so the identity that is running the client application must have permission to access the file.</span></span> <span data-ttu-id="e324e-117">Затем сервер отправляет клиенту содержимое файла.</span><span class="sxs-lookup"><span data-stu-id="e324e-117">The server then sends the contents of the file back to the client.</span></span> <span data-ttu-id="e324e-118">Полученное содержимое файла выводится в консоль.</span><span class="sxs-lookup"><span data-stu-id="e324e-118">The file contents are then displayed to the console.</span></span>  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a><span data-ttu-id="e324e-119">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="e324e-119">Robust Programming</span></span>  
 <span data-ttu-id="e324e-120">Клиентский и серверный процессы в этом примере предназначены для выполнения на одном компьютере, поэтому объекту <xref:System.IO.Pipes.NamedPipeClientStream> передается имя сервера `"."`.</span><span class="sxs-lookup"><span data-stu-id="e324e-120">The client and server processes in this example are intended to run on the same computer, so the server name provided to the <xref:System.IO.Pipes.NamedPipeClientStream> object is `"."`.</span></span> <span data-ttu-id="e324e-121">Если клиентский и серверный процессы выполняются на разных компьютерах, вместо `"."` должно быть указано сетевое имя компьютера, на котором осуществляется серверный процесс.</span><span class="sxs-lookup"><span data-stu-id="e324e-121">If the client and server processes were on separate computers, `"."` would be replaced with the network name of the computer that runs the server process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e324e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="e324e-122">See also</span></span>

- <xref:System.Security.Principal.TokenImpersonationLevel>
- <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>
- [<span data-ttu-id="e324e-123">Каналы</span><span class="sxs-lookup"><span data-stu-id="e324e-123">Pipes</span></span>](../../../docs/standard/io/pipe-operations.md)
- [<span data-ttu-id="e324e-124">Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами</span><span class="sxs-lookup"><span data-stu-id="e324e-124">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
