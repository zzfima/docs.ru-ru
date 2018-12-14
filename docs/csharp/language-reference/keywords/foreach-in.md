---
title: Оператор foreach в C#
ms.date: 06/29/2018
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 417a8cefbc9bc7544ae1156992e6e6c549fb828f
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128626"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="d1bca-102">foreach, in (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d1bca-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="d1bca-103">Оператор `foreach` выполняет оператор или блок операторов для каждого элемента в экземпляре типа, который реализует интерфейс <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d1bca-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="d1bca-104">Оператор `foreach` не ограничивается этими типами. Он может применяться к экземпляру любого типа, который удовлетворяет следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="d1bca-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="d1bca-105">включает открытый метод `GetEnumerator` без параметров со следующим типом возвращаемого значения: класс, структура или тип интерфейса;</span><span class="sxs-lookup"><span data-stu-id="d1bca-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="d1bca-106">тип возвращаемого значения метода `GetEnumerator` должен содержать открытое свойство `Current` и открытый метод `MoveNext` без параметров с типом возвращаемого значения <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="d1bca-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="d1bca-107">Начиная с версии C# 7.3, если свойство перечислителя `Current` возвращает [ссылочное возвращаемое значение](ref.md#reference-return-values) (`ref T`, где `T` — это тип элемента коллекции), вы можете объявить переменную итерации с модификатором `ref` или `ref readonly`.</span><span class="sxs-lookup"><span data-stu-id="d1bca-107">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span>

<span data-ttu-id="d1bca-108">В любой момент в блоке операторов `foreach` вы можете прервать цикл с помощью оператора [break](break.md) или перейти к следующей итерации в цикле с помощью оператора [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="d1bca-108">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="d1bca-109">Также можно выйти из цикла `foreach` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="d1bca-109">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="examples"></a><span data-ttu-id="d1bca-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="d1bca-110">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="d1bca-111">В следующем примере показано использование оператора `foreach` с экземпляром типа <xref:System.Collections.Generic.List%601>, который реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="d1bca-111">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="d1bca-112">В следующем примере показано использование оператора `foreach` с экземпляром типа <xref:System.Span%601?displayProperty=nameWithType>, который не реализует интерфейс:</span><span class="sxs-lookup"><span data-stu-id="d1bca-112">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

<span data-ttu-id="d1bca-113">В следующем примере с помощью переменной итерации `ref` устанавливается значение каждого элемента в массиве stackalloc.</span><span class="sxs-lookup"><span data-stu-id="d1bca-113">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="d1bca-114">В версии `ref readonly` выполняется перебор коллекции для печати всех значений.</span><span class="sxs-lookup"><span data-stu-id="d1bca-114">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="d1bca-115">В объявлении `readonly` используется неявное объявление локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="d1bca-115">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="d1bca-116">Неявные объявления переменных могут использоваться с объявлениями `ref` или `ref readonly`, так же как и явно типизированные объявления переменных.</span><span class="sxs-lookup"><span data-stu-id="d1bca-116">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

[!code-csharp-interactive[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

## <a name="c-language-specification"></a><span data-ttu-id="d1bca-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="d1bca-117">C# language specification</span></span>

<span data-ttu-id="d1bca-118">Дополнительные сведения см. в разделе [Оператор foreach](~/_csharplang/spec/statements.md#the-foreach-statement) в документации [Предварительная спецификация C# 6.0](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="d1bca-118">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d1bca-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d1bca-119">See also</span></span>

- [<span data-ttu-id="d1bca-120">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d1bca-120">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d1bca-121">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d1bca-121">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d1bca-122">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="d1bca-122">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d1bca-123">Операторы итерации</span><span class="sxs-lookup"><span data-stu-id="d1bca-123">Iteration Statements</span></span>](iteration-statements.md)
- [<span data-ttu-id="d1bca-124">Использование оператора foreach с массивами</span><span class="sxs-lookup"><span data-stu-id="d1bca-124">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="d1bca-125">Оператор for</span><span class="sxs-lookup"><span data-stu-id="d1bca-125">for statement</span></span>](for.md)
