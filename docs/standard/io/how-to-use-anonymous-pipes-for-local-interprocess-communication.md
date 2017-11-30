---
title: "Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами"
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
- anonymous pipes [.NET Framework]
- parent-child communication [.NET Framework]
- pipes [.NET Framework]
- one-way communication [.NET Framework]
- local computer communication [.NET Framework], pipes
ms.assetid: e7773c77-c646-4a01-8a96-a003d59fc4c9
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f457cc91e6fbfc118e5363d1b0a8e8c2ad800748
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-anonymous-pipes-for-local-interprocess-communication"></a><span data-ttu-id="15271-102">Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами</span><span class="sxs-lookup"><span data-stu-id="15271-102">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>
<span data-ttu-id="15271-103">Анонимные каналы обеспечивают межпроцессное взаимодействие на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="15271-103">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="15271-104">Они предоставляют меньше возможностей, чем именованные каналы, но требуют меньше ресурсов.</span><span class="sxs-lookup"><span data-stu-id="15271-104">They offer less functionality than named pipes, but also require less overhead.</span></span> <span data-ttu-id="15271-105">Можно использовать анонимные каналы для упрощения взаимодействия между процессами на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="15271-105">You can use anonymous pipes to make interprocess communication on a local computer easier.</span></span> <span data-ttu-id="15271-106">Анонимные каналы нельзя использовать для обмена данными по сети.</span><span class="sxs-lookup"><span data-stu-id="15271-106">You cannot use anonymous pipes for communication over a network.</span></span>  
  
 <span data-ttu-id="15271-107">Для реализации анонимных каналов используются классы <xref:System.IO.Pipes.AnonymousPipeServerStream> и <xref:System.IO.Pipes.AnonymousPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="15271-107">To implement anonymous pipes, use the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15271-108">Пример</span><span class="sxs-lookup"><span data-stu-id="15271-108">Example</span></span>  
 <span data-ttu-id="15271-109">Следующий пример демонстрирует способ отправки строки из родительского процесса в дочерний процесс посредством анонимных каналов.</span><span class="sxs-lookup"><span data-stu-id="15271-109">The following example demonstrates a way to send a string from a parent process to a child process using anonymous pipes.</span></span> <span data-ttu-id="15271-110">В этом примере создается <xref:System.IO.Pipes.AnonymousPipeServerStream> объекта в родительский процесс с <xref:System.IO.Pipes.PipeDirection> значение <xref:System.IO.Pipes.PipeDirection.Out>.</span><span class="sxs-lookup"><span data-stu-id="15271-110">This example creates an <xref:System.IO.Pipes.AnonymousPipeServerStream> object in a parent process with a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.Out>.</span></span> <span data-ttu-id="15271-111">Родительский процесс затем создает дочерний процесс с помощью дескриптора клиента для создания <xref:System.IO.Pipes.AnonymousPipeClientStream> объекта.</span><span class="sxs-lookup"><span data-stu-id="15271-111">The parent process then creates a child process by using a client handle to create an <xref:System.IO.Pipes.AnonymousPipeClientStream> object.</span></span> <span data-ttu-id="15271-112">Дочерний процесс имеет <xref:System.IO.Pipes.PipeDirection> значение <xref:System.IO.Pipes.PipeDirection.In>.</span><span class="sxs-lookup"><span data-stu-id="15271-112">The child process has a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.In>.</span></span>  
  
 <span data-ttu-id="15271-113">Родительский процесс затем отправляет пользовательскую строку дочернему процессу.</span><span class="sxs-lookup"><span data-stu-id="15271-113">The parent process then sends a user-supplied string to the child process.</span></span> <span data-ttu-id="15271-114">При отображении строки на консоль в дочерний процесс.</span><span class="sxs-lookup"><span data-stu-id="15271-114">The string is displayed to the console in the child process.</span></span>  
  
 <span data-ttu-id="15271-115">Пример серверного процесса.</span><span class="sxs-lookup"><span data-stu-id="15271-115">The following example shows the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="15271-116">Пример</span><span class="sxs-lookup"><span data-stu-id="15271-116">Example</span></span>  
 <span data-ttu-id="15271-117">Пример клиентского процесса.</span><span class="sxs-lookup"><span data-stu-id="15271-117">The following example shows the client process.</span></span> <span data-ttu-id="15271-118">Серверный процесс запускает клиентский процесс и передает этому процессу дескриптор клиента.</span><span class="sxs-lookup"><span data-stu-id="15271-118">The server process starts the client process and gives that process a client handle.</span></span> <span data-ttu-id="15271-119">Полученный исполняемый файл из клиентского кода, который должен быть назван `pipeClient.exe` и копируются в том же каталоге, что исполняемый файл сервера перед запуском серверного процесса.</span><span class="sxs-lookup"><span data-stu-id="15271-119">The resulting executable from the client code should be named `pipeClient.exe` and be copied to the same directory as the server executable before running the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="15271-120">См. также</span><span class="sxs-lookup"><span data-stu-id="15271-120">See Also</span></span>  
 [<span data-ttu-id="15271-121">Каналы</span><span class="sxs-lookup"><span data-stu-id="15271-121">Pipes</span></span>](../../../docs/standard/io/pipe-operations.md)  
 [<span data-ttu-id="15271-122">Практическое руководство. Использование именованных каналов для сетевого взаимодействия между процессами</span><span class="sxs-lookup"><span data-stu-id="15271-122">How to: Use Named Pipes for Network Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
