---
title: Практическое руководство. Извлечение вложенной задачи
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
ms.openlocfilehash: c72654a2bc21035fe706d76018bb163d8ba01ee8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73106909"
---
# <a name="how-to-unwrap-a-nested-task"></a><span data-ttu-id="dffd0-102">Практическое руководство. Извлечение вложенной задачи</span><span class="sxs-lookup"><span data-stu-id="dffd0-102">How to: Unwrap a Nested Task</span></span>
<span data-ttu-id="dffd0-103">Вы можете вернуть задачу из метода, и затем ожидать ее выполнения или продолжить работу после нее, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="dffd0-103">You can return a task from a method, and then wait on or continue from that task, as shown in the following example:</span></span>  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 <span data-ttu-id="dffd0-104">В предыдущем примере свойство <xref:System.Threading.Tasks.Task%601.Result%2A> имеет тип `string` (`String` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="dffd0-104">In the previous example, the <xref:System.Threading.Tasks.Task%601.Result%2A> property is of type `string` (`String` in Visual Basic).</span></span>  
  
 <span data-ttu-id="dffd0-105">Но в некоторых сценариях будет удобно создать в задаче другую задачу и возвратить эту вложенную задачу.</span><span class="sxs-lookup"><span data-stu-id="dffd0-105">However, in some scenarios, you might want to create a task within another task, and then return the nested task.</span></span> <span data-ttu-id="dffd0-106">В этом случае `TResult` вызывающей задачи является новой задачей.</span><span class="sxs-lookup"><span data-stu-id="dffd0-106">In this case, the `TResult` of the enclosing task is itself a task.</span></span> <span data-ttu-id="dffd0-107">В следующем примере в свойстве Result возвращается `Task<Task<string>>` (в C#) или `Task(Of Task(Of String))` (в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="dffd0-107">In the following example, the Result property is a `Task<Task<string>>` in C# or `Task(Of Task(Of String))` in Visual Basic.</span></span>  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 <span data-ttu-id="dffd0-108">Вы можете написать свой код, который распаковывает внешнюю задачу и извлекает исходную задачу и ее свойство <xref:System.Threading.Tasks.Task%601.Result%2A>. Но обработка исключений и возможных запросов отмены существенно усложняет такой код.</span><span class="sxs-lookup"><span data-stu-id="dffd0-108">Although it is possible to write code to unwrap the outer task and retrieve the original task and its <xref:System.Threading.Tasks.Task%601.Result%2A> property, such code is not easy to write because you must handle exceptions and also cancellation requests.</span></span> <span data-ttu-id="dffd0-109">Поэтому в такой ситуации мы рекомендуем использовать один из методов расширения <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="dffd0-109">In this situation, we recommend that you use one of the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods, as shown in the following example.</span></span>  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 <span data-ttu-id="dffd0-110">С помощью методов <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> можно преобразовать любой объект `Task<Task>` или `Task<Task<TResult>>` (`Task(Of Task)` или `Task(Of Task(Of TResult))` в Visual Basic) в `Task` или `Task<TResult>` (`Task(Of TResult)` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="dffd0-110">The <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> methods can be used to transform any `Task<Task>` or `Task<Task<TResult>>` (`Task(Of Task)` or `Task(Of Task(Of TResult))` in Visual Basic) to a `Task` or `Task<TResult>` (`Task(Of TResult)` in Visual Basic).</span></span> <span data-ttu-id="dffd0-111">Новая задача в полной мере представляет внутреннюю вложенную задачу с поддержкой состояния отмены и всех исключений.</span><span class="sxs-lookup"><span data-stu-id="dffd0-111">The new task fully represents the inner nested task, and includes cancellation state and all exceptions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dffd0-112">Пример</span><span class="sxs-lookup"><span data-stu-id="dffd0-112">Example</span></span>  
 <span data-ttu-id="dffd0-113">В следующем примере показано, как использовать методы расширения <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>.</span><span class="sxs-lookup"><span data-stu-id="dffd0-113">The following example demonstrates how to use the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods.</span></span>  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="dffd0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="dffd0-114">See also</span></span>

- <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>
- [<span data-ttu-id="dffd0-115">Асинхронное программирование на основе задач</span><span class="sxs-lookup"><span data-stu-id="dffd0-115">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
