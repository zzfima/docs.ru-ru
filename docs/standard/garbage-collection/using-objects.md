---
title: "Использование объектов, реализующих IDisposable"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- try/finally block
- garbage collection, encapsulating resources
ms.assetid: 81b2cdb5-c91a-4a31-9c83-eadc52da5cf0
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fd78c2f99ca5c8ffe3c753e158ceba3e0c458c5b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="using-objects-that-implement-idisposable"></a><span data-ttu-id="2fb3f-102">Использование объектов, реализующих IDisposable</span><span class="sxs-lookup"><span data-stu-id="2fb3f-102">Using objects that implement IDisposable</span></span>

<span data-ttu-id="2fb3f-103">Сборщик мусора среды CLR освобождает память, используемую с управляемыми объектами, но реализуют типы, которые используют неуправляемые ресурсы <xref:System.IDisposable> интерфейс, позволяющий память, выделенную для этих неуправляемые ресурсы, которые нужно освободить.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-103">The common language runtime's garbage collector reclaims the memory used by managed objects, but types that use unmanaged resources implement the <xref:System.IDisposable> interface to allow the memory allocated to these unmanaged resources to be reclaimed.</span></span> <span data-ttu-id="2fb3f-104">По окончании использования объекта, который реализует интерфейс <xref:System.IDisposable>, необходимо вызвать реализацию объекта <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-104">When you finish using an object that implements <xref:System.IDisposable>, you should call the object's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="2fb3f-105">Это можно сделать одним из двух способов.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-105">You can do this in one of two ways:</span></span>  
  
