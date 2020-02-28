---
title: Практическое руководство. Обработка исключений в параллельных циклах
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to handle exceptions
ms.assetid: 512f0d5a-4636-4875-b766-88f20044f143
ms.openlocfilehash: 5d108937e6ab2483cd1633d4b398c1e250f5c098
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453017"
---
# <a name="how-to-handle-exceptions-in-parallel-loops"></a><span data-ttu-id="86962-102">Практическое руководство. Обработка исключений в параллельных циклах</span><span class="sxs-lookup"><span data-stu-id="86962-102">How to: Handle Exceptions in Parallel Loops</span></span>
<span data-ttu-id="86962-103">Перегрузки <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> не имеют каких-либо специальных механизмов для обработки возможных исключений.</span><span class="sxs-lookup"><span data-stu-id="86962-103">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> overloads do not have any special mechanism to handle exceptions that might be thrown.</span></span> <span data-ttu-id="86962-104">В этом отношении они напоминают обычные циклы `for` и `foreach` (`For` и `For Each` в Visual Basic). Необработанное исключение приводит к завершению цикла сразу после выполнения всех текущих итераций.</span><span class="sxs-lookup"><span data-stu-id="86962-104">In this respect, they resemble regular `for` and `foreach` loops (`For` and `For Each` in Visual Basic); an unhandled exception causes the loop to terminate as soon as all currently running iterations finish.</span></span>
  
 <span data-ttu-id="86962-105">При добавлении собственной логики обработки исключений в параллельные циклы обработка случая, в котором подобные исключения могут создаваться в нескольких потоках одновременно, и случая, в котором исключение создается в одном потоке, приводит к созданию еще одного исключения в другом потоке.</span><span class="sxs-lookup"><span data-stu-id="86962-105">When you add your own exception-handling logic to parallel loops, handle the case in which similar exceptions might be thrown on multiple threads concurrently, and the case in which an exception thrown on one thread causes another exception to be thrown on another thread.</span></span> <span data-ttu-id="86962-106">Оба случая можно обработать путем заключения всех исключений из цикла в <xref:System.AggregateException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="86962-106">You can handle both cases by wrapping all exceptions from the loop in a <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="86962-107">В примере ниже показан один из возможных способов.</span><span class="sxs-lookup"><span data-stu-id="86962-107">The following example shows one possible approach.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="86962-108">Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и выводит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом".</span><span class="sxs-lookup"><span data-stu-id="86962-108">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="86962-109">Эта ошибка не является критической.</span><span class="sxs-lookup"><span data-stu-id="86962-109">This error is benign.</span></span> <span data-ttu-id="86962-110">Вы можете нажать клавишу F5, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="86962-110">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the example below.</span></span> <span data-ttu-id="86962-111">Чтобы выполнение программы не прерывалось после первой ошибки в Visual Studio, снимите флажок "Только мой код" в меню **Сервис > Параметры > Отладка > Общие**.</span><span class="sxs-lookup"><span data-stu-id="86962-111">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86962-112">Пример</span><span class="sxs-lookup"><span data-stu-id="86962-112">Example</span></span>  
 <span data-ttu-id="86962-113">В этом примере все исключения перехватываются и заключаются в созданный объект <xref:System.AggregateException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="86962-113">In this example, all exceptions are caught and then wrapped in an <xref:System.AggregateException?displayProperty=nameWithType> which is thrown.</span></span> <span data-ttu-id="86962-114">Вызывающая сторона может решать, какие исключения обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="86962-114">The caller can decide which exceptions to handle.</span></span>  
  
 [!code-csharp[TPL_Exceptions#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#08)]
 [!code-vb[TPL_Exceptions#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionsinloops.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="86962-115">См. также</span><span class="sxs-lookup"><span data-stu-id="86962-115">See also</span></span>

- [<span data-ttu-id="86962-116">Параллелизм данных</span><span class="sxs-lookup"><span data-stu-id="86962-116">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="86962-117">Лямбда-выражения в PLINQ и TPL</span><span class="sxs-lookup"><span data-stu-id="86962-117">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
