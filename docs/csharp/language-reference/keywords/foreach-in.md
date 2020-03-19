---
title: Оператор foreach в C#
ms.date: 05/17/2019
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: dbe4f4e95c2b99f1be47885e39d51db81ba3a97d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173709"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="ade6c-102">foreach, in (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ade6c-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="ade6c-103">Оператор `foreach` выполняет оператор или блок операторов для каждого элемента в экземпляре типа, который реализует интерфейс <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ade6c-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="ade6c-104">Оператор `foreach` не ограничивается этими типами. Он может применяться к экземпляру любого типа, который удовлетворяет следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="ade6c-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="ade6c-105">включает открытый метод `GetEnumerator` без параметров со следующим типом возвращаемого значения: класс, структура или тип интерфейса;</span><span class="sxs-lookup"><span data-stu-id="ade6c-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="ade6c-106">тип возвращаемого значения метода `GetEnumerator` должен содержать открытое свойство `Current` и открытый метод `MoveNext` без параметров с типом возвращаемого значения <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="ade6c-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="ade6c-107">Начиная с версии C# 7.3, если свойство перечислителя `Current` возвращает [ссылочное возвращаемое значение](ref.md#reference-return-values) (`ref T`, где `T` — это тип элемента коллекции), вы можете объявить переменную итерации с модификатором `ref` или `ref readonly`.</span><span class="sxs-lookup"><span data-stu-id="ade6c-107">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span>

<span data-ttu-id="ade6c-108">Начиная с версии C# 8.0, можно применять оператор `await` к инструкции `foreach`, если тип коллекции реализует интерфейс <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="ade6c-108">Beginning with C# 8.0, the `await` operator may be applied to the `foreach` statement when the collection type implements the <xref:System.Collections.Generic.IAsyncEnumerable%601> interface.</span></span> <span data-ttu-id="ade6c-109">Каждую итерацию цикла можно приостановить, пока будет осуществляться асинхронное извлечение следующего элемента.</span><span class="sxs-lookup"><span data-stu-id="ade6c-109">Each iteration of the loop may be suspended while the next element is retrieved asynchronously.</span></span> <span data-ttu-id="ade6c-110">Элементы потока по умолчанию обрабатываются в захваченном контексте.</span><span class="sxs-lookup"><span data-stu-id="ade6c-110">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="ade6c-111">Чтобы отключить захват контекста, используйте метод расширения <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ade6c-111">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="ade6c-112">Дополнительные сведения о контекстах синхронизации и захвате текущего контекста см. в [статье](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md), посвященной использованию асинхронной модели на основе задач.</span><span class="sxs-lookup"><span data-stu-id="ade6c-112">For more information about synchronization contexts and capturing the current context, see the article on [consuming the Task-based asynchronous pattern](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span>

<span data-ttu-id="ade6c-113">В любой момент в блоке операторов `foreach` вы можете прервать цикл с помощью оператора [break](break.md) или перейти к следующей итерации в цикле с помощью оператора [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="ade6c-113">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="ade6c-114">Также можно выйти из цикла `foreach` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="ade6c-114">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="ade6c-115">Если оператор `foreach` применяется к `null`, возникает исключение <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="ade6c-115">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="ade6c-116">Если исходная коллекция инструкции `foreach` пустая, тело цикла `foreach` не выполняется и пропускается.</span><span class="sxs-lookup"><span data-stu-id="ade6c-116">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop isn't executed and skipped.</span></span>

## <a name="examples"></a><span data-ttu-id="ade6c-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="ade6c-117">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="ade6c-118">В следующем примере показано использование оператора `foreach` с экземпляром типа <xref:System.Collections.Generic.List%601>, который реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="ade6c-118">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="ade6c-119">В следующем примере показано использование оператора `foreach` с экземпляром типа <xref:System.Span%601?displayProperty=nameWithType>, который не реализует интерфейс:</span><span class="sxs-lookup"><span data-stu-id="ade6c-119">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

<span data-ttu-id="ade6c-120">В следующем примере с помощью переменной итерации `ref` устанавливается значение каждого элемента в массиве stackalloc.</span><span class="sxs-lookup"><span data-stu-id="ade6c-120">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="ade6c-121">В версии `ref readonly` выполняется перебор коллекции для печати всех значений.</span><span class="sxs-lookup"><span data-stu-id="ade6c-121">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="ade6c-122">В объявлении `readonly` используется неявное объявление локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="ade6c-122">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="ade6c-123">Неявные объявления переменных могут использоваться с объявлениями `ref` или `ref readonly`, так же как и явно типизированные объявления переменных.</span><span class="sxs-lookup"><span data-stu-id="ade6c-123">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

[!code-csharp[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

<span data-ttu-id="ade6c-124">В следующем примере используется `await foreach` для выполнения итерации коллекции с асинхронным созданием каждого элемента:</span><span class="sxs-lookup"><span data-stu-id="ade6c-124">The following example uses `await foreach` to iterate a collection that generates each element asynchronously:</span></span>

[!code-csharp[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#AwaitForeach)]

## <a name="c-language-specification"></a><span data-ttu-id="ade6c-125">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ade6c-125">C# language specification</span></span>

<span data-ttu-id="ade6c-126">Дополнительные сведения см. в разделе [Оператор foreach](~/_csharplang/spec/statements.md#the-foreach-statement) в документации [Предварительная спецификация C# 6.0](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="ade6c-126">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="ade6c-127">См. также</span><span class="sxs-lookup"><span data-stu-id="ade6c-127">See also</span></span>

- [<span data-ttu-id="ade6c-128">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ade6c-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ade6c-129">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ade6c-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ade6c-130">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="ade6c-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ade6c-131">Использование оператора foreach с массивами</span><span class="sxs-lookup"><span data-stu-id="ade6c-131">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="ade6c-132">Оператор for</span><span class="sxs-lookup"><span data-stu-id="ade6c-132">for statement</span></span>](for.md)
