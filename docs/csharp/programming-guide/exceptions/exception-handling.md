---
title: "Обработка исключений (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ab03e00a6b62d0c737c90fdb489be2a78f7ab6af
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="exception-handling-c-programming-guide"></a><span data-ttu-id="9fc60-102">Обработка исключений (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="9fc60-102">Exception Handling (C# Programming Guide)</span></span>
<span data-ttu-id="9fc60-103">Блок [try](../../../csharp/language-reference/keywords/try-catch.md) используется программистами C# для разбиения на разделы кода, который может затрагиваться исключением.</span><span class="sxs-lookup"><span data-stu-id="9fc60-103">A [try](../../../csharp/language-reference/keywords/try-catch.md) block is used by C# programmers to partition code that might be affected by an exception.</span></span> <span data-ttu-id="9fc60-104">Связанные с ним блоки [catch](../../../csharp/language-reference/keywords/try-catch.md) используются для обработки возможных исключений.</span><span class="sxs-lookup"><span data-stu-id="9fc60-104">Associated [catch](../../../csharp/language-reference/keywords/try-catch.md) blocks are used to handle any resulting exceptions.</span></span> <span data-ttu-id="9fc60-105">Блок [finally](../../../csharp/language-reference/keywords/try-finally.md) содержит код, выполняемый вне зависимости от того, вызывается ли исключение в блоке `try`, например для освобождения ресурсов, выделенных в блоке `try`.</span><span class="sxs-lookup"><span data-stu-id="9fc60-105">A [finally](../../../csharp/language-reference/keywords/try-finally.md) block contains code that is run regardless of whether or not an exception is thrown in the `try` block, such as releasing resources that are allocated in the `try` block.</span></span> <span data-ttu-id="9fc60-106">Блоку `try` требуется один или несколько связанных блоков `catch` или блок `finally` (либо и то, и другое).</span><span class="sxs-lookup"><span data-stu-id="9fc60-106">A `try` block requires one or more associated `catch` blocks, or a `finally` block, or both.</span></span>  
  
 <span data-ttu-id="9fc60-107">В приведенных ниже примерах показаны операторы `try-catch`, `try-finally` и `try-catch-finally`.</span><span class="sxs-lookup"><span data-stu-id="9fc60-107">The following examples show a `try-catch` statement, a `try-finally` statement, and a `try-catch-finally` statement.</span></span>  
  
 <span data-ttu-id="9fc60-108">[!code-cs[csProgGuideExceptions#6](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9fc60-108">[!code-cs[csProgGuideExceptions#6](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_1.cs)]</span></span>  
  
 <span data-ttu-id="9fc60-109">[!code-cs[csProgGuideExceptions#7](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9fc60-109">[!code-cs[csProgGuideExceptions#7](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_2.cs)]</span></span>  
  
 <span data-ttu-id="9fc60-110">[!code-cs[csProgGuideExceptions#8](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="9fc60-110">[!code-cs[csProgGuideExceptions#8](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_3.cs)]</span></span>  
  
 <span data-ttu-id="9fc60-111">Блок `try` без блока `catch` или блока `finally` вызовет ошибку компилятора.</span><span class="sxs-lookup"><span data-stu-id="9fc60-111">A `try` block without a `catch` or `finally` block causes a compiler error.</span></span>  
  
## <a name="catch-blocks"></a><span data-ttu-id="9fc60-112">Блоки catch</span><span class="sxs-lookup"><span data-stu-id="9fc60-112">Catch Blocks</span></span>  
 <span data-ttu-id="9fc60-113">Блок `catch` может определять тип перехватываемого исключения.</span><span class="sxs-lookup"><span data-stu-id="9fc60-113">A `catch` block can specify the type of exception to catch.</span></span> <span data-ttu-id="9fc60-114">Спецификация типа называется *фильтром исключений*.</span><span class="sxs-lookup"><span data-stu-id="9fc60-114">The type specification is called an *exception filter*.</span></span> <span data-ttu-id="9fc60-115">Тип исключения должен быть производным от <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="9fc60-115">The exception type should be derived from <xref:System.Exception>.</span></span> <span data-ttu-id="9fc60-116">Как правило, не следует задавать <xref:System.Exception> в качестве фильтра исключений, кроме случаев, когда известно, как обрабатывать все исключения, которые могут быть вызваны в блоке `try`, или когда оператор [throw](../../../csharp/language-reference/keywords/throw.md) добавлен в конце блока `catch`.</span><span class="sxs-lookup"><span data-stu-id="9fc60-116">In general, do not specify <xref:System.Exception> as the exception filter unless either you know how to handle all exceptions that might be thrown in the `try` block, or you have included a [throw](../../../csharp/language-reference/keywords/throw.md) statement at the end of your `catch` block.</span></span>  
  
 <span data-ttu-id="9fc60-117">Несколько блоков `catch` с различными фильтрами исключений могут быть соединены друг с другом.</span><span class="sxs-lookup"><span data-stu-id="9fc60-117">Multiple `catch` blocks with different exception filters can be chained together.</span></span> <span data-ttu-id="9fc60-118">Блоки `catch` проверяются сверху вниз в коде, однако для каждого вызванного исключения выполняется только один блок `catch`.</span><span class="sxs-lookup"><span data-stu-id="9fc60-118">The `catch` blocks are evaluated from top to bottom in your code, but only one `catch` block is executed for each exception that is thrown.</span></span> <span data-ttu-id="9fc60-119">Выполняется первый блок `catch`, в котором указан точный тип или базовый класс вызванного исключения.</span><span class="sxs-lookup"><span data-stu-id="9fc60-119">The first `catch` block that specifies the exact type or a base class of the thrown exception is executed.</span></span> <span data-ttu-id="9fc60-120">Если нет блока `catch`, в котором определен соответствующий фильтр исключений, выбирается блок `catch`, в котором не выбран фильтр, если таковой имеется в операторе.</span><span class="sxs-lookup"><span data-stu-id="9fc60-120">If no `catch` block specifies a matching exception filter, a `catch` block that does not have a filter is selected, if one is present in the statement.</span></span> <span data-ttu-id="9fc60-121">Важно, чтобы первыми были размещены блоки `catch` с самыми конкретными (т. е. самыми производными) типами исключений.</span><span class="sxs-lookup"><span data-stu-id="9fc60-121">It is important to position `catch` blocks with the most specific (that is, the most derived) exception types first.</span></span>  
  
 <span data-ttu-id="9fc60-122">Исключения следует перехватывать при выполнении указанных ниже условий.</span><span class="sxs-lookup"><span data-stu-id="9fc60-122">You should catch exceptions when the following conditions are true:</span></span>  
  
-   <span data-ttu-id="9fc60-123">Вы ясно понимаете возможные причины вызова исключения и можете выполнить восстановление, например, предложив пользователю ввести новое имя файла при перехвате объекта <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="9fc60-123">You have a good understanding of why the exception might be thrown, and you can implement a specific recovery, such as prompting the user to enter a new file name when you catch a <xref:System.IO.FileNotFoundException> object.</span></span>  
  
-   <span data-ttu-id="9fc60-124">Вы можете создать и вызвать новое, более конкретное исключение.</span><span class="sxs-lookup"><span data-stu-id="9fc60-124">You can create and throw a new, more specific exception.</span></span>  
  
     <span data-ttu-id="9fc60-125">[!code-cs[csProgGuideExceptions#9](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="9fc60-125">[!code-cs[csProgGuideExceptions#9](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_4.cs)]</span></span>  
  
-   <span data-ttu-id="9fc60-126">Требуется частично обработать исключение перед передачей его на дополнительную обработку.</span><span class="sxs-lookup"><span data-stu-id="9fc60-126">You want to partially handle an exception before passing it on for additional handling.</span></span> <span data-ttu-id="9fc60-127">В приведенном ниже примере блок `catch` используется для добавления записи в журнал ошибок перед повторным вызовом исключения.</span><span class="sxs-lookup"><span data-stu-id="9fc60-127">In the following example, a `catch` block is used to add an entry to an error log before re-throwing the exception.</span></span>  
  
     <span data-ttu-id="9fc60-128">[!code-cs[csProgGuideExceptions#10](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="9fc60-128">[!code-cs[csProgGuideExceptions#10](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_5.cs)]</span></span>  
  
## <a name="finally-blocks"></a><span data-ttu-id="9fc60-129">Блоки "Finally"</span><span class="sxs-lookup"><span data-stu-id="9fc60-129">Finally Blocks</span></span>  
 <span data-ttu-id="9fc60-130">Блок `finally` позволяет удалить действия, выполненные в блоке `try`.</span><span class="sxs-lookup"><span data-stu-id="9fc60-130">A `finally` block enables you to clean up actions that are performed in a `try` block.</span></span> <span data-ttu-id="9fc60-131">При наличии блока `finally` он выполняется последним, после блока `try` и всех выполняемых блоков `catch`.</span><span class="sxs-lookup"><span data-stu-id="9fc60-131">If present, the `finally` block executes last, after the `try` block and any matched `catch` block.</span></span> <span data-ttu-id="9fc60-132">Блок `finally` выполняется всегда вне зависимости от возникновения исключения или обнаружения блока `catch`, соответствующего типу исключения.</span><span class="sxs-lookup"><span data-stu-id="9fc60-132">A `finally` block always runs, regardless of whether an exception is thrown or a `catch` block matching the exception type is found.</span></span>  
  
 <span data-ttu-id="9fc60-133">Блок `finally` можно использовать для высвобождения ресурсов, например потоков данных, подключений к базам данных, графических дескрипторов, не ожидая финализации объектов сборщиком мусора во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9fc60-133">The `finally` block can be used to release resources such as file streams, database connections, and graphics handles without waiting for the garbage collector in the runtime to finalize the objects.</span></span> <span data-ttu-id="9fc60-134">Дополнительные сведения см. в разделе [Оператор using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9fc60-134">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) for more information.</span></span>  
  
 <span data-ttu-id="9fc60-135">В приведенном ниже примере с помощью блока `finally` закрывается файл, открытый в блоке `try`.</span><span class="sxs-lookup"><span data-stu-id="9fc60-135">In the following example, the `finally` block is used to close a file that is opened in the `try` block.</span></span> <span data-ttu-id="9fc60-136">Обратите внимание, что состояние дескриптора файла проверяется до закрытия файла.</span><span class="sxs-lookup"><span data-stu-id="9fc60-136">Notice that the state of the file handle is checked before the file is closed.</span></span> <span data-ttu-id="9fc60-137">Если блок `try` не может открыть этот файл, дескриптор файла по-прежнему имеет значение `null`, и блок `finally` не пытается закрыть его.</span><span class="sxs-lookup"><span data-stu-id="9fc60-137">If the `try` block cannot open the file, the file handle still has the value `null` and the `finally` block does not try to close it.</span></span> <span data-ttu-id="9fc60-138">Кроме того, если файл успешно открыт в блоке `try`, блок `finally` закрывает открытый файл.</span><span class="sxs-lookup"><span data-stu-id="9fc60-138">Alternatively, if the file is opened successfully in the `try` block, the `finally` block closes the open file.</span></span>  
  
 <span data-ttu-id="9fc60-139">[!code-cs[csProgGuideExceptions#11](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="9fc60-139">[!code-cs[csProgGuideExceptions#11](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_6.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="9fc60-140">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="9fc60-140">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9fc60-141">См. также</span><span class="sxs-lookup"><span data-stu-id="9fc60-141">See Also</span></span>  
 <span data-ttu-id="9fc60-142">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9fc60-142">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9fc60-143">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9fc60-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9fc60-144">[Исключения и обработка исключений](../../../csharp/programming-guide/exceptions/index.md) </span><span class="sxs-lookup"><span data-stu-id="9fc60-144">[Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md) </span></span>  
 <span data-ttu-id="9fc60-145">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="9fc60-145">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="9fc60-146">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span><span class="sxs-lookup"><span data-stu-id="9fc60-146">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span></span>  
 <span data-ttu-id="9fc60-147">[try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md) </span><span class="sxs-lookup"><span data-stu-id="9fc60-147">[try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md) </span></span>  
 [<span data-ttu-id="9fc60-148">Оператор using</span><span class="sxs-lookup"><span data-stu-id="9fc60-148">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)

