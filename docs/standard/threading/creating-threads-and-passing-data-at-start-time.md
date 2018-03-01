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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d17ef8a199061f56f00e39fa887e2e64f64427ec
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="creating-threads-and-passing-data-at-start-time"></a><span data-ttu-id="1ae6d-102">Создание потоков и передача данных во время запуска</span><span class="sxs-lookup"><span data-stu-id="1ae6d-102">Creating Threads and Passing Data at Start Time</span></span>
<span data-ttu-id="1ae6d-103">При создании процесса в операционной системе она добавляет поток для выполнения кода этого процесса, включая все исходные домены приложений.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-103">When an operating-system process is created, the operating system injects a thread to execute code in that process, including any original application domain.</span></span> <span data-ttu-id="1ae6d-104">С этого момента домены приложений могут создаваться и уничтожаться, что не обязательно сопровождается созданием или уничтожением потоков операционной системы.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-104">From that point on, application domains can be created and destroyed without any operating system threads necessarily being created or destroyed.</span></span> <span data-ttu-id="1ae6d-105">Если выполняемый код является управляемым, то вы можете получить объект <xref:System.Threading.Thread> для потока, выполняющегося в текущем домене приложения. Для этого получите статическое свойство <xref:System.Threading.Thread.CurrentThread%2A> типа <xref:System.Threading.Thread>.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-105">If the code being executed is managed code, then a <xref:System.Threading.Thread> object for the thread executing in the current application domain can be obtained by retrieving the static <xref:System.Threading.Thread.CurrentThread%2A> property of type <xref:System.Threading.Thread>.</span></span> <span data-ttu-id="1ae6d-106">В этой статье описано создание потока и несколько способов передачи данных в процедуру потока.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-106">This topic describes thread creation and discusses alternatives for passing data to the thread procedure.</span></span>  
  
