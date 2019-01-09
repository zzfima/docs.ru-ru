---
title: Справочник по C#. Оператор using
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: df116a200795fd20405381fd71e82d1d6fe662bc
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614393"
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="31bd4-102">Оператор using (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="31bd4-102">using statement (C# Reference)</span></span>

<span data-ttu-id="31bd4-103">Предоставляет удобный синтаксис, обеспечивающий правильное использование объектов <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="31bd4-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>

## <a name="example"></a><span data-ttu-id="31bd4-104">Пример</span><span class="sxs-lookup"><span data-stu-id="31bd4-104">Example</span></span>

<span data-ttu-id="31bd4-105">В следующем примере показано использование оператора `using`.</span><span class="sxs-lookup"><span data-stu-id="31bd4-105">The following example shows how to use the `using` statement.</span></span>

[!code-csharp[csrefKeywordsNamespace#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#4)]

## <a name="remarks"></a><span data-ttu-id="31bd4-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="31bd4-106">Remarks</span></span>

<span data-ttu-id="31bd4-107"><xref:System.IO.File> и <xref:System.Drawing.Font> представляют собой примеры управляемых типов, которые обращаются к неуправляемым ресурсам (в данном случае это обработчики файлов и контексты устройств).</span><span class="sxs-lookup"><span data-stu-id="31bd4-107"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="31bd4-108">Существуют и многие другие виды неуправляемых ресурсов и типов библиотек классов, которые их инкапсулируют.</span><span class="sxs-lookup"><span data-stu-id="31bd4-108">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="31bd4-109">Все эти типы реализуют интерфейс <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="31bd4-109">All such types must implement the <xref:System.IDisposable> interface.</span></span>

<span data-ttu-id="31bd4-110">Когда время существования объекта `IDisposable` ограничено одним методом, необходимо объявить его и создать его экземпляр в операторе `using`.</span><span class="sxs-lookup"><span data-stu-id="31bd4-110">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in the `using` statement.</span></span> <span data-ttu-id="31bd4-111">Оператор `using` правильно вызывает метод <xref:System.IDisposable.Dispose%2A> для объектов, а также (если он используется, как показано выше) становится причиной выхода объекта из области действия, как только вызывается метод <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="31bd4-111">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="31bd4-112">В блоке `using` объект доступен только для чтения, и изменить или переназначить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="31bd4-112">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>

<span data-ttu-id="31bd4-113">Использование оператора `using` обеспечивает вызов метода <xref:System.IDisposable.Dispose%2A>, даже если в блоке `using` возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="31bd4-113">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs within the `using` block.</span></span> <span data-ttu-id="31bd4-114">Тот же результат можно получить, поместив объект в блок `try`, а затем вызвав метод <xref:System.IDisposable.Dispose%2A> в блоке `finally`; фактически компилятор переводит оператор `using` именно так.</span><span class="sxs-lookup"><span data-stu-id="31bd4-114">You can achieve the same result by putting the object inside a `try` block and then calling <xref:System.IDisposable.Dispose%2A> in a `finally` block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="31bd4-115">Во время компиляции представленный выше код разворачивается в следующий (обратите внимание на дополнительные фигурные скобки, создающие ограниченную область действия для объекта):</span><span class="sxs-lookup"><span data-stu-id="31bd4-115">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>

[!code-csharp[csrefKeywordsNamespace#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#5)]

<span data-ttu-id="31bd4-116">Дополнительные сведения об операторе `try`-`finally` см. в разделе [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="31bd4-116">For more information about the `try`-`finally` statement, see the [try-finally](try-finally.md) topic.</span></span>

<span data-ttu-id="31bd4-117">В операторе `using` можно объявить сразу несколько экземпляров типа, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="31bd4-117">Multiple instances of a type can be declared in the `using` statement, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsNamespace#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#6)]

<span data-ttu-id="31bd4-118">Вы можете создать экземпляр объекта ресурсов, а затем передать переменную в оператор `using`, однако делать этого не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="31bd4-118">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="31bd4-119">В этом случае объект остается в области действия и после того, как блок `using` теряет контроль, хотя доступа к неуправляемым ресурсам у него, скорее всего, не будет.</span><span class="sxs-lookup"><span data-stu-id="31bd4-119">In this case, after control leaves the `using` block, the object remains in scope but probably has no access to its unmanaged resources.</span></span> <span data-ttu-id="31bd4-120">Иными словами, он уже не полностью инициализируется.</span><span class="sxs-lookup"><span data-stu-id="31bd4-120">In other words, it's not fully initialized anymore.</span></span> <span data-ttu-id="31bd4-121">При попытке использовать объект за пределами блока `using` может возникнуть исключение.</span><span class="sxs-lookup"><span data-stu-id="31bd4-121">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="31bd4-122">По этой причине лучше создать экземпляр объекта в операторе `using` и ограничить область действия блоком `using`.</span><span class="sxs-lookup"><span data-stu-id="31bd4-122">For this reason, it's generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>

[!code-csharp[csrefKeywordsNamespace#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#7)]

<span data-ttu-id="31bd4-123">Дополнительные сведения об утилизации объектов `IDisposable` см. в разделе [Использование объектов, реализующих IDisposable](../../../standard/garbage-collection/using-objects.md).</span><span class="sxs-lookup"><span data-stu-id="31bd4-123">For more information about disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="31bd4-124">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="31bd4-124">C# language specification</span></span>

<span data-ttu-id="31bd4-125">Дополнительные сведения см. в разделе [Оператор using](~/_csharplang/spec/statements.md#the-using-statement) в статье [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="31bd4-125">For more information, see [The using statement](~/_csharplang/spec/statements.md#the-using-statement) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="31bd4-126">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="31bd4-126">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="31bd4-127">См. также</span><span class="sxs-lookup"><span data-stu-id="31bd4-127">See also</span></span>

- [<span data-ttu-id="31bd4-128">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="31bd4-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="31bd4-129">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="31bd4-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="31bd4-130">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="31bd4-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="31bd4-131">Директива using</span><span class="sxs-lookup"><span data-stu-id="31bd4-131">using Directive</span></span>](using-directive.md)
- [<span data-ttu-id="31bd4-132">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="31bd4-132">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="31bd4-133">Использование объектов, реализующих IDisposable</span><span class="sxs-lookup"><span data-stu-id="31bd4-133">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)
- [<span data-ttu-id="31bd4-134">Интерфейс IDisposable</span><span class="sxs-lookup"><span data-stu-id="31bd4-134">IDisposable interface</span></span>](xref:System.IDisposable)