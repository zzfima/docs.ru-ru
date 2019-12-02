---
title: Справочник по C#. while
ms.custom: seodec18
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: fad0ceae9cf1080e7f4b553e0808fd531fd28c57
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552382"
---
# <a name="while-c-reference"></a><span data-ttu-id="485f6-102">while (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="485f6-102">while (C# Reference)</span></span>

<span data-ttu-id="485f6-103">Оператор `while` выполняет оператор или блок операторов, пока определенное логическое выражение равно значению `true`.</span><span class="sxs-lookup"><span data-stu-id="485f6-103">The `while` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="485f6-104">Так как это выражение оценивается перед каждым выполнением цикла, цикл `while` выполняется ноль или несколько раз.</span><span class="sxs-lookup"><span data-stu-id="485f6-104">Because that expression is evaluated before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="485f6-105">Это отличает его от цикла [do](do.md), который выполняется от одного до нескольких раз.</span><span class="sxs-lookup"><span data-stu-id="485f6-105">This differs from the [do](do.md) loop, which executes one or more times.</span></span>

<span data-ttu-id="485f6-106">В любой точке блока операторов `while` можно разорвать цикл с помощью оператора [break](break.md).</span><span class="sxs-lookup"><span data-stu-id="485f6-106">At any point within the `while` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="485f6-107">Можно перейти непосредственно к оценке выражения `while`, воспользовавшись оператором [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="485f6-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="485f6-108">Если значение выражения оценивается как `true`, выполнение продолжается с первого оператора цикла.</span><span class="sxs-lookup"><span data-stu-id="485f6-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="485f6-109">В противном случае выполнение продолжается с первого оператора после цикла.</span><span class="sxs-lookup"><span data-stu-id="485f6-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="485f6-110">Также можно выйти из цикла `while` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="485f6-110">You also can exit a `while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="485f6-111">Пример</span><span class="sxs-lookup"><span data-stu-id="485f6-111">Example</span></span>

<span data-ttu-id="485f6-112">В следующем примере показано применение оператора `while`.</span><span class="sxs-lookup"><span data-stu-id="485f6-112">The following example shows the usage of the `while` statement.</span></span> <span data-ttu-id="485f6-113">Нажмите **Запустить** для выполнения примера кода.</span><span class="sxs-lookup"><span data-stu-id="485f6-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="485f6-114">После этого можно изменить код и запустить его еще раз.</span><span class="sxs-lookup"><span data-stu-id="485f6-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[while loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="485f6-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="485f6-115">C# language specification</span></span>

<span data-ttu-id="485f6-116">Дополнительные сведения см. в разделе [Оператор while](~/_csharplang/spec/statements.md#the-while-statement) в документации [Предварительная спецификация C# 6.0](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="485f6-116">For more information, see [The while statement](~/_csharplang/spec/statements.md#the-while-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="485f6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="485f6-117">See also</span></span>

- [<span data-ttu-id="485f6-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="485f6-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="485f6-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="485f6-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="485f6-120">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="485f6-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="485f6-121">Оператор do</span><span class="sxs-lookup"><span data-stu-id="485f6-121">do statement</span></span>](do.md)
