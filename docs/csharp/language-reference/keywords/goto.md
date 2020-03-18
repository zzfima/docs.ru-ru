---
title: Оператор goto. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: 076f793e880a7b4d1e8872d80e88c44cdf077541
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715277"
---
# <a name="goto-c-reference"></a><span data-ttu-id="99acf-102">goto (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="99acf-102">goto (C# Reference)</span></span>

<span data-ttu-id="99acf-103">Оператор `goto` передает управление программой непосредственно оператору с меткой.</span><span class="sxs-lookup"><span data-stu-id="99acf-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>

<span data-ttu-id="99acf-104">Оператор `goto` часто используется для передачи управления определенной метке смены регистра или метке по умолчанию в операторе `switch`.</span><span class="sxs-lookup"><span data-stu-id="99acf-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>

<span data-ttu-id="99acf-105">`goto` Этот оператор также удобно использовать для выхода из глубоко вложенных циклов.</span><span class="sxs-lookup"><span data-stu-id="99acf-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>

## <a name="example"></a><span data-ttu-id="99acf-106">Пример</span><span class="sxs-lookup"><span data-stu-id="99acf-106">Example</span></span>

<span data-ttu-id="99acf-107">В следующем примере демонстрируется использование `goto` в операторе [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="99acf-107">The following example demonstrates using `goto` in a [switch](switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a><span data-ttu-id="99acf-108">Пример</span><span class="sxs-lookup"><span data-stu-id="99acf-108">Example</span></span>

<span data-ttu-id="99acf-109">В следующем примере демонстрируется использование `goto` для выхода из вложенных циклов.</span><span class="sxs-lookup"><span data-stu-id="99acf-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="99acf-110">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="99acf-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="99acf-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="99acf-111">See also</span></span>

- [<span data-ttu-id="99acf-112">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="99acf-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="99acf-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="99acf-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="99acf-114">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="99acf-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="99acf-115">Оператор goto (C++)</span><span class="sxs-lookup"><span data-stu-id="99acf-115">goto Statement (C++)</span></span>](/cpp/cpp/goto-statement-cpp)
