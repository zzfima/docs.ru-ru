---
title: Использование объектов, реализующих IDisposable
ms.date: 04/07/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- try/finally block
- garbage collection, encapsulating resources
ms.assetid: 81b2cdb5-c91a-4a31-9c83-eadc52da5cf0
ms.openlocfilehash: 979cd782e5ab094b6dea010fc7a0b27caa390e67
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141340"
---
# <a name="using-objects-that-implement-idisposable"></a><span data-ttu-id="2f093-102">Использование объектов, реализующих IDisposable</span><span class="sxs-lookup"><span data-stu-id="2f093-102">Using objects that implement IDisposable</span></span>

<span data-ttu-id="2f093-103">Сборщик мусора среды CLR освобождает память, используемую управляемыми объектами, но типы, которые используют неуправляемые ресурсы, реализуют интерфейс <xref:System.IDisposable>, который позволяет освободить память, выделенную таким неуправляемым ресурсам.</span><span class="sxs-lookup"><span data-stu-id="2f093-103">The common language runtime's garbage collector reclaims the memory used by managed objects, but types that use unmanaged resources implement the <xref:System.IDisposable> interface to allow the memory allocated to these unmanaged resources to be reclaimed.</span></span> <span data-ttu-id="2f093-104">По окончании использования объекта, который реализует интерфейс <xref:System.IDisposable>, необходимо вызвать реализацию объекта <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2f093-104">When you finish using an object that implements <xref:System.IDisposable>, you should call the object's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="2f093-105">Это можно сделать одним из двух способов.</span><span class="sxs-lookup"><span data-stu-id="2f093-105">You can do this in one of two ways:</span></span>  
  
