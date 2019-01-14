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
ms.openlocfilehash: 6e485bc80a213be6a5d0da8a00c8ca718f867efb
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222940"
---
# <a name="while-c-reference"></a><span data-ttu-id="42649-102">while (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="42649-102">while (C# Reference)</span></span>

<span data-ttu-id="42649-103">Оператор `while` выполняет оператор или блок операторов, пока определенное логическое выражение равно значению `true`.</span><span class="sxs-lookup"><span data-stu-id="42649-103">The `while` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="42649-104">Так как это выражение оценивается перед каждым выполнением цикла, цикл `while` выполняется ноль или несколько раз.</span><span class="sxs-lookup"><span data-stu-id="42649-104">Because that expression is evaluated before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="42649-105">Это отличает его от цикла [do](do.md), который выполняется от одного до нескольких раз.</span><span class="sxs-lookup"><span data-stu-id="42649-105">This differs from the [do](do.md) loop, which executes one or more times.</span></span>

<span data-ttu-id="42649-106">В любой точке блока операторов `while` можно разорвать цикл с помощью оператора [break](break.md).</span><span class="sxs-lookup"><span data-stu-id="42649-106">At any point within the `while` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="42649-107">Можно перейти непосредственно к оценке выражения `while`, воспользовавшись оператором [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="42649-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="42649-108">Если значение выражения оценивается как `true`, выполнение продолжается с первого оператора цикла.</span><span class="sxs-lookup"><span data-stu-id="42649-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="42649-109">В противном случае выполнение продолжается с первого оператора после цикла.</span><span class="sxs-lookup"><span data-stu-id="42649-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="42649-110">Также можно выйти из цикла `while` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="42649-110">You also can exit a `while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="42649-111">Пример</span><span class="sxs-lookup"><span data-stu-id="42649-111">Example</span></span>

<span data-ttu-id="42649-112">В следующем примере показано применение оператора `while`.</span><span class="sxs-lookup"><span data-stu-id="42649-112">The following example shows the usage of the `while` statement.</span></span> <span data-ttu-id="42649-113">Нажмите **Запустить** для выполнения примера кода.</span><span class="sxs-lookup"><span data-stu-id="42649-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="42649-114">После этого можно изменить код и запустить его еще раз.</span><span class="sxs-lookup"><span data-stu-id="42649-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[while loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="42649-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="42649-115">C# language specification</span></span>

<span data-ttu-id="42649-116">Дополнительные сведения см. в разделе [Оператор while](~/_csharplang/spec/statements.md#the-while-statement) в документации [Предварительная спецификация C# 6.0](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="42649-116">For more information, see [The while statement](~/_csharplang/spec/statements.md#the-while-statement) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="42649-117">См. также</span><span class="sxs-lookup"><span data-stu-id="42649-117">See also</span></span>

- [<span data-ttu-id="42649-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="42649-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="42649-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="42649-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="42649-120">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="42649-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="42649-121">Операторы итерации</span><span class="sxs-lookup"><span data-stu-id="42649-121">Iteration Statements</span></span>](iteration-statements.md)
- [<span data-ttu-id="42649-122">Оператор do</span><span class="sxs-lookup"><span data-stu-id="42649-122">do statement</span></span>](do.md)