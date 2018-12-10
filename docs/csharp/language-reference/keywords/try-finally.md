---
title: try-finally (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- finally
- finally_CSharpKeyword
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
ms.openlocfilehash: 227c880aab89d0ada4431dc50148c36ce00cfda8
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155162"
---
# <a name="try-finally-c-reference"></a><span data-ttu-id="c2ab2-102">try-finally (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c2ab2-102">try-finally (C# Reference)</span></span>

<span data-ttu-id="c2ab2-103">С помощью блока `finally` можно выполнить очистку всех ресурсов, выделенных в блоке [try](try-catch.md), и запускать код даже при возникновении исключения в блоке `try`.</span><span class="sxs-lookup"><span data-stu-id="c2ab2-103">By using a `finally` block, you can clean up any resources that are allocated in a [try](try-catch.md) block, and you can run code even if an exception occurs in the `try` block.</span></span> <span data-ttu-id="c2ab2-104">Как правило, операторы блока `finally` выполняются, когда элемент управления покидает оператор `try`.</span><span class="sxs-lookup"><span data-stu-id="c2ab2-104">Typically, the statements of a `finally` block run when control leaves a `try` statement.</span></span> <span data-ttu-id="c2ab2-105">Передача управления может возникать в результате нормального выполнения, выполнения операторов `break`, `continue`, `goto` или `return` или распространения исключения из оператора `try`.</span><span class="sxs-lookup"><span data-stu-id="c2ab2-105">The transfer of control can occur as a result of normal execution, of execution of a `break`, `continue`, `goto`, or `return` statement, or of propagation of an exception out of the `try` statement.</span></span>

<span data-ttu-id="c2ab2-106">Внутри обработанного исключения гарантируется выполнение связанного блока `finally`.</span><span class="sxs-lookup"><span data-stu-id="c2ab2-106">Within a handled exception, the associated `finally` block is guaranteed to be run.</span></span> <span data-ttu-id="c2ab2-107">Однако если исключение не обработано, то выполнение блока `finally` зависит от того, как запускается операция развертывания исключения.</span><span class="sxs-lookup"><span data-stu-id="c2ab2-107">However, if the exception is unhandled, execution of the `finally` block is dependent on how the exception unwind operation is triggered.</span></span> <span data-ttu-id="c2ab2-108">Это, в свою очередь, зависит от способа настройки компьютера.</span><span class="sxs-lookup"><span data-stu-id="c2ab2-108">That, in turn, is dependent on how your computer is set up.</span></span>

<span data-ttu-id="c2ab2-109">Как правило, когда необработанное исключение приводит к завершению работы приложения, выполнение блока `finally` не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="c2ab2-109">Usually, when an unhandled exception ends an application, whether or not the `finally` block is run is not important.</span></span> <span data-ttu-id="c2ab2-110">Однако если в блоке `finally` есть операторы, которые необходимо запускать даже в такой ситуации, одним из решений является добавление блока `catch` в оператор `try`-`finally`.</span><span class="sxs-lookup"><span data-stu-id="c2ab2-110">However, if you have statements in a `finally` block that must be run even in that situation, one solution is to add a `catch` block to the `try`-`finally` statement.</span></span> <span data-ttu-id="c2ab2-111">Кроме того, можно перехватить исключение, которое может создаваться в блоке `try` оператора `try`-`finally` выше в стеке вызовов.</span><span class="sxs-lookup"><span data-stu-id="c2ab2-111">Alternatively, you can catch the exception that might be thrown in the `try` block of a `try`-`finally` statement higher up the call stack.</span></span> <span data-ttu-id="c2ab2-112">То есть можно перехватить исключение в методе, который вызывает метод, содержащий оператор `try`-`finally`, или в методе, который вызывает этот метод, или в любом методе в стеке вызовов.</span><span class="sxs-lookup"><span data-stu-id="c2ab2-112">That is, you can catch the exception in the method that calls the method that contains the `try`-`finally` statement, or in the method that calls that method, or in any method in the call stack.</span></span> <span data-ttu-id="c2ab2-113">Если исключение не перехвачено, выполнение блока `finally` зависит от того, активирует ли операционная система операцию развертывания исключения.</span><span class="sxs-lookup"><span data-stu-id="c2ab2-113">If the exception is not caught, execution of the `finally` block depends on whether the operating system chooses to trigger an exception unwind operation.</span></span>

## <a name="example"></a><span data-ttu-id="c2ab2-114">Пример</span><span class="sxs-lookup"><span data-stu-id="c2ab2-114">Example</span></span>

<span data-ttu-id="c2ab2-115">В следующем примере недопустимый оператор преобразования вызывает исключение `System.InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="c2ab2-115">In the following example, an invalid conversion statement causes a `System.InvalidCastException` exception.</span></span> <span data-ttu-id="c2ab2-116">Исключение не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="c2ab2-116">The exception is unhandled.</span></span>

[!code-csharp[csrefKeywordsExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#4)]

<span data-ttu-id="c2ab2-117">В следующем примере исключение из метода `TryCast` перехватывается в методе выше в стеке вызовов.</span><span class="sxs-lookup"><span data-stu-id="c2ab2-117">In the following example, an exception from the `TryCast` method is caught in a method farther up the call stack.</span></span>

[!code-csharp[csrefKeywordsExceptions#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#6)]

<span data-ttu-id="c2ab2-118">Дополнительные сведения о `finally` см. в разделе [try-catch-finally](try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="c2ab2-118">For more information about `finally`, see [try-catch-finally](try-catch-finally.md).</span></span>

<span data-ttu-id="c2ab2-119">C# также содержит [оператор using](using-statement.md), который предоставляет аналогичную функциональность для объектов <xref:System.IDisposable> в удобном синтаксисе.</span><span class="sxs-lookup"><span data-stu-id="c2ab2-119">C# also contains the [using statement](using-statement.md), which provides similar functionality for <xref:System.IDisposable> objects in a convenient syntax.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c2ab2-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c2ab2-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c2ab2-121">См. также</span><span class="sxs-lookup"><span data-stu-id="c2ab2-121">See Also</span></span>

- [<span data-ttu-id="c2ab2-122">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="c2ab2-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c2ab2-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c2ab2-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c2ab2-124">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="c2ab2-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c2ab2-125">Операторы try, throw и catch (C++)</span><span class="sxs-lookup"><span data-stu-id="c2ab2-125">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="c2ab2-126">Операторы обработки исключений</span><span class="sxs-lookup"><span data-stu-id="c2ab2-126">Exception Handling Statements</span></span>](exception-handling-statements.md)
- [<span data-ttu-id="c2ab2-127">throw</span><span class="sxs-lookup"><span data-stu-id="c2ab2-127">throw</span></span>](throw.md)
- [<span data-ttu-id="c2ab2-128">try-catch</span><span class="sxs-lookup"><span data-stu-id="c2ab2-128">try-catch</span></span>](try-catch.md)
- [<span data-ttu-id="c2ab2-129">Практическое руководство. Явное создание исключений</span><span class="sxs-lookup"><span data-stu-id="c2ab2-129">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)