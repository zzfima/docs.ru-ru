---
title: Оператор break (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 9dc71cce3cc0ca4035df483d2b3a3ab9a3bab9c5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467643"
---
# <a name="break-c-reference"></a><span data-ttu-id="b735a-102">break (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b735a-102">break (C# Reference)</span></span>

<span data-ttu-id="b735a-103">Оператор `break` завершает выполнение ближайшего оператора внешнего цикла или [switch](../../../csharp/language-reference/keywords/switch.md), в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="b735a-103">The `break` statement terminates the closest enclosing loop or [switch](../../../csharp/language-reference/keywords/switch.md) statement in which it appears.</span></span> <span data-ttu-id="b735a-104">Управление передается оператору, который расположен после завершенного оператора.</span><span class="sxs-lookup"><span data-stu-id="b735a-104">Control is passed to the statement that follows the terminated statement, if any.</span></span>

## <a name="example"></a><span data-ttu-id="b735a-105">Пример</span><span class="sxs-lookup"><span data-stu-id="b735a-105">Example</span></span>

<span data-ttu-id="b735a-106">В этом примере условный оператор содержит счетчик, который должен выполнять отсчет от 1 до 100; при этом оператор `break` завершает цикл после четырех отсчетов.</span><span class="sxs-lookup"><span data-stu-id="b735a-106">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a><span data-ttu-id="b735a-107">Пример</span><span class="sxs-lookup"><span data-stu-id="b735a-107">Example</span></span>

<span data-ttu-id="b735a-108">В этом примере оператор `break` используется для выхода из внутреннего вложенного цикла и возвращения управления внешнему циклу.</span><span class="sxs-lookup"><span data-stu-id="b735a-108">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span>

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a><span data-ttu-id="b735a-109">Пример</span><span class="sxs-lookup"><span data-stu-id="b735a-109">Example</span></span>

<span data-ttu-id="b735a-110">В этом примере демонстрируется использование `break` в операторе [switch](../../../csharp/language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="b735a-110">This example demonstrates the use of `break` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

<span data-ttu-id="b735a-111">Если вы ввели `4`, выходные данные будут следующими:</span><span class="sxs-lookup"><span data-stu-id="b735a-111">If you entered `4`, the output would be:</span></span>

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="c-language-specification"></a><span data-ttu-id="b735a-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b735a-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b735a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b735a-113">See Also</span></span>

- [<span data-ttu-id="b735a-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b735a-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="b735a-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b735a-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="b735a-116">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="b735a-116">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="b735a-117">switch</span><span class="sxs-lookup"><span data-stu-id="b735a-117">switch</span></span>](../../../csharp/language-reference/keywords/switch.md)  
- [<span data-ttu-id="b735a-118">Операторы перехода</span><span class="sxs-lookup"><span data-stu-id="b735a-118">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)  
- [<span data-ttu-id="b735a-119">Операторы итерации</span><span class="sxs-lookup"><span data-stu-id="b735a-119">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
