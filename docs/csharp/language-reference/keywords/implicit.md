---
title: implicit (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
ms.openlocfilehash: 160d9f7c0d58abd685bf1d799b53cc96a26aebe8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="implicit-c-reference"></a><span data-ttu-id="e831e-102">implicit (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e831e-102">implicit (C# Reference)</span></span>
<span data-ttu-id="e831e-103">Ключевое слово `implicit` служит для объявления неявного оператора преобразования пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="e831e-103">The `implicit` keyword is used to declare an implicit user-defined type conversion operator.</span></span> <span data-ttu-id="e831e-104">Этот оператор обеспечивает неявное преобразование между пользовательским типом и другим типом, если при преобразовании исключается утрата данных.</span><span class="sxs-lookup"><span data-stu-id="e831e-104">Use it to enable implicit conversions between a user-defined type and another type, if the conversion is guaranteed not to cause a loss of data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e831e-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e831e-105">Example</span></span>  
 [!code-csharp[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]  
  
 <span data-ttu-id="e831e-106">Неявное преобразование позволяет устранить ненужные операции приведения и повышает удобочитаемость исходного кода.</span><span class="sxs-lookup"><span data-stu-id="e831e-106">By eliminating unnecessary casts, implicit conversions can improve source code readability.</span></span> <span data-ttu-id="e831e-107">Однако поскольку при неявных преобразованиях разработчикам не требуется явным образом приводить один тип к другому, нужно осторожно применять неявные преобразования, чтобы обеспечить правильные результаты.</span><span class="sxs-lookup"><span data-stu-id="e831e-107">However, because implicit conversions do not require programmers to explicitly cast from one type to the other, care must be taken to prevent unexpected results.</span></span> <span data-ttu-id="e831e-108">В общем случае операторы неявного преобразования не должны создавать исключений и не должны терять данные, чтобы их можно было безопасно использовать.</span><span class="sxs-lookup"><span data-stu-id="e831e-108">In general, implicit conversion operators should never throw exceptions and never lose information so that they can be used safely without the programmer's awareness.</span></span> <span data-ttu-id="e831e-109">Если оператор преобразования не соответствует таким условиям, его нужно пометить словом `explicit`.</span><span class="sxs-lookup"><span data-stu-id="e831e-109">If a conversion operator cannot meet those criteria, it should be marked `explicit`.</span></span> <span data-ttu-id="e831e-110">Дополнительные сведения см. в разделе [Использование операторов преобразования](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="e831e-110">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e831e-111">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e831e-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e831e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e831e-112">See Also</span></span>  
 [<span data-ttu-id="e831e-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="e831e-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e831e-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e831e-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e831e-115">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="e831e-115">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="e831e-116">explicit</span><span class="sxs-lookup"><span data-stu-id="e831e-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
 [<span data-ttu-id="e831e-117">operator (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="e831e-117">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)  
 [<span data-ttu-id="e831e-118">Практическое руководство. Реализация определенных пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="e831e-118">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
