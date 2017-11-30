---
title: "Создание потоков и передача данных во время запуска"
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
- threading [.NET Framework], creating
- threading [.NET Framework], passing data to threads
- threading [.NET Framework], retrieving data from threads
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61808dc804cc627ab368a5250414dfcc5f54c87e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="creating-threads-and-passing-data-at-start-time"></a><span data-ttu-id="da67b-102">Создание потоков и передача данных во время запуска</span><span class="sxs-lookup"><span data-stu-id="da67b-102">Creating Threads and Passing Data at Start Time</span></span>
<span data-ttu-id="da67b-103">При создании процесса операционной системы, операционная система включается поток для выполнения кода в этом процессе, включая исходным доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="da67b-103">When an operating-system process is created, the operating system injects a thread to execute code in that process, including any original application domain.</span></span> <span data-ttu-id="da67b-104">С этого момента домены приложений могут создаваться и уничтожаться, без каких-либо потоков операционной системы, обязательно создается или уничтожается.</span><span class="sxs-lookup"><span data-stu-id="da67b-104">From that point on, application domains can be created and destroyed without any operating system threads necessarily being created or destroyed.</span></span> <span data-ttu-id="da67b-105">Если выполняемый код является управляемым кодом, то <xref:System.Threading.Thread> объекта для потока, выполняющегося в текущем домене приложения можно получить посредством статического <xref:System.Threading.Thread.CurrentThread%2A> свойство типа <xref:System.Threading.Thread>.</span><span class="sxs-lookup"><span data-stu-id="da67b-105">If the code being executed is managed code, then a <xref:System.Threading.Thread> object for the thread executing in the current application domain can be obtained by retrieving the static <xref:System.Threading.Thread.CurrentThread%2A> property of type <xref:System.Threading.Thread>.</span></span> <span data-ttu-id="da67b-106">В этом разделе описывается создание потока и обсуждаются альтернативные способы передачи данных в процедуру потока.</span><span class="sxs-lookup"><span data-stu-id="da67b-106">This topic describes thread creation and discusses alternatives for passing data to the thread procedure.</span></span>  
  
