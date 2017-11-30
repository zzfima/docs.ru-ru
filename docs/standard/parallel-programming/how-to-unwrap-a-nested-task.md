---
title: "Практическое руководство. Извлечение вложенной задачи из оболочки"
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
helpviewer_keywords: tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2da3de912abb693c4342e1ede02f273348e4b571
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-unwrap-a-nested-task"></a><span data-ttu-id="cae7c-102">Практическое руководство. Извлечение вложенной задачи из оболочки</span><span class="sxs-lookup"><span data-stu-id="cae7c-102">How to: Unwrap a Nested Task</span></span>
<span data-ttu-id="cae7c-103">Можно вернуть задачу из метода и затем ожидать или продолжить с этой задачи, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="cae7c-103">You can return a task from a method, and then wait on or continue from that task, as shown in the following example:</span></span>  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 <span data-ttu-id="cae7c-104">В предыдущем примере <xref:System.Threading.Tasks.Task%601.Result%2A> свойство относится к типу `string` (`String` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="cae7c-104">In the previous example, the <xref:System.Threading.Tasks.Task%601.Result%2A> property is of type `string` (`String` in Visual Basic).</span></span>  
  
 <span data-ttu-id="cae7c-105">Однако в некоторых сценариях может потребоваться создать задачу в другую задачу, а затем возвращаете вложенной задачи.</span><span class="sxs-lookup"><span data-stu-id="cae7c-105">However, in some scenarios, you might want to create a task within another task, and then return the nested task.</span></span> <span data-ttu-id="cae7c-106">В этом случае `TResult` присоединенной задачи является задачей.</span><span class="sxs-lookup"><span data-stu-id="cae7c-106">In this case, the `TResult` of the enclosing task is itself a task.</span></span> <span data-ttu-id="cae7c-107">В следующем примере свойство результат является `Task<Task<string>>` в C# или `Task(Of Task(Of String))` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="cae7c-107">In the following example, the Result property is a `Task<Task<string>>` in C# or `Task(Of Task(Of String))` in Visual Basic.</span></span>  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 <span data-ttu-id="cae7c-108">Несмотря на то, что можно написать код для распаковки внешней задачи и извлечения исходной задачи и ее <xref:System.Threading.Tasks.Task%601.Result%2A> свойство, такой код не просто запись, так как необходимо обрабатывать исключения, а также запросы отмены.</span><span class="sxs-lookup"><span data-stu-id="cae7c-108">Although it is possible to write code to unwrap the outer task and retrieve the original task and its <xref:System.Threading.Tasks.Task%601.Result%2A> property, such code is not easy to write because you must handle exceptions and also cancellation requests.</span></span> <span data-ttu-id="cae7c-109">В этом случае рекомендуется использовать один из <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> методы расширения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="cae7c-109">In this situation, we recommend that you use one of the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods, as shown in the following example.</span></span>  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 <span data-ttu-id="cae7c-110"><xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> Методы можно использовать для преобразования любого `Task<Task>` или `Task<Task<TResult>>` (`Task(Of Task)` или `Task(Of Task(Of TResult))` в Visual Basic) для `Task` или `Task<TResult>` (`Task(Of TResult)` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="cae7c-110">The <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> methods can be used to transform any `Task<Task>` or `Task<Task<TResult>>` (`Task(Of Task)` or `Task(Of Task(Of TResult))` in Visual Basic) to a `Task` or `Task<TResult>` (`Task(Of TResult)` in Visual Basic).</span></span> <span data-ttu-id="cae7c-111">Новая задача полностью представляет внутреннюю вложенную задачу и включает состояние отмены и все исключения.</span><span class="sxs-lookup"><span data-stu-id="cae7c-111">The new task fully represents the inner nested task, and includes cancellation state and all exceptions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cae7c-112">Пример</span><span class="sxs-lookup"><span data-stu-id="cae7c-112">Example</span></span>  
 <span data-ttu-id="cae7c-113">В следующем примере демонстрируется использование <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> методы расширения.</span><span class="sxs-lookup"><span data-stu-id="cae7c-113">The following example demonstrates how to use the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods.</span></span>  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="cae7c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="cae7c-114">See Also</span></span>  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>  
 [<span data-ttu-id="cae7c-115">Асинхронное программирование на основе задач</span><span class="sxs-lookup"><span data-stu-id="cae7c-115">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