- <span data-ttu-id="2f093-106">С помощью оператора `using` (C#) или `Using` (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="2f093-106">With the C# `using` statement or the Visual Basic `Using` statement.</span></span>  
  
- <span data-ttu-id="2f093-107">Путем реализации блока `try/finally`.</span><span class="sxs-lookup"><span data-stu-id="2f093-107">By implementing a `try/finally` block.</span></span>  

## <a name="the-using-statement"></a><span data-ttu-id="2f093-108">Оператор using</span><span class="sxs-lookup"><span data-stu-id="2f093-108">The using statement</span></span>

<span data-ttu-id="2f093-109">Операторы `using` (C#) и `Using` (Visual Basic) упрощают составление кода для создания и очистки объекта.</span><span class="sxs-lookup"><span data-stu-id="2f093-109">The `using` statement in C# and the `Using` statement in Visual Basic simplify the code that you must write to create and clean up an object.</span></span> <span data-ttu-id="2f093-110">Оператор `using` получает один или больше ресурсов, выполняет заданные операторы, после чего автоматически освобождает объект.</span><span class="sxs-lookup"><span data-stu-id="2f093-110">The `using` statement obtains one or more resources, executes the statements that you specify, and automatically disposes of the object.</span></span> <span data-ttu-id="2f093-111">Однако оператор `using` полезен только для объектов в области действия метода, в котором они созданы.</span><span class="sxs-lookup"><span data-stu-id="2f093-111">However, the `using` statement is useful only for objects that are used within the scope of the method in which they are constructed.</span></span>  
  
<span data-ttu-id="2f093-112">В следующем примере для создания и освобождения объекта `using` используется оператор <xref:System.IO.StreamReader?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2f093-112">The following example uses the `using` statement to create and release a <xref:System.IO.StreamReader?displayProperty=nameWithType> object.</span></span>  
  
[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using1.vb#1)]  
  
<span data-ttu-id="2f093-113">Обратите внимание, что хотя класс <xref:System.IO.StreamReader> реализует интерфейс <xref:System.IDisposable>, который указывает, что используется неуправляемый ресурс, пример явно не вызывает метод <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2f093-113">Note that although the <xref:System.IO.StreamReader> class implements the <xref:System.IDisposable> interface, which indicates that it uses an unmanaged resource, the example doesn't explicitly call the <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2f093-114">Когда компилятор C# или Visual Basic встречает оператор `using`, он создает промежуточный язык, эквивалентный следующему коду, который явно содержит блок `try/finally`.</span><span class="sxs-lookup"><span data-stu-id="2f093-114">When the C# or Visual Basic compiler encounters the `using` statement, it emits intermediate language (IL) that is equivalent to the following code that explicitly contains a `try/finally` block.</span></span>  
  
[!code-csharp[Conceptual.Disposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using3.cs#3)]
[!code-vb[Conceptual.Disposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using3.vb#3)]  
  
<span data-ttu-id="2f093-115">Оператор `using` в C# позволяет присоединять несколько ресурсов в одном операторе, что эквивалентно использованию вложенных инструкций `using`.</span><span class="sxs-lookup"><span data-stu-id="2f093-115">The C# `using` statement also allows you to acquire multiple resources in a single statement, which is internally equivalent to nested `using` statements.</span></span> <span data-ttu-id="2f093-116">В следующем примере создается два объекта <xref:System.IO.StreamReader> для чтения содержимого двух разных файлов.</span><span class="sxs-lookup"><span data-stu-id="2f093-116">The following example instantiates two <xref:System.IO.StreamReader> objects to read the contents of two different files.</span></span>  
  
[!code-csharp[Conceptual.Disposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using4.cs#4)]

## <a name="tryfinally-block"></a><span data-ttu-id="2f093-117">Блок try/finally</span><span class="sxs-lookup"><span data-stu-id="2f093-117">Try/finally block</span></span>

<span data-ttu-id="2f093-118">Вместо размещения блока `try/finally` в операторе `using` можно реализовать блок `try/finally` напрямую.</span><span class="sxs-lookup"><span data-stu-id="2f093-118">Instead of wrapping a `try/finally` block in a `using` statement, you may choose to implement the `try/finally` block directly.</span></span> <span data-ttu-id="2f093-119">Это может быть личным стилем программирования или же осуществляться по одной из следующих причин:</span><span class="sxs-lookup"><span data-stu-id="2f093-119">This may be your personal coding style, or you might want to do this for one of the following reasons:</span></span>  
  
- <span data-ttu-id="2f093-120">Чтобы включить блок `catch` для обработки исключений, вызванных в блоке `try`.</span><span class="sxs-lookup"><span data-stu-id="2f093-120">To include a `catch` block to handle any exceptions thrown in the `try` block.</span></span> <span data-ttu-id="2f093-121">В противном случае исключения, вызываемые оператором `using`, а также создаваемые в блоке `using`, если блок `try/catch` отсутствует, не обрабатываются.</span><span class="sxs-lookup"><span data-stu-id="2f093-121">Otherwise, any exceptions thrown by the `using` statement are unhandled, as are any exceptions thrown within the `using` block if a `try/catch` block isn't present.</span></span>  
  
- <span data-ttu-id="2f093-122">Чтобы создать экземпляр объекта, реализующего интерфейс <xref:System.IDisposable>, область действия которого не является локальной для блока, в котором он объявлен.</span><span class="sxs-lookup"><span data-stu-id="2f093-122">To instantiate an object that implements <xref:System.IDisposable> whose scope is not local to the block within which it is declared.</span></span>  
  
<span data-ttu-id="2f093-123">Следующий пример похож на предыдущий с тем отличием, что в нем используется блок `try/catch/finally`для создания, использования и удаления экземпляра объекта <xref:System.IO.StreamReader>, а также для обработки исключений, создаваемых конструктором <xref:System.IO.StreamReader> и его методом <xref:System.IO.StreamReader.ReadToEnd%2A>.</span><span class="sxs-lookup"><span data-stu-id="2f093-123">The following example is similar to the previous example, except that it uses a `try/catch/finally` block to instantiate, use, and dispose of a <xref:System.IO.StreamReader> object, and to handle any exceptions thrown by the <xref:System.IO.StreamReader> constructor and its <xref:System.IO.StreamReader.ReadToEnd%2A> method.</span></span> <span data-ttu-id="2f093-124">Обратите внимание, что перед вызовом метода `finally` код в блоке <xref:System.IDisposable> проверяет, имеет ли объект, реализующий интерфейс `null`, значение <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="2f093-124">Note that the code in the `finally` block checks that the object that implements <xref:System.IDisposable> isn't `null` before it calls the <xref:System.IDisposable.Dispose%2A> method.</span></span> <span data-ttu-id="2f093-125">Если этого сделать не удастся, это может привести к исключению <xref:System.NullReferenceException> во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2f093-125">Failure to do this can result in a <xref:System.NullReferenceException> exception at run time.</span></span>  
  
[!code-csharp[Conceptual.Disposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using5.cs#6)]
[!code-vb[Conceptual.Disposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using5.vb#6)]  
  
<span data-ttu-id="2f093-126">Вы можете применить этот базовый шаблон, если есть желание или необходимость реализовать блок `try/finally` на языке программирования, который не поддерживает оператор `using`, но допускает прямые вызовы метода <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="2f093-126">You can follow this basic pattern if you choose to implement or must implement a `try/finally` block, because your programming language doesn't support a `using` statement but does allow direct calls to the <xref:System.IDisposable.Dispose%2A> method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2f093-127">См. также</span><span class="sxs-lookup"><span data-stu-id="2f093-127">See also</span></span>

- [<span data-ttu-id="2f093-128">Очистка неуправляемых ресурсов</span><span class="sxs-lookup"><span data-stu-id="2f093-128">Cleaning Up Unmanaged Resources</span></span>](../../../docs/standard/garbage-collection/unmanaged.md)
- [<span data-ttu-id="2f093-129">Оператор using (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2f093-129">using Statement (C# Reference)</span></span>](../../csharp/language-reference/keywords/using-statement.md)
- [<span data-ttu-id="2f093-130">Оператор Using (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f093-130">Using Statement (Visual Basic)</span></span>](../../visual-basic/language-reference/statements/using-statement.md)