## <a name="creating-a-thread"></a><span data-ttu-id="da67b-107">Создание потока</span><span class="sxs-lookup"><span data-stu-id="da67b-107">Creating a Thread</span></span>  
 <span data-ttu-id="da67b-108">Создание нового <xref:System.Threading.Thread> объект создает нового управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="da67b-108">Creating a new <xref:System.Threading.Thread> object creates a new managed thread.</span></span> <span data-ttu-id="da67b-109"><xref:System.Threading.Thread> Класс имеет конструкторы, принимающие <xref:System.Threading.ThreadStart> делегата или <xref:System.Threading.ParameterizedThreadStart> делегата; делегат инкапсулирует метод, который может быть вызван с новым потоком при вызове <xref:System.Threading.Thread.Start%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="da67b-109">The <xref:System.Threading.Thread> class has constructors that take a <xref:System.Threading.ThreadStart> delegate or a <xref:System.Threading.ParameterizedThreadStart> delegate; the delegate wraps the method that is invoked by the new thread when you call the <xref:System.Threading.Thread.Start%2A> method.</span></span> <span data-ttu-id="da67b-110">Вызов <xref:System.Threading.Thread.Start%2A> несколько раз вызывает <xref:System.Threading.ThreadStateException> исключение.</span><span class="sxs-lookup"><span data-stu-id="da67b-110">Calling <xref:System.Threading.Thread.Start%2A> more than once causes a <xref:System.Threading.ThreadStateException> to be thrown.</span></span>  
  
 <span data-ttu-id="da67b-111"><xref:System.Threading.Thread.Start%2A> Метод возвращается немедленно, часто до действительно был запущен новый поток.</span><span class="sxs-lookup"><span data-stu-id="da67b-111">The <xref:System.Threading.Thread.Start%2A> method returns immediately, often before the new thread has actually started.</span></span> <span data-ttu-id="da67b-112">Можно использовать <xref:System.Threading.Thread.ThreadState%2A> и <xref:System.Threading.Thread.IsAlive%2A> свойства, чтобы определить состояние потока в настоящий момент, но эти свойства никогда не должен использоваться для синхронизации действий потоков.</span><span class="sxs-lookup"><span data-stu-id="da67b-112">You can use the <xref:System.Threading.Thread.ThreadState%2A> and <xref:System.Threading.Thread.IsAlive%2A> properties to determine the state of the thread at any one moment, but these properties should never be used for synchronizing the activities of threads.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da67b-113">После запуска потока, нет необходимости сохранять ссылку на <xref:System.Threading.Thread> объекта.</span><span class="sxs-lookup"><span data-stu-id="da67b-113">Once a thread is started, it is not necessary to retain a reference to the <xref:System.Threading.Thread> object.</span></span> <span data-ttu-id="da67b-114">Поток продолжает выполняться до завершения потоковой процедуры.</span><span class="sxs-lookup"><span data-stu-id="da67b-114">The thread continues to execute until the thread procedure ends.</span></span>  
  
 <span data-ttu-id="da67b-115">В следующем примере кода создается два новых потоков для вызова экземпляра и статические методы в другой объект.</span><span class="sxs-lookup"><span data-stu-id="da67b-115">The following code example creates two new threads to call instance and static methods on another object.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads-and-retrieving-data-from-threads"></a><span data-ttu-id="da67b-116">Передача данных в потоки и получение данных из потоков</span><span class="sxs-lookup"><span data-stu-id="da67b-116">Passing Data to Threads and Retrieving Data from Threads</span></span>  
 <span data-ttu-id="da67b-117">В .NET Framework версии 2.0 <xref:System.Threading.ParameterizedThreadStart> делегат предоставляет простой способ передачи объекта, содержащего данные в поток при вызове <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> перегрузки метода.</span><span class="sxs-lookup"><span data-stu-id="da67b-117">In the .NET Framework version 2.0, the <xref:System.Threading.ParameterizedThreadStart> delegate provides an easy way to pass an object containing data to a thread when you call the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload.</span></span> <span data-ttu-id="da67b-118">См. пример кода в <xref:System.Threading.ParameterizedThreadStart>.</span><span class="sxs-lookup"><span data-stu-id="da67b-118">See <xref:System.Threading.ParameterizedThreadStart> for a code example.</span></span>  
  
 <span data-ttu-id="da67b-119">С помощью <xref:System.Threading.ParameterizedThreadStart> делегат несовместим типобезопасный способ передачи данных, так как <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> перегруженный метод принимает любой объект.</span><span class="sxs-lookup"><span data-stu-id="da67b-119">Using the <xref:System.Threading.ParameterizedThreadStart> delegate is not a type-safe way to pass data, because the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload accepts any object.</span></span> <span data-ttu-id="da67b-120">Альтернативой является инкапсуляция процедуры потока и данных во вспомогательном классе и использование <xref:System.Threading.ThreadStart> делегат для выполнения процедуры потока.</span><span class="sxs-lookup"><span data-stu-id="da67b-120">An alternative is to encapsulate the thread procedure and the data in a helper class and use the <xref:System.Threading.ThreadStart> delegate to execute the thread procedure.</span></span> <span data-ttu-id="da67b-121">Этот способ показан в приведенных ниже примерах кода.</span><span class="sxs-lookup"><span data-stu-id="da67b-121">This technique is shown in the two code examples that follow.</span></span>  
  
 <span data-ttu-id="da67b-122">Ни один из этих делегатов не имеет возвращаемого значения, поскольку нет места для возвращения данных после асинхронного вызова.</span><span class="sxs-lookup"><span data-stu-id="da67b-122">Neither of these delegates has a return value, because there is no place to return the data from an asynchronous call.</span></span> <span data-ttu-id="da67b-123">Для получения результатов метода потока, можно использовать метод обратного вызова, как показано во втором примере кода.</span><span class="sxs-lookup"><span data-stu-id="da67b-123">To retrieve the results of a thread method, you can use a callback method, as demonstrated in the second code example.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  
  
### <a name="retrieving-data-with-callback-methods"></a><span data-ttu-id="da67b-124">Извлечение данных с помощью методов обратного вызова</span><span class="sxs-lookup"><span data-stu-id="da67b-124">Retrieving Data with Callback Methods</span></span>  
 <span data-ttu-id="da67b-125">В следующем примере показано, метод обратного вызова, который получает данные из потока.</span><span class="sxs-lookup"><span data-stu-id="da67b-125">The following example demonstrates a callback method that retrieves data from a thread.</span></span> <span data-ttu-id="da67b-126">Конструктор для класса, содержащего данные и метод потока также принимает делегат, представляющий метод обратного вызова; Перед завершением работы метод потока, он вызывает делегат обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="da67b-126">The constructor for the class that contains the data and the thread method also accepts a delegate representing the callback method; before the thread method ends, it invokes the callback delegate.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="da67b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="da67b-127">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadStart>  
 <xref:System.Threading.ParameterizedThreadStart>  
 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="da67b-128">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="da67b-128">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="da67b-129">Использование потоков и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="da67b-129">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
