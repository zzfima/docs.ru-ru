---
title: while (Справочник по C#)
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: e3e9493b5371fbd6f53a779ba73743efc6d6e05b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514064"
---
# <a name="while-c-reference"></a><span data-ttu-id="7d223-102">while (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="7d223-102">while (C# Reference)</span></span>

<span data-ttu-id="7d223-103">Оператор `while` выполняет оператор или блок операторов, пока определенное логическое выражение равно значению `true`.</span><span class="sxs-lookup"><span data-stu-id="7d223-103">The `while` statement executes a statement or a block of statements while a specified boolean expression evaluates to `true`.</span></span> <span data-ttu-id="7d223-104">Так как это выражение оценивается перед каждым выполнением цикла, цикл `while` выполняется ноль или несколько раз.</span><span class="sxs-lookup"><span data-stu-id="7d223-104">Because that expression is evaluated before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="7d223-105">Это отличает его от цикла [do](do.md), который выполняется от одного до нескольких раз.</span><span class="sxs-lookup"><span data-stu-id="7d223-105">This differs from the [do](do.md) loop, which executes one or more times.</span></span>

<span data-ttu-id="7d223-106">В любой точке блока операторов `while` можно разорвать цикл с помощью оператора [break](break.md).</span><span class="sxs-lookup"><span data-stu-id="7d223-106">At any point within the `while` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="7d223-107">Можно перейти непосредственно к оценке выражения `while`, воспользовавшись оператором [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="7d223-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="7d223-108">Если значение выражения оценивается как `true`, выполнение продолжается с первого оператора цикла.</span><span class="sxs-lookup"><span data-stu-id="7d223-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="7d223-109">В противном случае выполнение продолжается с первого оператора после цикла.</span><span class="sxs-lookup"><span data-stu-id="7d223-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="7d223-110">Также можно выйти из цикла `while` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="7d223-110">You also can exit a `while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="7d223-111">Пример</span><span class="sxs-lookup"><span data-stu-id="7d223-111">Example</span></span>

<span data-ttu-id="7d223-112">В следующем примере показано применение оператора `while`.</span><span class="sxs-lookup"><span data-stu-id="7d223-112">The following example shows the usage of the `while` statement.</span></span> <span data-ttu-id="7d223-113">Нажмите **Запустить** для выполнения примера кода.</span><span class="sxs-lookup"><span data-stu-id="7d223-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="7d223-114">После этого можно изменить код и запустить его еще раз.</span><span class="sxs-lookup"><span data-stu-id="7d223-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[while loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="7d223-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7d223-115">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7d223-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7d223-116">See also</span></span>

- [<span data-ttu-id="7d223-117">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="7d223-117">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="7d223-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7d223-118">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="7d223-119">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="7d223-119">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="7d223-120">Оператор while (C++)</span><span class="sxs-lookup"><span data-stu-id="7d223-120">while Statement (C++)</span></span>](/cpp/cpp/while-statement-cpp)  
- [<span data-ttu-id="7d223-121">Операторы итерации</span><span class="sxs-lookup"><span data-stu-id="7d223-121">Iteration Statements</span></span>](iteration-statements.md)  
- [<span data-ttu-id="7d223-122">Оператор do</span><span class="sxs-lookup"><span data-stu-id="7d223-122">do statement</span></span>](do.md)  
