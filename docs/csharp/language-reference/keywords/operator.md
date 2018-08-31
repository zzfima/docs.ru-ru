---
title: Ключевое слово operator (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: c3bfada235993670bf158fe9803a09707b2b3251
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929876"
---
# <a name="operator-c-reference"></a><span data-ttu-id="9384c-102">operator (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9384c-102">operator (C# Reference)</span></span>

<span data-ttu-id="9384c-103">Ключевое слово `operator` используется для перегрузки встроенного оператора или выполнения пользовательского преобразования в объявлении класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="9384c-103">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>

## <a name="example"></a><span data-ttu-id="9384c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="9384c-104">Example</span></span>

<span data-ttu-id="9384c-105">Ниже приведен сильно упрощенный класс для дробных чисел.</span><span class="sxs-lookup"><span data-stu-id="9384c-105">The following is a very simplified class for fractional numbers.</span></span> <span data-ttu-id="9384c-106">Он перегружает операторы `+` и `*` для выполнения сложения и умножения, а также предоставляет оператор преобразования, который преобразует тип `Fraction` в тип `double`.</span><span class="sxs-lookup"><span data-stu-id="9384c-106">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="9384c-107">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="9384c-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="9384c-108">См. также</span><span class="sxs-lookup"><span data-stu-id="9384c-108">See also</span></span>

- [<span data-ttu-id="9384c-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="9384c-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9384c-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9384c-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9384c-111">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="9384c-111">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="9384c-112">implicit</span><span class="sxs-lookup"><span data-stu-id="9384c-112">implicit</span></span>](implicit.md)
- [<span data-ttu-id="9384c-113">explicit</span><span class="sxs-lookup"><span data-stu-id="9384c-113">explicit</span></span>](explicit.md)
- [<span data-ttu-id="9384c-114">Практическое руководство. Реализация определенных пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="9384c-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
