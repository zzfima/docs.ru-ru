---
title: Практическое руководство. Реализация шаблона потока данных "производитель-получатель"
ms.date: 03/30/2017
ms.prod: .net
ms.technology: dotnet-standard
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TPL dataflow library, implementing producer-consumer pattern
- Task Parallel Library, dataflows
- producer-consumer patterns, implementing [TPL]
ms.assetid: 47a1d38c-fe9c-44aa-bd15-937bd5659b0b
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e47355ceebaa00a8a688dc56bfd9e647da79ded2
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-implement-a-producer-consumer-dataflow-pattern"></a><span data-ttu-id="04987-102">Практическое руководство. Реализация шаблона потока данных "производитель-получатель"</span><span class="sxs-lookup"><span data-stu-id="04987-102">How to: Implement a Producer-Consumer Dataflow Pattern</span></span>
<span data-ttu-id="04987-103">В этом документе описан способ использования библиотеки потоков данных TPL для реализации шаблона "производитель-получатель".</span><span class="sxs-lookup"><span data-stu-id="04987-103">This document describes how to use the TPL Dataflow Library to implement a producer-consumer pattern.</span></span> <span data-ttu-id="04987-104">В этом шаблоне *производитель* отправляет сообщения в блок сообщений, а *потребитель* считывает сообщения из этого блока.</span><span class="sxs-lookup"><span data-stu-id="04987-104">In this pattern, the *producer* sends messages to a message block, and the *consumer* reads messages from that block.</span></span>  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="example"></a><span data-ttu-id="04987-105">Пример</span><span class="sxs-lookup"><span data-stu-id="04987-105">Example</span></span>  
 <span data-ttu-id="04987-106">В следующем примере показана базовая модель "производитель-получатель", которая использует поток данных.</span><span class="sxs-lookup"><span data-stu-id="04987-106">The following example demonstrates a basic producer- consumer model that uses dataflow.</span></span> <span data-ttu-id="04987-107">Метод `Produce` записывает массивы, содержащие случайные байты данных, в объект <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType>, а метод `Consume` выполняет чтение байтов из объекта <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="04987-107">The `Produce` method writes arrays that contain random bytes of data to a <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> object and the `Consume` method reads bytes from a <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="04987-108">Используя интерфейсы <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> и <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> вместо их производных типов, можно создавать пригодный для повторного использования код, который может работать с различными типами блоков потока данных.</span><span class="sxs-lookup"><span data-stu-id="04987-108">By acting on the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> and <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> interfaces, instead of their derived types, you can write reusable code that can act on a variety of dataflow block types.</span></span> <span data-ttu-id="04987-109">В этом примере используется класс <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="04987-109">This example uses the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> class.</span></span> <span data-ttu-id="04987-110">Поскольку класс <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> действует и как блок источника, и как целевой блок, потребитель и производитель могут использовать общий объект для передачи данных.</span><span class="sxs-lookup"><span data-stu-id="04987-110">Because the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> class acts as both a source block and as a target block, the producer and the consumer can use a shared object to transfer data.</span></span>  
  
 <span data-ttu-id="04987-111">Метод `Produce` вызывает метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> в цикле для синхронной записи данных в целевой блок.</span><span class="sxs-lookup"><span data-stu-id="04987-111">The `Produce` method calls the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> method in a loop to synchronously write data to the target block.</span></span> <span data-ttu-id="04987-112">После того, как метод `Produce` записывает все данные в целевой блок, он вызывает метод <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A>, чтобы указать, что у этого блока никогда не будет дополнительных доступных данных.</span><span class="sxs-lookup"><span data-stu-id="04987-112">After the `Produce` method writes all data to the target block, it calls the <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> method to indicate that the block will never have additional data available.</span></span> <span data-ttu-id="04987-113">Метод `Consume` использует операторы [async](~/docs/csharp/language-reference/keywords/async.md) и [await](~/docs/csharp/language-reference/keywords/await.md) ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) и [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) в Visual Basic) для асинхронного вычисления общего числа байтов, полученных от объекта <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="04987-113">The `Consume` method uses the [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) operators ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in Visual Basic) to asynchronously compute the total number of bytes that are received from the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> object.</span></span> <span data-ttu-id="04987-114">Для асинхронной работы метод `Consume` вызывает метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>, чтобы получать уведомления, если блок источника получит доступные данные и если у блока источника никогда не будет дополнительных доступных данных.</span><span class="sxs-lookup"><span data-stu-id="04987-114">To act asynchronously, the `Consume` method calls the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> method to receive a notification when the source block has data available and when the source block will never have additional data available.</span></span>  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="04987-115">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="04987-115">Compiling the Code</span></span>  
 <span data-ttu-id="04987-116">Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `DataflowProducerConsumer.cs` (`DataflowProducerConsumer.vb` для Visual Basic), затем выполните в окне командной строки Visual Studio следующую команду.</span><span class="sxs-lookup"><span data-stu-id="04987-116">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowProducerConsumer.cs` (`DataflowProducerConsumer.vb` for Visual Basic), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="04987-117">Visual C#</span><span class="sxs-lookup"><span data-stu-id="04987-117">Visual C#</span></span>  
  
 <span data-ttu-id="04987-118">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**</span><span class="sxs-lookup"><span data-stu-id="04987-118">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**</span></span>  
  
 <span data-ttu-id="04987-119">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="04987-119">Visual Basic</span></span>  
  
 <span data-ttu-id="04987-120">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**</span><span class="sxs-lookup"><span data-stu-id="04987-120">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="04987-121">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="04987-121">Robust Programming</span></span>  
 <span data-ttu-id="04987-122">В этом примере используется только один получатель для обработки исходных данных.</span><span class="sxs-lookup"><span data-stu-id="04987-122">This example uses just one consumer to process the source data.</span></span> <span data-ttu-id="04987-123">При наличии нескольких получателей в приложении следует использовать метод <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> для чтения данных из блока источника, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="04987-123">If you have multiple consumers in your application, use the <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method to read data from the source block, as shown in the following example.</span></span>  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]  
  
 <span data-ttu-id="04987-124">Метод <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> возвращает `False`, когда нет доступных данных.</span><span class="sxs-lookup"><span data-stu-id="04987-124">The <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method returns `False` when no data is available.</span></span> <span data-ttu-id="04987-125">Когда несколько потребителей должны использовать блок источника параллельно, этот механизм гарантирует, что данные все еще будут доступны после вызова <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="04987-125">When multiple consumers must access the source block concurrently, this mechanism guarantees that data is still available after the call to <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04987-126">См. также</span><span class="sxs-lookup"><span data-stu-id="04987-126">See Also</span></span>  
 [<span data-ttu-id="04987-127">Поток данных</span><span class="sxs-lookup"><span data-stu-id="04987-127">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
