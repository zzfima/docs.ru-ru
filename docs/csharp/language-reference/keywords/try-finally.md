---
title: "try-finally (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- finally
- finally_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
caps.latest.revision: 25
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
ms.openlocfilehash: 88b9960b8c026d1fcd8eed1815ade57422cd2a15
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="try-finally-c-reference"></a><span data-ttu-id="6fcef-102">try-finally (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6fcef-102">try-finally (C# Reference)</span></span>
<span data-ttu-id="6fcef-103">С помощью блока `finally` можно выполнить очистку всех ресурсов, выделенных в блоке [try](../../../csharp/language-reference/keywords/try-catch.md), и запускать код даже при возникновении исключения в блоке `try`.</span><span class="sxs-lookup"><span data-stu-id="6fcef-103">By using a `finally` block, you can clean up any resources that are allocated in a [try](../../../csharp/language-reference/keywords/try-catch.md) block, and you can run code even if an exception occurs in the `try` block.</span></span> <span data-ttu-id="6fcef-104">Как правило, операторы блока `finally` выполняются, когда элемент управления покидает оператор `try`.</span><span class="sxs-lookup"><span data-stu-id="6fcef-104">Typically, the statements of a `finally` block run when control leaves a `try` statement.</span></span> <span data-ttu-id="6fcef-105">Передача управления может возникать в результате нормального выполнения, выполнения операторов `break`, `continue`, `goto` или `return` или распространения исключения из оператора `try`.</span><span class="sxs-lookup"><span data-stu-id="6fcef-105">The transfer of control can occur as a result of normal execution, of execution of a `break`, `continue`, `goto`, or `return` statement, or of propagation of an exception out of the `try` statement.</span></span>  
  
 <span data-ttu-id="6fcef-106">Внутри обработанного исключения гарантируется выполнение связанного блока `finally`.</span><span class="sxs-lookup"><span data-stu-id="6fcef-106">Within a handled exception, the associated `finally` block is guaranteed to be run.</span></span> <span data-ttu-id="6fcef-107">Однако если исключение не обработано, то выполнение блока `finally` зависит от того, как запускается операция развертывания исключения.</span><span class="sxs-lookup"><span data-stu-id="6fcef-107">However, if the exception is unhandled, execution of the `finally` block is dependent on how the exception unwind operation is triggered.</span></span> <span data-ttu-id="6fcef-108">Это, в свою очередь, зависит от способа настройки компьютера.</span><span class="sxs-lookup"><span data-stu-id="6fcef-108">That, in turn, is dependent on how your computer is set up.</span></span> <span data-ttu-id="6fcef-109">Дополнительные сведения см. в разделе [Обработка необработанных исключений в CLR](http://go.microsoft.com/fwlink/?LinkId=128371).</span><span class="sxs-lookup"><span data-stu-id="6fcef-109">For more information, see [Unhandled Exception Processing in the CLR](http://go.microsoft.com/fwlink/?LinkId=128371).</span></span>  
  
 <span data-ttu-id="6fcef-110">Как правило, когда необработанное исключение приводит к завершению работы приложения, выполнение блока `finally` не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="6fcef-110">Usually, when an unhandled exception ends an application, whether or not the `finally` block is run is not important.</span></span> <span data-ttu-id="6fcef-111">Однако если в блоке `finally` есть операторы, которые необходимо запускать даже в такой ситуации, одним из решений является добавление блока `catch` в оператор `try`-`finally`.</span><span class="sxs-lookup"><span data-stu-id="6fcef-111">However, if you have statements in a `finally` block that must be run even in that situation, one solution is to add a `catch` block to the `try`-`finally` statement.</span></span> <span data-ttu-id="6fcef-112">Кроме того, можно перехватить исключение, которое может создаваться в блоке `try` оператора `try`-`finally` выше в стеке вызовов.</span><span class="sxs-lookup"><span data-stu-id="6fcef-112">Alternatively, you can catch the exception that might be thrown in the `try` block of a `try`-`finally` statement higher up the call stack.</span></span> <span data-ttu-id="6fcef-113">То есть можно перехватить исключение в методе, который вызывает метод, содержащий оператор `try`-`finally`, или в методе, который вызывает этот метод, или в любом методе в стеке вызовов.</span><span class="sxs-lookup"><span data-stu-id="6fcef-113">That is, you can catch the exception in the method that calls the method that contains the `try`-`finally` statement, or in the method that calls that method, or in any method in the call stack.</span></span> <span data-ttu-id="6fcef-114">Если исключение не перехвачено, выполнение блока `finally` зависит от того, активирует ли операционная система операцию развертывания исключения.</span><span class="sxs-lookup"><span data-stu-id="6fcef-114">If the exception is not caught, execution of the `finally` block depends on whether the operating system chooses to trigger an exception unwind operation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fcef-115">Пример</span><span class="sxs-lookup"><span data-stu-id="6fcef-115">Example</span></span>  
 <span data-ttu-id="6fcef-116">В следующем примере недопустимый оператор преобразования вызывает исключение `System.InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="6fcef-116">In the following example, an invalid conversion statement causes a `System.InvalidCastException` exception.</span></span> <span data-ttu-id="6fcef-117">Исключение не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="6fcef-117">The exception is unhandled.</span></span>  
  
 <span data-ttu-id="6fcef-118">[!code-cs[csrefKeywordsExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6fcef-118">[!code-cs[csrefKeywordsExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_1.cs)]</span></span>  
  
 <span data-ttu-id="6fcef-119">В следующем примере исключение из метода `TryCast` перехватывается в методе выше в стеке вызовов.</span><span class="sxs-lookup"><span data-stu-id="6fcef-119">In the following example, an exception from the `TryCast` method is caught in a method farther up the call stack.</span></span>  
  
 <span data-ttu-id="6fcef-120">[!code-cs[csrefKeywordsExceptions#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6fcef-120">[!code-cs[csrefKeywordsExceptions#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_2.cs)]</span></span>  
  
 <span data-ttu-id="6fcef-121">Дополнительные сведения о `finally` см. в разделе [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="6fcef-121">For more information about `finally`, see [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span></span>  
  
 <span data-ttu-id="6fcef-122">C# также содержит [оператор using](../../../csharp/language-reference/keywords/using-statement.md), который предоставляет аналогичную функциональность для объектов <xref:System.IDisposable> в удобном синтаксисе.</span><span class="sxs-lookup"><span data-stu-id="6fcef-122">C# also contains the [using statement](../../../csharp/language-reference/keywords/using-statement.md), which provides similar functionality for <xref:System.IDisposable> objects in a convenient syntax.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6fcef-123">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6fcef-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6fcef-124">См. также</span><span class="sxs-lookup"><span data-stu-id="6fcef-124">See Also</span></span>  
 <span data-ttu-id="6fcef-125">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6fcef-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6fcef-126">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6fcef-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6fcef-127">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="6fcef-127">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="6fcef-128">[Операторы try, throw и catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span><span class="sxs-lookup"><span data-stu-id="6fcef-128">[try, throw, and catch Statements (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span></span>  
 <span data-ttu-id="6fcef-129">[Операторы обработки исключений](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span><span class="sxs-lookup"><span data-stu-id="6fcef-129">[Exception Handling Statements](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span></span>  
 <span data-ttu-id="6fcef-130">[throw](../../../csharp/language-reference/keywords/throw.md) </span><span class="sxs-lookup"><span data-stu-id="6fcef-130">[throw](../../../csharp/language-reference/keywords/throw.md) </span></span>  
 <span data-ttu-id="6fcef-131">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="6fcef-131">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 [<span data-ttu-id="6fcef-132">Практическое руководство. Явное создание исключений</span><span class="sxs-lookup"><span data-stu-id="6fcef-132">How to: Explicitly Throw Exceptions</span></span>](https://msdn.microsoft.com/library/xhcbs8fz)

