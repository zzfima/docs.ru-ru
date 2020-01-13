---
title: Справочник по C#. Оператор continue
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 83b43b31eacf0ed835ee3d7a919538eb9f1dd1e8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713664"
---
# <a name="continue-c-reference"></a><span data-ttu-id="1dd00-102">continue (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1dd00-102">continue (C# Reference)</span></span>

<span data-ttu-id="1dd00-103">Оператор `continue` передает управление следующей итерации вложенного оператора [while](./while.md), [do](./do.md), [for](./for.md) или [foreach](./foreach-in.md), в котором она встречается.</span><span class="sxs-lookup"><span data-stu-id="1dd00-103">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="1dd00-104">Пример</span><span class="sxs-lookup"><span data-stu-id="1dd00-104">Example</span></span>

<span data-ttu-id="1dd00-105">В этом примере инициализируется счетчик, выполняющий отсчет от 1 до 10.</span><span class="sxs-lookup"><span data-stu-id="1dd00-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="1dd00-106">Благодаря использованию оператора `continue` в сочетании с выражением `(i < 9)` операторы между `continue` и концом текста `for` пропускаются.</span><span class="sxs-lookup"><span data-stu-id="1dd00-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="1dd00-107">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="1dd00-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="1dd00-108">См. также</span><span class="sxs-lookup"><span data-stu-id="1dd00-108">See also</span></span>

- [<span data-ttu-id="1dd00-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="1dd00-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1dd00-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1dd00-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1dd00-111">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="1dd00-111">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="1dd00-112">Оператор break</span><span class="sxs-lookup"><span data-stu-id="1dd00-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
