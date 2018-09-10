---
title: Практическое руководство. Удаление связей с блоками потоков данных
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow blocks, unlinking in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, unlinking dataflow blocks
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65d42597c572a85a95f9e2b4407df42c6fb7bb3d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43407895"
---
# <a name="how-to-unlink-dataflow-blocks"></a><span data-ttu-id="d965e-102">Практическое руководство. Удаление связей с блоками потоков данных</span><span class="sxs-lookup"><span data-stu-id="d965e-102">How to: Unlink Dataflow Blocks</span></span>
<span data-ttu-id="d965e-103">В этом документе описан способ отсоединения целевого блока потока данных от его источника.</span><span class="sxs-lookup"><span data-stu-id="d965e-103">This document describes how to unlink a target dataflow block from its source.</span></span>

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a><span data-ttu-id="d965e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d965e-104">Example</span></span>  
 <span data-ttu-id="d965e-105">В следующем примере создаются три объекта <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, каждый из которых вызывает метод `TrySolution` для вычисления значения.</span><span class="sxs-lookup"><span data-stu-id="d965e-105">The following example creates three <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objects, each of which calls the `TrySolution` method to compute a value.</span></span> <span data-ttu-id="d965e-106">В этом примере для завершения требуется только результат первого вызова `TrySolution`.</span><span class="sxs-lookup"><span data-stu-id="d965e-106">This example requires only the result from the first call to `TrySolution` to finish.</span></span>  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 <span data-ttu-id="d965e-107">Чтобы получить значение от первого завершившегося объекта <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, в этом примере определяется метод `ReceiveFromAny(T)`.</span><span class="sxs-lookup"><span data-stu-id="d965e-107">To receive the value from the first <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> object that finishes, this example defines the `ReceiveFromAny(T)` method.</span></span> <span data-ttu-id="d965e-108">Метод `ReceiveFromAny(T)` принимает массив объектов <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> и связывает каждый из этих объектов с объектом <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="d965e-108">The `ReceiveFromAny(T)` method accepts an array of <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> objects and links each of these objects to a <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object.</span></span> <span data-ttu-id="d965e-109">При использовании метода <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> для привязки блока источника потока данных к целевому блоку источник передает сообщения целевому объекту по мере поступления данных.</span><span class="sxs-lookup"><span data-stu-id="d965e-109">When you use the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method to link a source dataflow block to a target block, the source propagates messages to the target as data becomes available.</span></span> <span data-ttu-id="d965e-110">Поскольку класс <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> принимает только первое предлагаемое сообщение, метод `ReceiveFromAny(T)` получает результат путем вызова метода <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A>.</span><span class="sxs-lookup"><span data-stu-id="d965e-110">Because the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> class accepts only the first message that it is offered, the `ReceiveFromAny(T)` method produces its result by calling the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> method.</span></span> <span data-ttu-id="d965e-111">Таким образом создается первое сообщение, которое предлагается объекту <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="d965e-111">This produces the first message that is offered to the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object.</span></span> <span data-ttu-id="d965e-112">Метод <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> имеет перегруженную версию, которая принимает объект <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions> со свойством <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions.MaxMessages>, которое, если оно имеет значение `1`, обеспечивает отсоединение источника данных от целевого объекта после того, как целевой объект получит одно сообщение от источника.</span><span class="sxs-lookup"><span data-stu-id="d965e-112">The <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method has an overloaded version that takes an <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions> object with a <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions.MaxMessages> property that, when it is set to `1`, instructs the source block to unlink from the target after the target receives one message from the source.</span></span> <span data-ttu-id="d965e-113">Для объекта <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> важно отсоединиться от источников, поскольку связь между массивом источников и объектом <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> больше не требуется после того, как объект <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> получает сообщение.</span><span class="sxs-lookup"><span data-stu-id="d965e-113">It is important for the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object to unlink from its sources because the relationship between the array of sources and the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object is no longer required after the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object receives a message.</span></span>  
  
 <span data-ttu-id="d965e-114">Чтобы оставшиеся вызовы `TrySolution` могли завершиться после вычисления значения одним из них, метод `TrySolution` принимает объект <xref:System.Threading.CancellationToken>, который отменяется после возврата вызова `ReceiveFromAny(T)`.</span><span class="sxs-lookup"><span data-stu-id="d965e-114">To enable the remaining calls to `TrySolution` to end after one of them computes a value, the `TrySolution` method takes a <xref:System.Threading.CancellationToken> object that is canceled after the call to `ReceiveFromAny(T)` returns.</span></span> <span data-ttu-id="d965e-115">Метод <xref:System.Threading.SpinWait.SpinUntil%2A> возвращает результат, когда объект <xref:System.Threading.CancellationToken> отменяется.</span><span class="sxs-lookup"><span data-stu-id="d965e-115">The <xref:System.Threading.SpinWait.SpinUntil%2A> method returns when this <xref:System.Threading.CancellationToken> object is canceled.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d965e-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="d965e-116">Compiling the Code</span></span>  
 <span data-ttu-id="d965e-117">Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `DataflowReceiveAny.cs` (`DataflowReceiveAny.vb` для Visual Basic), затем выполните в окне командной строки Visual Studio следующую команду.</span><span class="sxs-lookup"><span data-stu-id="d965e-117">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowReceiveAny.cs` (`DataflowReceiveAny.vb` for Visual Basic), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 <span data-ttu-id="d965e-118">Visual C#</span><span class="sxs-lookup"><span data-stu-id="d965e-118">Visual C#</span></span>  
  
 <span data-ttu-id="d965e-119">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**</span><span class="sxs-lookup"><span data-stu-id="d965e-119">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**</span></span>  
  
 <span data-ttu-id="d965e-120">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d965e-120">Visual Basic</span></span>  
  
 <span data-ttu-id="d965e-121">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**</span><span class="sxs-lookup"><span data-stu-id="d965e-121">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**</span></span>  

## <a name="see-also"></a><span data-ttu-id="d965e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="d965e-122">See Also</span></span>  
 [<span data-ttu-id="d965e-123">Поток данных</span><span class="sxs-lookup"><span data-stu-id="d965e-123">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
