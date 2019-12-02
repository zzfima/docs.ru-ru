---
title: Справочник по C#. do
ms.custom: seodec18
ms.date: 05/28/2018
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 5612cfb2462117ac431de9c702cd8137f495e5dc
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2019
ms.locfileid: "74551810"
---
# <a name="do-c-reference"></a><span data-ttu-id="195da-102">do (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="195da-102">do (C# Reference)</span></span>

<span data-ttu-id="195da-103">Оператор `do` выполняет оператор или блок операторов, пока определенное логическое выражение равно значению `true`.</span><span class="sxs-lookup"><span data-stu-id="195da-103">The `do` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="195da-104">Так как это выражение оценивается после каждого выполнения цикла, цикл `do-while` выполняется один или несколько раз.</span><span class="sxs-lookup"><span data-stu-id="195da-104">Because that expression is evaluated after each execution of the loop, a `do-while` loop executes one or more times.</span></span> <span data-ttu-id="195da-105">Это отличает его от цикла [while](while.md), который выполняется от нуля до нескольких раз.</span><span class="sxs-lookup"><span data-stu-id="195da-105">This differs from the [while](while.md) loop, which executes zero or more times.</span></span>

<span data-ttu-id="195da-106">В любой точке блока операторов `do` можно разорвать цикл с помощью оператора [break](break.md).</span><span class="sxs-lookup"><span data-stu-id="195da-106">At any point within the `do` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="195da-107">Можно перейти непосредственно к оценке выражения `while`, воспользовавшись оператором [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="195da-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="195da-108">Если значение выражения оценивается как `true`, выполнение продолжается с первого оператора цикла.</span><span class="sxs-lookup"><span data-stu-id="195da-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="195da-109">В противном случае выполнение продолжается с первого оператора после цикла.</span><span class="sxs-lookup"><span data-stu-id="195da-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="195da-110">Также можно выйти из цикла `do-while` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="195da-110">You also can exit a `do-while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="195da-111">Пример</span><span class="sxs-lookup"><span data-stu-id="195da-111">Example</span></span>

<span data-ttu-id="195da-112">В следующем примере показано применение оператора `do`.</span><span class="sxs-lookup"><span data-stu-id="195da-112">The following example shows the usage of the `do` statement.</span></span> <span data-ttu-id="195da-113">Нажмите **Запустить** для выполнения примера кода.</span><span class="sxs-lookup"><span data-stu-id="195da-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="195da-114">После этого можно изменить код и запустить его еще раз.</span><span class="sxs-lookup"><span data-stu-id="195da-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[do loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="195da-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="195da-115">C# language specification</span></span>

<span data-ttu-id="195da-116">Дополнительные сведения см. в разделе [Оператор do](~/_csharplang/spec/statements.md#the-do-statement) в документации [Предварительная спецификация C# 6.0](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="195da-116">For more information, see [The do statement](~/_csharplang/spec/statements.md#the-do-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="195da-117">См. также</span><span class="sxs-lookup"><span data-stu-id="195da-117">See also</span></span>

- [<span data-ttu-id="195da-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="195da-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="195da-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="195da-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="195da-120">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="195da-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="195da-121">Оператор while</span><span class="sxs-lookup"><span data-stu-id="195da-121">while statement</span></span>](while.md)