* <span data-ttu-id="2fb3f-106">С помощью оператора `using` (C#) или `Using` (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="2fb3f-106">With the C# `using` statement or the Visual Basic `Using` statement.</span></span>  
  
* <span data-ttu-id="2fb3f-107">Путем реализации блока `try/finally`.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-107">By implementing a `try/finally` block.</span></span>  

## <a name="the-using-statement"></a><span data-ttu-id="2fb3f-108">Оператор using</span><span class="sxs-lookup"><span data-stu-id="2fb3f-108">The using statement</span></span>

<span data-ttu-id="2fb3f-109">Операторы `using` (C#) и `Using` (Visual Basic) упрощают составление кода для создания и очистки объекта.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-109">The `using` statement in C# and the `Using` statement in Visual Basic simplify the code that you must write to create and clean up an object.</span></span> <span data-ttu-id="2fb3f-110">Оператор `using` получает один или больше ресурсов, выполняет заданные операторы, после чего автоматически освобождает объект.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-110">The `using` statement obtains one or more resources, executes the statements that you specify, and automatically disposes of the object.</span></span> <span data-ttu-id="2fb3f-111">Однако оператор `using` полезен только для объектов в области действия метода, в котором они созданы.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-111">However, the `using` statement is useful only for objects that are used within the scope of the method in which they are constructed.</span></span>  
  
<span data-ttu-id="2fb3f-112">В следующем примере для создания и освобождения объекта `using` используется оператор <xref:System.IO.StreamReader?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-112">The following example uses the `using` statement to create and release a <xref:System.IO.StreamReader?displayProperty=nameWithType> object.</span></span>  
  
[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using1.vb#1)]  
  
<span data-ttu-id="2fb3f-113">Обратите внимание, что хотя класс <xref:System.IO.StreamReader> реализует интерфейс <xref:System.IDisposable>, который указывает, что используется неуправляемый ресурс, пример явно не вызывает метод <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-113">Note that although the <xref:System.IO.StreamReader> class implements the <xref:System.IDisposable> interface, which indicates that it uses an unmanaged resource, the example doesn't explicitly call the <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2fb3f-114">Когда компилятор C# или Visual Basic встречает оператор `using`, он создает промежуточный язык, эквивалентный следующему коду, который явно содержит блок `try/finally`.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-114">When the C# or Visual Basic compiler encounters the `using` statement, it emits intermediate language (IL) that is equivalent to the following code that explicitly contains a `try/finally` block.</span></span>  
  
[!code-csharp[Conceptual.Disposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using3.cs#3)]
[!code-vb[Conceptual.Disposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using3.vb#3)]  
  
<span data-ttu-id="2fb3f-115">C# `using` инструкция также позволяет присоединять несколько ресурсов в одной инструкции, что эквивалентно внутри вложенной `using` инструкции.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-115">The C# `using` statement also allows you to acquire multiple resources in a single statement, which is internally equivalent to nested `using` statements.</span></span> <span data-ttu-id="2fb3f-116">В следующем примере создается два объекта <xref:System.IO.StreamReader> для чтения содержимого двух разных файлов.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-116">The following example instantiates two <xref:System.IO.StreamReader> objects to read the contents of two different files.</span></span>  
  
[!code-csharp[Conceptual.Disposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using4.cs#4)]

## <a name="tryfinally-block"></a><span data-ttu-id="2fb3f-117">Блок try/finally</span><span class="sxs-lookup"><span data-stu-id="2fb3f-117">Try/finally block</span></span>

<span data-ttu-id="2fb3f-118">Вместо размещения блока `try/finally` в операторе `using` можно реализовать блок `try/finally` напрямую.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-118">Instead of wrapping a `try/finally` block in a `using` statement, you may choose to implement the `try/finally` block directly.</span></span> <span data-ttu-id="2fb3f-119">Это может быть личным стилем программирования или же осуществляться по одной из следующих причин:</span><span class="sxs-lookup"><span data-stu-id="2fb3f-119">This may be your personal coding style, or you might want to do this for one of the following reasons:</span></span>  
  
* <span data-ttu-id="2fb3f-120">Чтобы включить блок `catch` для обработки исключений, вызванных в блоке `try`.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-120">To include a `catch` block to handle any exceptions thrown in the `try` block.</span></span> <span data-ttu-id="2fb3f-121">В противном случае исключения, вызываемые оператором `using`, а также создаваемые в блоке `using`, если блок `try/catch` отсутствует, не обрабатываются.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-121">Otherwise, any exceptions thrown by the `using` statement are unhandled, as are any exceptions thrown within the `using` block if a `try/catch` block isn't present.</span></span>  
  
* <span data-ttu-id="2fb3f-122">Чтобы создать экземпляр объекта, реализующего интерфейс <xref:System.IDisposable>, область действия которого не является локальной для блока, в котором он объявлен.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-122">To instantiate an object that implements <xref:System.IDisposable> whose scope is not local to the block within which it is declared.</span></span>  
  
<span data-ttu-id="2fb3f-123">Следующий пример аналогичен предыдущему примеру, за исключением того, что он использует `try/catch/finally` блок для создания экземпляра, использования и удаления <xref:System.IO.StreamReader> объекта и для обработки исключения, вызываемые <xref:System.IO.StreamReader> конструктор и его <xref:System.IO.StreamReader.ReadToEnd%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-123">The following example is similar to the previous example, except that it uses a `try/catch/finally` block to instantiate, use, and dispose of a <xref:System.IO.StreamReader> object, and to handle any exceptions thrown by the <xref:System.IO.StreamReader> constructor and its <xref:System.IO.StreamReader.ReadToEnd%2A> method.</span></span> <span data-ttu-id="2fb3f-124">Обратите внимание, что перед вызовом метода `finally` код в блоке <xref:System.IDisposable> проверяет, имеет ли объект, реализующий интерфейс `null`, значение <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-124">Note that the code in the `finally` block checks that the object that implements <xref:System.IDisposable> isn't `null` before it calls the <xref:System.IDisposable.Dispose%2A> method.</span></span> <span data-ttu-id="2fb3f-125">Если этого сделать не удастся, это может привести к исключению <xref:System.NullReferenceException> во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-125">Failure to do this can result in a <xref:System.NullReferenceException> exception at run time.</span></span>  
  
[!code-csharp[Conceptual.Disposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using5.cs#6)]
[!code-vb[Conceptual.Disposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using5.vb#6)]  
  
<span data-ttu-id="2fb3f-126">Можно следовать этому простому шаблону, если выбрать для реализации или если необходимо реализовать `try/finally` блокируются, поскольку язык программирования не поддерживает `using` инструкции, но разрешает прямые вызовы <xref:System.IDisposable.Dispose%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="2fb3f-126">You can follow this basic pattern if you choose to implement or must implement a `try/finally` block, because your programming language doesn't support a `using` statement but does allow direct calls to the <xref:System.IDisposable.Dispose%2A> method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2fb3f-127">См. также</span><span class="sxs-lookup"><span data-stu-id="2fb3f-127">See also</span></span>

<span data-ttu-id="2fb3f-128">[Очистка неуправляемых ресурсов](../../../docs/standard/garbage-collection/unmanaged.md) </span><span class="sxs-lookup"><span data-stu-id="2fb3f-128">[Cleaning Up Unmanaged Resources](../../../docs/standard/garbage-collection/unmanaged.md) </span></span>  
<span data-ttu-id="2fb3f-129">[Оператор using (Справочник по C#)](~/docs/csharp/language-reference/keywords/using-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2fb3f-129">[using Statement (C# Reference)](~/docs/csharp/language-reference/keywords/using-statement.md) </span></span>  
[<span data-ttu-id="2fb3f-130">С помощью оператора (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2fb3f-130">Using Statement (Visual Basic)</span></span>](~/docs/visual-basic/language-reference/statements/using-statement.md)
