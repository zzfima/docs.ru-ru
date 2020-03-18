---
title: Справочник по C#. if-else
ms.date: 07/20/2015
f1_keywords:
- if_CSharpKeyword
- else
- else_CSharpKeyword
- if
helpviewer_keywords:
- else keyword [C#]
- if keyword [C#]
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
ms.openlocfilehash: 98c1a8dceec3e5a47627841988e2d722c56fc36c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715263"
---
# <a name="if-else-c-reference"></a><span data-ttu-id="6c972-102">if-else (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6c972-102">if-else (C# Reference)</span></span>

<span data-ttu-id="6c972-103">Оператор `if` определяет, какой оператор будет выполняться при выполнения условия, заданного логическим выражением.</span><span class="sxs-lookup"><span data-stu-id="6c972-103">An `if` statement identifies which statement to run based on the value of a Boolean expression.</span></span> <span data-ttu-id="6c972-104">В приведенном ниже примере переменной `bool` типа `condition` присваивается значение `true` , а затем она проверяется оператором `if` .</span><span class="sxs-lookup"><span data-stu-id="6c972-104">In the following example, the `bool` variable `condition` is set to `true` and then checked in the `if` statement.</span></span> <span data-ttu-id="6c972-105">В результате получается `The variable is set to true.`.</span><span class="sxs-lookup"><span data-stu-id="6c972-105">The output is `The variable is set to true.`.</span></span>

[!code-csharp[csrefKeywordsSelection#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#1)]

<span data-ttu-id="6c972-106">Примеры в этом разделе можно выполнить, разместив их в методе `Main` консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="6c972-106">You can run the examples in this topic by placing them in the `Main` method of a console app.</span></span>

<span data-ttu-id="6c972-107">Оператор `if` в С# может иметь две формы, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="6c972-107">An `if` statement in C# can take two forms, as the following example shows.</span></span>

```csharp
// if-else statement
if (condition)
{
    then-statement;
}
else
{
    else-statement;
}
// Next statement in the program.

// if statement without an else
if (condition)
{
    then-statement;
}
// Next statement in the program.
```

<span data-ttu-id="6c972-108">В операторе `if-else` , если `condition` имеет значение true, выполняется `then-statement` .</span><span class="sxs-lookup"><span data-stu-id="6c972-108">In an `if-else` statement, if `condition` evaluates to true, the `then-statement` runs.</span></span> <span data-ttu-id="6c972-109">Если `condition` имеет значение false, выполняется `else-statement` .</span><span class="sxs-lookup"><span data-stu-id="6c972-109">If `condition` is false, the `else-statement` runs.</span></span> <span data-ttu-id="6c972-110">Так как `condition` не может одновременно иметь значения true и false, `then-statement` и `else-statement` оператора `if-else` не могут выполняться оба.</span><span class="sxs-lookup"><span data-stu-id="6c972-110">Because `condition` can’t be simultaneously true and false, the `then-statement` and the `else-statement` of an `if-else` statement can never both run.</span></span> <span data-ttu-id="6c972-111">После выполнения `then-statement` или `else-statement` управление передается следующему оператору после оператора `if` .</span><span class="sxs-lookup"><span data-stu-id="6c972-111">After the `then-statement` or the `else-statement` runs, control is transferred to the next statement after the `if` statement.</span></span>

<span data-ttu-id="6c972-112">В операторе `if` , не включающем оператор `else` , если `condition` имеет значение true, выполняется `then-statement` .</span><span class="sxs-lookup"><span data-stu-id="6c972-112">In an `if` statement that doesn’t include an `else` statement, if `condition` is true, the `then-statement` runs.</span></span> <span data-ttu-id="6c972-113">Если `condition` имеет значение false, то управление передается следующему оператору после оператора `if` .</span><span class="sxs-lookup"><span data-stu-id="6c972-113">If `condition` is false, control is transferred to the next statement after the `if` statement.</span></span>

<span data-ttu-id="6c972-114">`then-statement` и `else-statement` могут состоять из одного или нескольких операторов, заключенных в фигурные скобки (`{}`).</span><span class="sxs-lookup"><span data-stu-id="6c972-114">Both the `then-statement` and the `else-statement` can consist of a single statement or multiple statements that are enclosed in braces (`{}`).</span></span> <span data-ttu-id="6c972-115">Для одного оператора скобки необязательны, но рекомендуются.</span><span class="sxs-lookup"><span data-stu-id="6c972-115">For a single statement, the braces are optional but recommended.</span></span>

<span data-ttu-id="6c972-116">Оператор или операторы в `then-statement` и `else-statement` могут быть любого типа, включая другой оператор `if` , вложенный в исходный оператор `if` .</span><span class="sxs-lookup"><span data-stu-id="6c972-116">The statement or statements in the `then-statement` and the `else-statement` can be of any kind, including another `if` statement nested inside the original `if` statement.</span></span> <span data-ttu-id="6c972-117">Во вложенных операторах `if` каждое предложение `else` относится к последнему оператору `if` , у которого нет соответствующего объекта `else`.</span><span class="sxs-lookup"><span data-stu-id="6c972-117">In nested `if` statements, each `else` clause belongs to the last `if` that doesn’t have a corresponding `else`.</span></span> <span data-ttu-id="6c972-118">В приведенном ниже примере `Result1` получается, если оба выражения `m > 10` и `n > 20` имеют значение true.</span><span class="sxs-lookup"><span data-stu-id="6c972-118">In the following example, `Result1` appears if both `m > 10` and `n > 20` evaluate to true.</span></span> <span data-ttu-id="6c972-119">Если `m > 10` имеет значение true, но `n > 20` — значение false, то получается `Result2` .</span><span class="sxs-lookup"><span data-stu-id="6c972-119">If `m > 10` is true but `n > 20` is false, `Result2` appears.</span></span>

[!code-csharp[csrefKeywordsSelection#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#2)]

<span data-ttu-id="6c972-120">Если вместо этого нужно, чтобы `Result2` получался, когда значение `(m > 10)` равно false, можно указать такую связь с помощью фигурных скобок для задания начала и конца вложенного оператора `if` , как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="6c972-120">If, instead, you want `Result2` to appear when `(m > 10)` is false, you can specify that association by using braces to establish the start and end of the nested `if` statement, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsSelection#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#3)]

<span data-ttu-id="6c972-121">`Result2` получается, если условие `(m > 10)` имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="6c972-121">`Result2` appears if the condition `(m > 10)` evaluates to false.</span></span>

## <a name="example"></a><span data-ttu-id="6c972-122">Пример</span><span class="sxs-lookup"><span data-stu-id="6c972-122">Example</span></span>

<span data-ttu-id="6c972-123">В приведенном ниже примере вы вводите символ с помощью клавиатуры, а программа использует вложенный оператор `if` для определения того, является ли введенный символ буквой.</span><span class="sxs-lookup"><span data-stu-id="6c972-123">In the following example, you enter a character from the keyboard, and the program uses a nested `if` statement to determine whether the input character is an alphabetic character.</span></span> <span data-ttu-id="6c972-124">Если введенный символ является буквой, программа определяет его регистр.</span><span class="sxs-lookup"><span data-stu-id="6c972-124">If the input character is an alphabetic character, the program checks whether the input character is lowercase or uppercase.</span></span> <span data-ttu-id="6c972-125">Для каждого случая предусмотрено отдельное сообщение.</span><span class="sxs-lookup"><span data-stu-id="6c972-125">A message appears for each case.</span></span>

[!code-csharp[csrefKeywordsSelection#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#4)]

## <a name="example"></a><span data-ttu-id="6c972-126">Пример</span><span class="sxs-lookup"><span data-stu-id="6c972-126">Example</span></span>

<span data-ttu-id="6c972-127">Также можно поместить оператор `if` в блок else, как показано в части кода, приведенной ниже.</span><span class="sxs-lookup"><span data-stu-id="6c972-127">You also can nest an `if` statement inside an else block, as the following partial code shows.</span></span> <span data-ttu-id="6c972-128">В примере операторы `if` помещаются в два блока else и один блок then.</span><span class="sxs-lookup"><span data-stu-id="6c972-128">The example nests `if` statements inside two else blocks and one then block.</span></span> <span data-ttu-id="6c972-129">Комментарии определяют какие условия выполняются в каждом из блоков.</span><span class="sxs-lookup"><span data-stu-id="6c972-129">The comments specify which conditions are true or false in each block.</span></span>

[!code-csharp[csrefKeywordsSelection#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#5)]

## <a name="example"></a><span data-ttu-id="6c972-130">Пример</span><span class="sxs-lookup"><span data-stu-id="6c972-130">Example</span></span>

<span data-ttu-id="6c972-131">В приведенном ниже примере определяется, является ли введенный символ строчной буквой, прописной буквой или цифрой.</span><span class="sxs-lookup"><span data-stu-id="6c972-131">The following example determines whether an input character is a lowercase letter, an uppercase letter, or a number.</span></span> <span data-ttu-id="6c972-132">Если все три условия имеют значение false, то символ не является алфавитно-цифровым.</span><span class="sxs-lookup"><span data-stu-id="6c972-132">If all three conditions are false, the character isn’t an alphanumeric character.</span></span> <span data-ttu-id="6c972-133">Для каждого случая выводится сообщение.</span><span class="sxs-lookup"><span data-stu-id="6c972-133">The example displays a message for each case.</span></span>

[!code-csharp[csrefKeywordsSelection#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsSelection/CS/csrefKeywordsSelection.cs#6)]

<span data-ttu-id="6c972-134">Точно так же как оператор в блоке else или блоке then может быть любым допустимым оператором, в качестве условия можно использовать любое допустимое логическое выражение.</span><span class="sxs-lookup"><span data-stu-id="6c972-134">Just as a statement in the else block or the then block can be any valid statement, you can use any valid Boolean expression for the condition.</span></span> <span data-ttu-id="6c972-135">Вы можете использовать [логические операторы](../operators/boolean-logical-operators.md), такие как `!`, `&&`, `||`, `&`, `|`и `^`, для формирования составных условий.</span><span class="sxs-lookup"><span data-stu-id="6c972-135">You can use [logical operators](../operators/boolean-logical-operators.md) such as `!`, `&&`, `||`, `&`, `|`, and `^` to make compound conditions.</span></span> <span data-ttu-id="6c972-136">В коде ниже приведены примеры.</span><span class="sxs-lookup"><span data-stu-id="6c972-136">The following code shows examples.</span></span>

```csharp
// NOT
bool result = true;
if (!result)
{
    Console.WriteLine("The condition is true (result is false).");
}
else
{
    Console.WriteLine("The condition is false (result is true).");
}

// Short-circuit AND
int m = 9;
int n = 7;
int p = 5;
if (m >= n && m >= p)
{
    Console.WriteLine("Nothing is larger than m.");
}

// AND and NOT
if (m >= n && !(p > m))
{
    Console.WriteLine("Nothing is larger than m.");
}

// Short-circuit OR
if (m > n || m > p)
{
    Console.WriteLine("m isn't the smallest.");
}

// NOT and OR
m = 4;
if (!(m >= n || m >= p))
{
    Console.WriteLine("Now m is the smallest.");
}
// Output:
// The condition is false (result is true).
// Nothing is larger than m.
// Nothing is larger than m.
// m isn't the smallest.
// Now m is the smallest.
```

## <a name="c-language-specification"></a><span data-ttu-id="6c972-137">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6c972-137">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="6c972-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6c972-138">See also</span></span>

- [<span data-ttu-id="6c972-139">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6c972-139">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6c972-140">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6c972-140">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6c972-141">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="6c972-141">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="6c972-142">Оператор ?:</span><span class="sxs-lookup"><span data-stu-id="6c972-142">?: Operator</span></span>](../operators/conditional-operator.md)
- [<span data-ttu-id="6c972-143">Оператор if-else (C++)</span><span class="sxs-lookup"><span data-stu-id="6c972-143">if-else Statement (C++)</span></span>](/cpp/cpp/if-else-statement-cpp)
- [<span data-ttu-id="6c972-144">switch</span><span class="sxs-lookup"><span data-stu-id="6c972-144">switch</span></span>](switch.md)
