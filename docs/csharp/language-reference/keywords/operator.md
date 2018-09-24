---
title: Ключевое слово operator (справочник по C#)
description: Сведения о том, как перегрузить встроенные операторы C#
ms.date: 08/27/2018
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: 1e11d7767b61becc39b1158fae9cb2abe997e4bd
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "46525754"
---
# <a name="operator-c-reference"></a><span data-ttu-id="a69db-103">operator (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a69db-103">operator (C# Reference)</span></span>

<span data-ttu-id="a69db-104">Ключевое слово `operator` используется для перегрузки встроенного оператора или выполнения пользовательского преобразования в объявлении класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="a69db-104">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>

<span data-ttu-id="a69db-105">Чтобы перегрузить оператор в пользовательском классе или структуре, создайте объявление оператора в соответствующем типе.</span><span class="sxs-lookup"><span data-stu-id="a69db-105">To overload an operator on a custom class or struct, you create an operator declaration in the corresponding type.</span></span> <span data-ttu-id="a69db-106">Объявление оператора, которое перегружает встроенный оператор C#, должно удовлетворять следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="a69db-106">The operator declaration that overloads a built-in C# operator must satisfy the following rules:</span></span>

- <span data-ttu-id="a69db-107">Оно должно включать `public` и модификатор `static`.</span><span class="sxs-lookup"><span data-stu-id="a69db-107">It includes both a `public` and a `static` modifier.</span></span>
- <span data-ttu-id="a69db-108">Оно должно включать `operator X`, где `X` — имя или обозначение перегружаемого оператора.</span><span class="sxs-lookup"><span data-stu-id="a69db-108">It includes `operator X` where `X` is the name or symbol of the operator being overloaded.</span></span>
- <span data-ttu-id="a69db-109">Унарные операторы имеют один параметр, а бинарные операторы имеют два параметра.</span><span class="sxs-lookup"><span data-stu-id="a69db-109">Unary operators have one parameter, and binary operators have two parameters.</span></span> <span data-ttu-id="a69db-110">В каждом случае по крайней мере один параметр должен иметь тот же тип, что и класс или структура, в которых объявлен этот оператор.</span><span class="sxs-lookup"><span data-stu-id="a69db-110">In each case, at least one parameter must be the same type as the class or struct that declares the operator.</span></span>

<span data-ttu-id="a69db-111">Сведения о том, как определить операторы преобразования, см. в разделах, посвященных ключевым словам [explicit](explicit.md) и [implicit](implicit.md).</span><span class="sxs-lookup"><span data-stu-id="a69db-111">For information about how to define conversion operators, see the [explicit](explicit.md) and [implicit](implicit.md) keyword articles.</span></span>

<span data-ttu-id="a69db-112">Обзор операторов C#, которые могут быть перегружены, см. в разделе [Перегружаемые операторы](../../programming-guide/statements-expressions-operators/overloadable-operators.md).</span><span class="sxs-lookup"><span data-stu-id="a69db-112">For an overview of the C# operators that can be overloaded, see the [Overloadable operators](../../programming-guide/statements-expressions-operators/overloadable-operators.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="a69db-113">Пример</span><span class="sxs-lookup"><span data-stu-id="a69db-113">Example</span></span>

<span data-ttu-id="a69db-114">В следующем примере определяется тип `Fraction`, представляющий дробные числа.</span><span class="sxs-lookup"><span data-stu-id="a69db-114">The following example defines a `Fraction` type that represents fractional numbers.</span></span> <span data-ttu-id="a69db-115">Он перегружает операторы `+` и `*` для выполнения сложения и умножения, а также предоставляет оператор преобразования, который преобразует тип `Fraction` в тип `double`.</span><span class="sxs-lookup"><span data-stu-id="a69db-115">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="a69db-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a69db-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a69db-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a69db-117">See also</span></span>

- [<span data-ttu-id="a69db-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a69db-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a69db-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a69db-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a69db-120">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="a69db-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a69db-121">implicit</span><span class="sxs-lookup"><span data-stu-id="a69db-121">implicit</span></span>](implicit.md)
- [<span data-ttu-id="a69db-122">explicit</span><span class="sxs-lookup"><span data-stu-id="a69db-122">explicit</span></span>](explicit.md)
- [<span data-ttu-id="a69db-123">Перегружаемые операторы</span><span class="sxs-lookup"><span data-stu-id="a69db-123">Overloadable operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="a69db-124">Практическое руководство. Реализация определенных пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="a69db-124">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
