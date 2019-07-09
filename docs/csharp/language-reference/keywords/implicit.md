---
title: implicit. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
ms.openlocfilehash: 00fe1a02b52ef2ddc393bc7424efa73fc4059a9c
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610115"
---
# <a name="implicit-c-reference"></a><span data-ttu-id="d7981-102">implicit (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d7981-102">implicit (C# Reference)</span></span>

<span data-ttu-id="d7981-103">Ключевое слово `implicit` служит для объявления неявного оператора преобразования пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="d7981-103">The `implicit` keyword is used to declare an implicit user-defined type conversion operator.</span></span> <span data-ttu-id="d7981-104">Этот оператор обеспечивает неявное преобразование между пользовательским типом и другим типом, если при преобразовании исключается утрата данных.</span><span class="sxs-lookup"><span data-stu-id="d7981-104">Use it to enable implicit conversions between a user-defined type and another type, if the conversion is guaranteed not to cause a loss of data.</span></span>

## <a name="example"></a><span data-ttu-id="d7981-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d7981-105">Example</span></span>

[!code-csharp[csrefKeywordsConversion#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#5)]

<span data-ttu-id="d7981-106">Неявное преобразование позволяет устранить ненужные операции приведения и повышает удобочитаемость исходного кода.</span><span class="sxs-lookup"><span data-stu-id="d7981-106">By eliminating unnecessary casts, implicit conversions can improve source code readability.</span></span> <span data-ttu-id="d7981-107">Однако поскольку при неявных преобразованиях разработчикам не требуется явным образом приводить один тип к другому, нужно осторожно применять неявные преобразования, чтобы обеспечить правильные результаты.</span><span class="sxs-lookup"><span data-stu-id="d7981-107">However, because implicit conversions do not require programmers to explicitly cast from one type to the other, care must be taken to prevent unexpected results.</span></span> <span data-ttu-id="d7981-108">В общем случае операторы неявного преобразования не должны создавать исключений и не должны терять данные, чтобы их можно было безопасно использовать.</span><span class="sxs-lookup"><span data-stu-id="d7981-108">In general, implicit conversion operators should never throw exceptions and never lose information so that they can be used safely without the programmer's awareness.</span></span> <span data-ttu-id="d7981-109">Если оператор преобразования не соответствует таким условиям, его нужно пометить словом `explicit`.</span><span class="sxs-lookup"><span data-stu-id="d7981-109">If a conversion operator cannot meet those criteria, it should be marked `explicit`.</span></span> <span data-ttu-id="d7981-110">Дополнительные сведения см. в разделе [Использование операторов преобразования](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="d7981-110">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d7981-111">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="d7981-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="d7981-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d7981-112">See also</span></span>

- [<span data-ttu-id="d7981-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d7981-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d7981-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d7981-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d7981-115">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="d7981-115">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d7981-116">explicit</span><span class="sxs-lookup"><span data-stu-id="d7981-116">explicit</span></span>](explicit.md)
- [<span data-ttu-id="d7981-117">Перегрузка операторов</span><span class="sxs-lookup"><span data-stu-id="d7981-117">Operator overloading</span></span>](../operators/operator-overloading.md)
- [<span data-ttu-id="d7981-118">Практическое руководство. Реализация определяемых пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="d7981-118">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
