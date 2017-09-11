---
title: "Использование исключений (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], about exceptions
ms.assetid: 71472c62-320a-470a-97d2-67995180389d
caps.latest.revision: 15
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
ms.openlocfilehash: 96fc082d135d38f521429de7b4e9a668773982ea
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="using-exceptions-c-programming-guide"></a><span data-ttu-id="a8e5f-102">Использование исключений (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="a8e5f-102">Using Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="a8e5f-103">В C# ошибки в программе в среде выполнения передаются через программу с помощью механизма, который называется исключениями.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-103">In C#, errors in the program at run time are propagated through the program by using a mechanism called exceptions.</span></span> <span data-ttu-id="a8e5f-104">Исключения вызываются кодом, который встречает ошибку, и перехватываются кодом, который может ее исправить.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-104">Exceptions are thrown by code that encounters an error and caught by code that can correct the error.</span></span> <span data-ttu-id="a8e5f-105">Исключения могут вызываться средой CLR .NET Framework или кодом в программе.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-105">Exceptions can be thrown by the .NET Framework common language runtime (CLR) or by code in a program.</span></span> <span data-ttu-id="a8e5f-106">Вызванное исключение передается вверх по стеку вызовов, пока не будет найден соответствующий оператор `catch`.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-106">Once an exception is thrown, it propagates up the call stack until a `catch` statement for the exception is found.</span></span> <span data-ttu-id="a8e5f-107">Не перехваченные исключения обрабатываются универсальным обработчиком исключений, предоставляемым системой, которая отображает диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-107">Uncaught exceptions are handled by a generic exception handler provided by the system that displays a dialog box.</span></span>  
  
 <span data-ttu-id="a8e5f-108">Исключения представляются классами, производными от <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-108">Exceptions are represented by classes derived from <xref:System.Exception>.</span></span> <span data-ttu-id="a8e5f-109">Этот класс определяет тип исключения и содержит свойства с подробными сведениями об исключении.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-109">This class identifies the type of exception and contains properties that have details about the exception.</span></span> <span data-ttu-id="a8e5f-110">При вызове исключения создается экземпляр производного класса, а также могут настраиваться свойства исключения. После этого с помощью ключевого слова `throw` вызывается объект.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-110">Throwing an exception involves creating an instance of an exception-derived class, optionally configuring properties of the exception, and then throwing the object by using the `throw` keyword.</span></span> <span data-ttu-id="a8e5f-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="a8e5f-111">For example:</span></span>  
  
 <span data-ttu-id="a8e5f-112">[!code-cs[csProgGuideExceptions#1](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8e5f-112">[!code-cs[csProgGuideExceptions#1](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_1.cs)]</span></span>  
  
 <span data-ttu-id="a8e5f-113">После выдачи исключения среда выполнения проверяет, входит ли текущий оператор в блок `try`.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-113">After an exception is thrown, the runtime checks the current statement to see whether it is within a `try` block.</span></span> <span data-ttu-id="a8e5f-114">Если да, она проверяет, может ли какой-либо из блоков `catch`, связанных с блоком `try`, перехватить исключение.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-114">If it is, any `catch` blocks associated with the `try` block are checked to see whether they can catch the exception.</span></span> <span data-ttu-id="a8e5f-115">Блоки `Catch` обычно задают типы исключений; если тип блока `catch` совпадает с типом или базовым классом исключения, блок `catch` может обработать этот метод.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-115">`Catch` blocks typically specify exception types; if the type of the `catch` block is the same type as the exception, or a base class of the exception, the `catch` block can handle the method.</span></span> <span data-ttu-id="a8e5f-116">Например:</span><span class="sxs-lookup"><span data-stu-id="a8e5f-116">For example:</span></span>  
  
 <span data-ttu-id="a8e5f-117">[!code-cs[csProgGuideExceptions#2](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8e5f-117">[!code-cs[csProgGuideExceptions#2](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_2.cs)]</span></span>  
  
 <span data-ttu-id="a8e5f-118">Если оператор, который вызывает исключение, не находится в блоке `try` или блок `try`, в который он входит, не имеет соответствующего блока `catch`, среда выполнения проверяет вызывающий метод на наличие оператора `try` и блоков `catch`.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-118">If the statement that throws an exception is not within a `try` block or if the `try` block that encloses it has no matching `catch` block, the runtime checks the calling method for a `try` statement and `catch` blocks.</span></span> <span data-ttu-id="a8e5f-119">Среда выполнения продолжает перебирать стек вызовов в поиска подходящего блока `catch`.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-119">The runtime continues up the calling stack, searching for a compatible `catch` block.</span></span> <span data-ttu-id="a8e5f-120">После того как блок `catch` будет найден и выполнен, управление передается оператору, следующему после блока `catch`.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-120">After the `catch` block is found and executed, control is passed to the next statement after that `catch` block.</span></span>  
  
 <span data-ttu-id="a8e5f-121">Оператор `try` может содержать не один блок `catch`.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-121">A `try` statement can contain more than one `catch` block.</span></span> <span data-ttu-id="a8e5f-122">Выполняется первый оператор `catch`, который может обработать исключение; все последующие операторы `catch` игнорируются, даже если они совместимы.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-122">The first `catch` statement that can handle the exception is executed; any following `catch` statements, even if they are compatible, are ignored.</span></span> <span data-ttu-id="a8e5f-123">В связи с этим блоки catch следует располагать в порядке от наиболее конкретных (наиболее производных) до наименее конкретных.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-123">Therefore, catch blocks should always be ordered from most specific (or most-derived) to least specific.</span></span> <span data-ttu-id="a8e5f-124">Пример:</span><span class="sxs-lookup"><span data-stu-id="a8e5f-124">For example:</span></span>  
  
 <span data-ttu-id="a8e5f-125">[!code-cs[csProgGuideExceptions#3](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8e5f-125">[!code-cs[csProgGuideExceptions#3](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_3.cs)]</span></span>  
  
 <span data-ttu-id="a8e5f-126">Прежде чем выполнять блок `catch`, среда выполнения проверяет наличие блоков `finally`.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-126">Before the `catch` block is executed, the runtime checks for `finally` blocks.</span></span> <span data-ttu-id="a8e5f-127">Блоки `Finally` позволяют программисту удалить любое неоднозначное состояние, которое может остаться после прерванного блока `try`, а также освободить любые внешние ресурсы (включая обработчики графики, соединители баз данных или файловые потоки), не дожидаясь, пока сборщик мусора в среде выполнения завершит объекты.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-127">`Finally` blocks enable the programmer to clean up any ambiguous state that could be left over from an aborted `try` block, or to release any external resources (such as graphics handles, database connections or file streams) without waiting for the garbage collector in the runtime to finalize the objects.</span></span> <span data-ttu-id="a8e5f-128">Пример:</span><span class="sxs-lookup"><span data-stu-id="a8e5f-128">For example:</span></span>  
  
 <span data-ttu-id="a8e5f-129">[!code-cs[csProgGuideExceptions#4](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8e5f-129">[!code-cs[csProgGuideExceptions#4](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_4.cs)]</span></span>  
  
 <span data-ttu-id="a8e5f-130">Если `WriteByte()` выдает исключение, код во втором блоке `try`, который пытается открыть файл повторно, завершается ошибкой, если `file.Close()` не вызывается, а файл остается заблокированным.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-130">If `WriteByte()` threw an exception, the code in the second `try` block that tries to reopen the file would fail if `file.Close()` is not called, and the file would remain locked.</span></span> <span data-ttu-id="a8e5f-131">Поскольку блоки `finally` выполняются, даже если выдается исключение, блок `finally` в предыдущем примере обеспечивает правильное закрытие файла и помогает избежать ошибки.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-131">Because `finally` blocks are executed even if an exception is thrown, the `finally` block in the previous example allows for the file to be closed correctly and helps avoid an error.</span></span>  
  
 <span data-ttu-id="a8e5f-132">Если после выдачи исключения обнаружить совместимый блок `catch` в стеке вызовов не удается, происходит одно из трех:</span><span class="sxs-lookup"><span data-stu-id="a8e5f-132">If no compatible `catch` block is found on the call stack after an exception is thrown, one of three things occurs:</span></span>  
  
-   <span data-ttu-id="a8e5f-133">Если исключение возникает в методе завершения, он прерывается, и вызывается базовый метод завершения (если есть).</span><span class="sxs-lookup"><span data-stu-id="a8e5f-133">If the exception is within a finalizer, the finalizer is aborted and the base finalizer, if any, is called.</span></span>  
  
-   <span data-ttu-id="a8e5f-134">Если стек вызовов содержит статический конструктор или инициализатор статического поля, выдается исключение <xref:System.TypeInitializationException>, а исходное исключение назначается свойству <xref:System.Exception.InnerException%2A> нового исключения.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-134">If the call stack contains a static constructor, or a static field initializer, a <xref:System.TypeInitializationException> is thrown, with the original exception assigned to the <xref:System.Exception.InnerException%2A> property of the new exception.</span></span>  
  
-   <span data-ttu-id="a8e5f-135">Как только достигается начало потока, он прерывается.</span><span class="sxs-lookup"><span data-stu-id="a8e5f-135">If the start of the thread is reached, the thread is terminated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8e5f-136">См. также</span><span class="sxs-lookup"><span data-stu-id="a8e5f-136">See Also</span></span>  
 <span data-ttu-id="a8e5f-137">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a8e5f-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="a8e5f-138">Исключения и обработка исключений</span><span class="sxs-lookup"><span data-stu-id="a8e5f-138">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)