## <a name="creating-a-thread"></a><span data-ttu-id="1ae6d-107">Создание потока</span><span class="sxs-lookup"><span data-stu-id="1ae6d-107">Creating a Thread</span></span>  
 <span data-ttu-id="1ae6d-108">Создание нового объекта <xref:System.Threading.Thread> приводит к созданию нового управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-108">Creating a new <xref:System.Threading.Thread> object creates a new managed thread.</span></span> <span data-ttu-id="1ae6d-109">Класс <xref:System.Threading.Thread> имеет конструкторы, которые принимают делегат <xref:System.Threading.ThreadStart> или <xref:System.Threading.ParameterizedThreadStart>. Этот делегат инкапсулирует метод, который вызывается новым потоком при вызове метода <xref:System.Threading.Thread.Start%2A>.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-109">The <xref:System.Threading.Thread> class has constructors that take a <xref:System.Threading.ThreadStart> delegate or a <xref:System.Threading.ParameterizedThreadStart> delegate; the delegate wraps the method that is invoked by the new thread when you call the <xref:System.Threading.Thread.Start%2A> method.</span></span> <span data-ttu-id="1ae6d-110">Повторный вызов <xref:System.Threading.Thread.Start%2A> приводит к созданию исключения <xref:System.Threading.ThreadStateException>.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-110">Calling <xref:System.Threading.Thread.Start%2A> more than once causes a <xref:System.Threading.ThreadStateException> to be thrown.</span></span>  
  
 <span data-ttu-id="1ae6d-111">Метод <xref:System.Threading.Thread.Start%2A> завершается немедленно, часто даже до запуска нового потока.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-111">The <xref:System.Threading.Thread.Start%2A> method returns immediately, often before the new thread has actually started.</span></span> <span data-ttu-id="1ae6d-112">Вы можете использовать свойства <xref:System.Threading.Thread.ThreadState%2A> и <xref:System.Threading.Thread.IsAlive%2A>, чтобы определить состояние потока в настоящий момент, но эти свойства ни в коем случае нельзя использовать для синхронизации действий потоков.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-112">You can use the <xref:System.Threading.Thread.ThreadState%2A> and <xref:System.Threading.Thread.IsAlive%2A> properties to determine the state of the thread at any one moment, but these properties should never be used for synchronizing the activities of threads.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ae6d-113">После запуска потока не нужно сохранять ссылку на объект <xref:System.Threading.Thread>.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-113">Once a thread is started, it is not necessary to retain a reference to the <xref:System.Threading.Thread> object.</span></span> <span data-ttu-id="1ae6d-114">Поток продолжит выполняться, пока не завершится запущенная в нем процедура.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-114">The thread continues to execute until the thread procedure ends.</span></span>  
  
 <span data-ttu-id="1ae6d-115">В следующем примере кода создается два новых потока для вызова метода экземпляра и статического метода из другого объекта.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-115">The following code example creates two new threads to call instance and static methods on another object.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads-and-retrieving-data-from-threads"></a><span data-ttu-id="1ae6d-116">Передача данных в потоки и получение данных из потоков</span><span class="sxs-lookup"><span data-stu-id="1ae6d-116">Passing Data to Threads and Retrieving Data from Threads</span></span>  
 <span data-ttu-id="1ae6d-117">На платформе .NET Framework версии 2.0 делегат <xref:System.Threading.ParameterizedThreadStart> предоставляет простой способ передать в поток объект с данными при вызове перегрузки метода <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-117">In the .NET Framework version 2.0, the <xref:System.Threading.ParameterizedThreadStart> delegate provides an easy way to pass an object containing data to a thread when you call the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload.</span></span> <span data-ttu-id="1ae6d-118">См. пример кода в <xref:System.Threading.ParameterizedThreadStart>.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-118">See <xref:System.Threading.ParameterizedThreadStart> for a code example.</span></span>  
  
 <span data-ttu-id="1ae6d-119">Делегат <xref:System.Threading.ParameterizedThreadStart> не является типобезопасным способом передачи данных, так как перегруженный метод <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> принимает любой объект.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-119">Using the <xref:System.Threading.ParameterizedThreadStart> delegate is not a type-safe way to pass data, because the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload accepts any object.</span></span> <span data-ttu-id="1ae6d-120">Вместо этого можно инкапсулировать процедуру потока и данные во вспомогательный класс и выполнять процедуру потока при помощи делегата <xref:System.Threading.ThreadStart>.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-120">An alternative is to encapsulate the thread procedure and the data in a helper class and use the <xref:System.Threading.ThreadStart> delegate to execute the thread procedure.</span></span> <span data-ttu-id="1ae6d-121">Этот подход демонстрируют приведенные ниже примеры кода.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-121">This technique is shown in the two code examples that follow.</span></span>  
  
 <span data-ttu-id="1ae6d-122">Ни один из этих делегатов не имеет возвращаемого значения, так как им некуда возвращать данные после асинхронного вызова.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-122">Neither of these delegates has a return value, because there is no place to return the data from an asynchronous call.</span></span> <span data-ttu-id="1ae6d-123">Чтобы получить результаты из метода потока, вы можете использовать метод обратного вызова, как показано во втором примере кода.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-123">To retrieve the results of a thread method, you can use a callback method, as demonstrated in the second code example.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  
  
### <a name="retrieving-data-with-callback-methods"></a><span data-ttu-id="1ae6d-124">Извлечение данных с помощью методов обратного вызова</span><span class="sxs-lookup"><span data-stu-id="1ae6d-124">Retrieving Data with Callback Methods</span></span>  
 <span data-ttu-id="1ae6d-125">Приведенный ниже пример демонстрирует метод обратного вызова, который получает данные из потока.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-125">The following example demonstrates a callback method that retrieves data from a thread.</span></span> <span data-ttu-id="1ae6d-126">Конструктор класса, содержащего данные и метод потока, также принимает делегат, который представляет метод обратного вызова. Метод потока перед завершением своей работы вызывает этот делегат обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="1ae6d-126">The constructor for the class that contains the data and the thread method also accepts a delegate representing the callback method; before the thread method ends, it invokes the callback delegate.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="1ae6d-127">См. также</span><span class="sxs-lookup"><span data-stu-id="1ae6d-127">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadStart>  
 <xref:System.Threading.ParameterizedThreadStart>  
 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="1ae6d-128">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="1ae6d-128">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="1ae6d-129">Использование потоков и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="1ae6d-129">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
