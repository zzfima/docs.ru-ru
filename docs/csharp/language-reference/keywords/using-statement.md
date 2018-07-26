---
title: Оператор using (Справочник по C#)
ms.date: 07/20/2015
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: 7bf9138721ecee63c65c2e39922aee96b1dfaa41
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37960957"
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="5d116-102">Оператор using (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5d116-102">using Statement (C# Reference)</span></span>
<span data-ttu-id="5d116-103">Предоставляет удобный синтаксис, обеспечивающий правильное использование объектов <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="5d116-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d116-104">Пример</span><span class="sxs-lookup"><span data-stu-id="5d116-104">Example</span></span>  
 <span data-ttu-id="5d116-105">В следующем примере показано использование оператора `using`.</span><span class="sxs-lookup"><span data-stu-id="5d116-105">The following example shows how to use the `using` statement.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="5d116-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="5d116-106">Remarks</span></span>  
 <span data-ttu-id="5d116-107"><xref:System.IO.File> и <xref:System.Drawing.Font> представляют собой примеры управляемых типов, которые обращаются к неуправляемым ресурсам (в данном случае это обработчики файлов и контексты устройств).</span><span class="sxs-lookup"><span data-stu-id="5d116-107"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="5d116-108">Существуют и многие другие виды неуправляемых ресурсов и типов библиотек классов, которые их инкапсулируют.</span><span class="sxs-lookup"><span data-stu-id="5d116-108">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="5d116-109">Все эти типы реализуют интерфейс <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="5d116-109">All such types must implement the <xref:System.IDisposable> interface.</span></span>  
  
<span data-ttu-id="5d116-110">Когда время существования объекта `IDisposable` ограничено одним методом, необходимо объявить его и создать его экземпляр в операторе `using`.</span><span class="sxs-lookup"><span data-stu-id="5d116-110">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in the `using` statement.</span></span> <span data-ttu-id="5d116-111">Оператор `using` правильно вызывает метод <xref:System.IDisposable.Dispose%2A> для объектов, а также (если он используется, как показано выше) становится причиной выхода объекта из области действия, как только вызывается метод <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="5d116-111">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="5d116-112">В блоке `using` объект доступен только для чтения, и изменить или переназначить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="5d116-112">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>  
  
 <span data-ttu-id="5d116-113">Использование оператора `using` обеспечивает вызов метода <xref:System.IDisposable.Dispose%2A>, даже если в блоке `using` возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="5d116-113">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs within the `using` block.</span></span> <span data-ttu-id="5d116-114">Тот же результат можно получить, поместив объект в блок `try`, а затем вызвав метод <xref:System.IDisposable.Dispose%2A> в блоке `finally`; фактически компилятор переводит оператор `using` именно так.</span><span class="sxs-lookup"><span data-stu-id="5d116-114">You can achieve the same result by putting the object inside a `try` block and then calling <xref:System.IDisposable.Dispose%2A> in a `finally` block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="5d116-115">Во время компиляции представленный выше код разворачивается в следующий (обратите внимание на дополнительные фигурные скобки, создающие ограниченную область действия для объекта):</span><span class="sxs-lookup"><span data-stu-id="5d116-115">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
 
 <span data-ttu-id="5d116-116">Дополнительные сведения об операторе `try`-`finally` см. в разделе [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="5d116-116">For more information about the `try`-`finally` statement, see the [try-finally](try-finally.md) topic.</span></span>
  
 <span data-ttu-id="5d116-117">В операторе `using` можно объявить сразу несколько экземпляров типа, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="5d116-117">Multiple instances of a type can be declared in the `using` statement, as shown in the following example:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 <span data-ttu-id="5d116-118">Вы можете создать экземпляр объекта ресурсов, а затем передать переменную в оператор `using`, однако делать этого не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="5d116-118">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="5d116-119">В этом случае объект остается в области действия и после того, как блок `using` теряет контроль, хотя доступа к неуправляемым ресурсам у него, скорее всего, не будет.</span><span class="sxs-lookup"><span data-stu-id="5d116-119">In this case, after control leaves the `using` block, the object remains in scope but probably has no access to its unmanaged resources.</span></span> <span data-ttu-id="5d116-120">Иными словами, он уже не полностью инициализируется.</span><span class="sxs-lookup"><span data-stu-id="5d116-120">In other words, it's not fully initialized anymore.</span></span> <span data-ttu-id="5d116-121">При попытке использовать объект за пределами блока `using` может возникнуть исключение.</span><span class="sxs-lookup"><span data-stu-id="5d116-121">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="5d116-122">По этой причине лучше создать экземпляр объекта в операторе `using` и ограничить область действия блоком `using`.</span><span class="sxs-lookup"><span data-stu-id="5d116-122">For this reason, it's generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
<span data-ttu-id="5d116-123">Дополнительные сведения об утилизации объектов `IDisposable` см. в разделе [Использование объектов, реализующих IDisposable](../../../standard/garbage-collection/using-objects.md).</span><span class="sxs-lookup"><span data-stu-id="5d116-123">For more information about disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5d116-124">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5d116-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5d116-125">См. также</span><span class="sxs-lookup"><span data-stu-id="5d116-125">See Also</span></span>  
 [<span data-ttu-id="5d116-126">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5d116-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5d116-127">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5d116-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5d116-128">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="5d116-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="5d116-129">Директива using</span><span class="sxs-lookup"><span data-stu-id="5d116-129">using Directive</span></span>](../../../csharp/language-reference/keywords/using-directive.md)  
 [<span data-ttu-id="5d116-130">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="5d116-130">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)  
 [<span data-ttu-id="5d116-131">Использование объектов, реализующих IDisposable</span><span class="sxs-lookup"><span data-stu-id="5d116-131">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)  
 [<span data-ttu-id="5d116-132">Интерфейс IDisposable</span><span class="sxs-lookup"><span data-stu-id="5d116-132">IDisposable interface</span></span>](xref:System.IDisposable)
