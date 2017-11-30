---
title: "Практическое руководство. Указание степени параллелизма в блоке потока данных"
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
helpviewer_keywords:
- dataflow block, specifying parallelism in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, specifying parallelism
ms.assetid: e4088541-ee05-40db-95f5-147cfe62fde7
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c1ccd64a9acbc75a30984719671af2dc7dda6922
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-specify-the-degree-of-parallelism-in-a-dataflow-block"></a><span data-ttu-id="012a8-102">Практическое руководство. Указание степени параллелизма в блоке потока данных</span><span class="sxs-lookup"><span data-stu-id="012a8-102">How to: Specify the Degree of Parallelism in a Dataflow Block</span></span>
<span data-ttu-id="012a8-103">В этом документе описывается, как задать свойство <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType>, чтобы позволить блоку выполнения потока данных обрабатывать более одного сообщения единовременно.</span><span class="sxs-lookup"><span data-stu-id="012a8-103">This document describes how to set the <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType> property to enable an execution dataflow block to process more than one message at a time.</span></span> <span data-ttu-id="012a8-104">Это удобно при наличии блока потока данных, который выполняет длительное вычисление и может получить выгоду от обработки сообщений параллельным образом.</span><span class="sxs-lookup"><span data-stu-id="012a8-104">Doing this is useful when you have a dataflow block that performs a long-running computation and can benefit from processing messages in parallel.</span></span> <span data-ttu-id="012a8-105">В этом примере используется класс <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType> для параллельного выполнения нескольких операций потока данных; однако можно задать максимальную степень параллелизма в любом из предопределенных типов блоков выполнения, предоставляемых библиотекой потоков данных: <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="012a8-105">This example uses the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType> class to perform multiple dataflow operations concurrently; however, you can specify the maximum degree of parallelism in any of the predefined execution block types that the TPL Dataflow Library provides, <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType>, and <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="012a8-106">Библиотека потоков данных TPL (пространство имен <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) не поставляется с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="012a8-106">The TPL Dataflow Library (the <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="012a8-107">Чтобы установить <xref:System.Threading.Tasks.Dataflow> пространства имен, откройте проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите **управление пакетами NuGet** меню проекта и выполните поиск в Интернете `Microsoft.Tpl.Dataflow` пакета.</span><span class="sxs-lookup"><span data-stu-id="012a8-107">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
## <a name="example"></a><span data-ttu-id="012a8-108">Пример</span><span class="sxs-lookup"><span data-stu-id="012a8-108">Example</span></span>  
 <span data-ttu-id="012a8-109">В следующем примере выполняется два вычисления потока данных и выводится остаток времени, необходимый для каждого вычисления.</span><span class="sxs-lookup"><span data-stu-id="012a8-109">The following example performs two dataflow computations and prints the elapsed time that is required for each computation.</span></span> <span data-ttu-id="012a8-110">Первое вычисление указывает максимальную степень параллелизма 1, что является значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="012a8-110">The first computation specifies a maximum degree of parallelism of 1, which is the default.</span></span> <span data-ttu-id="012a8-111">Максимальная степень параллелизма 1 заставляет блок потока данных обрабатывать сообщения последовательно.</span><span class="sxs-lookup"><span data-stu-id="012a8-111">A maximum degree of parallelism of 1 causes the dataflow block to process messages serially.</span></span> <span data-ttu-id="012a8-112">Второе вычисление напоминает первое за исключением того, что для него указывается максимальная степень параллелизма, равная числу доступных процессоров.</span><span class="sxs-lookup"><span data-stu-id="012a8-112">The second computation resembles the first, except that it specifies a maximum degree of parallelism that is equal to the number of available processors.</span></span> <span data-ttu-id="012a8-113">Это позволяет блоку потока данных выполнять несколько операций параллельно.</span><span class="sxs-lookup"><span data-stu-id="012a8-113">This enables the dataflow block to perform multiple operations in parallel.</span></span>  
  
 [!code-csharp[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_degreeofparallelism/cs/dataflowdegreeofparallelism.cs#1)]
 [!code-vb[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_degreeofparallelism/vb/dataflowdegreeofparallelism.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="012a8-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="012a8-114">Compiling the Code</span></span>  
 <span data-ttu-id="012a8-115">Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `DataflowDegreeOfParallelism.cs` (`DataflowDegreeOfParallelism.vb` для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), затем выполните в окне командной строки Visual Studio следующую команду.</span><span class="sxs-lookup"><span data-stu-id="012a8-115">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowDegreeOfParallelism.cs` (`DataflowDegreeOfParallelism.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="012a8-116">**CSC.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.cs**</span><span class="sxs-lookup"><span data-stu-id="012a8-116">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="012a8-117">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.vb**</span><span class="sxs-lookup"><span data-stu-id="012a8-117">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="012a8-118">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="012a8-118">Robust Programming</span></span>  
 <span data-ttu-id="012a8-119">По умолчанию все предопределенные блоки потока данных распространяют сообщения в том порядке, в котором они их получают.</span><span class="sxs-lookup"><span data-stu-id="012a8-119">By default, each predefined dataflow block propagates out messages in the order in which the messages are received.</span></span>  <span data-ttu-id="012a8-120">Хотя при указании максимальной степени параллелизма больше 1 несколько сообщений обрабатываются одновременно, они по-прежнему распространяются в порядке, в котором были получены.</span><span class="sxs-lookup"><span data-stu-id="012a8-120">Although multiple messages are processed simultaneously when you specify a maximum degree of parallelism that is greater than 1, they are still propagated out in the order in which they are received.</span></span>  
  
 <span data-ttu-id="012a8-121">Поскольку свойство <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> представляет максимальную степень параллелизма, блок потока данных может выполняться с меньшей степенью параллелизма, чем задано.</span><span class="sxs-lookup"><span data-stu-id="012a8-121">Because the <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> property represents the maximum degree of parallelism, the dataflow block might execute with a lesser degree of parallelism than you specify.</span></span> <span data-ttu-id="012a8-122">Блок потока данных может использовать меньшую степень параллелизма для удовлетворения функциональных требований или при недостатке доступных системных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="012a8-122">The dataflow block can use a lesser degree of parallelism to meet its functional requirements or to account for a lack of available system resources.</span></span> <span data-ttu-id="012a8-123">Блок потока данных никогда не выбирает степень параллелизма, превосходящую указанную.</span><span class="sxs-lookup"><span data-stu-id="012a8-123">A dataflow block never chooses a greater degree of parallelism than you specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="012a8-124">См. также</span><span class="sxs-lookup"><span data-stu-id="012a8-124">See Also</span></span>  
 [<span data-ttu-id="012a8-125">Поток данных</span><span class="sxs-lookup"><span data-stu-id="012a8-125">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
