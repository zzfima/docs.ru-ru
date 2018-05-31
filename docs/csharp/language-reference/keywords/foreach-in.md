---
title: foreach, in (Справочник по C#)
ms.date: 05/24/2018
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: b6b7dc0a4d3970ddfbbb6635ccebbbd5b75671e4
ms.sourcegitcommit: 54231aa56fca059e9297888a96fbca1d4cf3746c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2018
ms.locfileid: "34549388"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="abc04-102">foreach, in (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="abc04-102">foreach, in (C# Reference)</span></span>

<span data-ttu-id="abc04-103">Оператор `foreach` выполняет оператор или блок операторов для каждого элемента в экземпляре типа, который реализует интерфейс <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="abc04-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="abc04-104">Оператор `foreach` не ограничивается этими типами. Он может применяться к экземпляру любого типа, который удовлетворяет следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="abc04-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="abc04-105">включает открытый метод `GetEnumerator` без параметров со следующим типом возвращаемого значения: класс, структура или тип интерфейса;</span><span class="sxs-lookup"><span data-stu-id="abc04-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="abc04-106">тип возвращаемого значения метода `GetEnumerator` должен содержать открытое свойство `Current` и открытый метод `MoveNext` без параметров с типом возвращаемого значения <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="abc04-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="abc04-107">В любой момент в блоке операторов `foreach` вы можете прервать цикл с помощью ключевого слова [break](break.md) или перейти к следующей итерации с помощью ключевого слова [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="abc04-107">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) keyword, or step to the next iteration in the loop by using the [continue](continue.md) keyword.</span></span> <span data-ttu-id="abc04-108">Также можно выйти из цикла `foreach` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="abc04-108">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="examples"></a><span data-ttu-id="abc04-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="abc04-109">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="abc04-110">В следующем примере показано использование оператора `foreach` с экземпляром типа <xref:System.Collections.Generic.List%601>, который реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="abc04-110">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="abc04-111">В следующем примере показано использование оператора `foreach` с экземпляром типа <xref:System.Span%601?displayProperty=nameWithType>, который не реализует интерфейс:</span><span class="sxs-lookup"><span data-stu-id="abc04-111">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="abc04-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="abc04-112">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="abc04-113">См. также</span><span class="sxs-lookup"><span data-stu-id="abc04-113">See also</span></span>

[<span data-ttu-id="abc04-114">Оператор foreach (спецификация языка C#)</span><span class="sxs-lookup"><span data-stu-id="abc04-114">The foreach statement (C# language specification)</span></span>](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement)  
[<span data-ttu-id="abc04-115">Использование оператора foreach с массивами</span><span class="sxs-lookup"><span data-stu-id="abc04-115">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)  
[<span data-ttu-id="abc04-116">for</span><span class="sxs-lookup"><span data-stu-id="abc04-116">for</span></span>](for.md)  
[<span data-ttu-id="abc04-117">Операторы итерации</span><span class="sxs-lookup"><span data-stu-id="abc04-117">Iteration Statements</span></span>](iteration-statements.md)  
[<span data-ttu-id="abc04-118">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="abc04-118">C# Keywords</span></span>](index.md)  
[<span data-ttu-id="abc04-119">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="abc04-119">C# Reference</span></span>](../index.md)  
[<span data-ttu-id="abc04-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="abc04-120">C# Programming Guide</span></span>](../../programming-guide/index.md)  