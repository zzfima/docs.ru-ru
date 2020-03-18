---
title: Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: ea4aee60d090a56eb0cf3f2a81c1b05c04806d4b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "77627998"
---
# <a name="how-to-use-anonymous-pipes-for-local-interprocess-communication"></a><span data-ttu-id="881af-102">Практическое руководство. Использование анонимных каналов для локального взаимодействия между процессами</span><span class="sxs-lookup"><span data-stu-id="881af-102">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>
<span data-ttu-id="881af-103">Анонимные каналы обеспечивают межпроцессное взаимодействие на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="881af-103">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="881af-104">Они предоставляют меньше возможностей, чем именованные каналы, но требуют меньше ресурсов.</span><span class="sxs-lookup"><span data-stu-id="881af-104">They offer less functionality than named pipes, but also require less overhead.</span></span> <span data-ttu-id="881af-105">С помощью анонимных каналов вы можете легко организовать межпроцессное взаимодействие на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="881af-105">You can use anonymous pipes to make interprocess communication on a local computer easier.</span></span> <span data-ttu-id="881af-106">Анонимные каналы не подходят для обмена данными по сети.</span><span class="sxs-lookup"><span data-stu-id="881af-106">You cannot use anonymous pipes for communication over a network.</span></span>  
  
 <span data-ttu-id="881af-107">Для реализации анонимных каналов используются классы <xref:System.IO.Pipes.AnonymousPipeServerStream> и <xref:System.IO.Pipes.AnonymousPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="881af-107">To implement anonymous pipes, use the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="881af-108">Пример</span><span class="sxs-lookup"><span data-stu-id="881af-108">Example</span></span>  
 <span data-ttu-id="881af-109">В следующем примере показано, как отправить строку из родительского процесса в дочерний процесс через анонимные каналы.</span><span class="sxs-lookup"><span data-stu-id="881af-109">The following example demonstrates a way to send a string from a parent process to a child process using anonymous pipes.</span></span> <span data-ttu-id="881af-110">В этом примере создается объект <xref:System.IO.Pipes.AnonymousPipeServerStream> в родительском процессе, в котором параметру <xref:System.IO.Pipes.PipeDirection> задано значение <xref:System.IO.Pipes.PipeDirection.Out>.</span><span class="sxs-lookup"><span data-stu-id="881af-110">This example creates an <xref:System.IO.Pipes.AnonymousPipeServerStream> object in a parent process with a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.Out>.</span></span> <span data-ttu-id="881af-111">Затем родительский процесс создает дочерний процесс, используя дескриптор клиента для создания объекта <xref:System.IO.Pipes.AnonymousPipeClientStream>.</span><span class="sxs-lookup"><span data-stu-id="881af-111">The parent process then creates a child process by using a client handle to create an <xref:System.IO.Pipes.AnonymousPipeClientStream> object.</span></span> <span data-ttu-id="881af-112">В дочернем процессе <xref:System.IO.Pipes.PipeDirection> имеет значение <xref:System.IO.Pipes.PipeDirection.In>.</span><span class="sxs-lookup"><span data-stu-id="881af-112">The child process has a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.In>.</span></span>  
  
 <span data-ttu-id="881af-113">Теперь родительский процесс отправляет предоставленную пользователем строку в дочерний процесс.</span><span class="sxs-lookup"><span data-stu-id="881af-113">The parent process then sends a user-supplied string to the child process.</span></span> <span data-ttu-id="881af-114">Эта строка выводится в консоль дочернего процесса.</span><span class="sxs-lookup"><span data-stu-id="881af-114">The string is displayed to the console in the child process.</span></span>  
  
 <span data-ttu-id="881af-115">Ниже представлен серверный процесс для этого примера.</span><span class="sxs-lookup"><span data-stu-id="881af-115">The following example shows the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]
  
## <a name="example"></a><span data-ttu-id="881af-116">Пример</span><span class="sxs-lookup"><span data-stu-id="881af-116">Example</span></span>  
 <span data-ttu-id="881af-117">Ниже представлен клиентский процесс для этого примера.</span><span class="sxs-lookup"><span data-stu-id="881af-117">The following example shows the client process.</span></span> <span data-ttu-id="881af-118">Серверный процесс запускает клиентский процесс и передает ему дескриптор клиента.</span><span class="sxs-lookup"><span data-stu-id="881af-118">The server process starts the client process and gives that process a client handle.</span></span> <span data-ttu-id="881af-119">Полученному исполняемому файлу в коде клиентского процесса следует присвоить имя `pipeClient.exe` и сохранить его в том же каталоге, где расположен исполняемый файл серверного процесса, прежде чем запускать серверный процесс.</span><span class="sxs-lookup"><span data-stu-id="881af-119">The resulting executable from the client code should be named `pipeClient.exe` and be copied to the same directory as the server executable before running the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="881af-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="881af-120">See also</span></span>

- [<span data-ttu-id="881af-121">Каналы</span><span class="sxs-lookup"><span data-stu-id="881af-121">Pipes</span></span>](../../../docs/standard/io/pipe-operations.md)
- [<span data-ttu-id="881af-122">Практическое руководство. Использование именованных каналов для сетевого взаимодействия между процессами</span><span class="sxs-lookup"><span data-stu-id="881af-122">How to: Use Named Pipes for Network Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
