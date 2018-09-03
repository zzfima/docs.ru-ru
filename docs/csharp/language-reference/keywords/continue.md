---
title: Оператор continue (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 37315caf14ba829dfc91da065bc49982f21b947f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43408235"
---
# <a name="continue-c-reference"></a><span data-ttu-id="6155d-102">continue (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6155d-102">continue (C# Reference)</span></span>

<span data-ttu-id="6155d-103">Оператор `continue` передает управление следующей итерации вложенного оператора [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md) или [foreach](../../../csharp/language-reference/keywords/foreach-in.md), в котором она встречается.</span><span class="sxs-lookup"><span data-stu-id="6155d-103">The `continue` statement passes control to the next iteration of the enclosing [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="6155d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="6155d-104">Example</span></span>

<span data-ttu-id="6155d-105">В этом примере инициализируется счетчик, выполняющий отсчет от 1 до 10.</span><span class="sxs-lookup"><span data-stu-id="6155d-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="6155d-106">Благодаря использованию оператора `continue` в сочетании с выражением `(i < 9)` операторы между `continue` и концом текста `for` пропускаются.</span><span class="sxs-lookup"><span data-stu-id="6155d-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="6155d-107">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6155d-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="6155d-108">См. также</span><span class="sxs-lookup"><span data-stu-id="6155d-108">See also</span></span>

- [<span data-ttu-id="6155d-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6155d-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="6155d-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6155d-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="6155d-111">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="6155d-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="6155d-112">Оператор break</span><span class="sxs-lookup"><span data-stu-id="6155d-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)  
- [<span data-ttu-id="6155d-113">Операторы перехода</span><span class="sxs-lookup"><span data-stu-id="6155d-113">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)