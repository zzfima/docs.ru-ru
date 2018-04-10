---
title: implicit (Справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c893c7a9afbdc6f715010d537e9ccaf66c5785c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="implicit-c-reference"></a><span data-ttu-id="c05ce-102">implicit (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c05ce-102">implicit (C# Reference)</span></span>
<span data-ttu-id="c05ce-103">Ключевое слово `implicit` служит для объявления неявного оператора преобразования пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="c05ce-103">The `implicit` keyword is used to declare an implicit user-defined type conversion operator.</span></span> <span data-ttu-id="c05ce-104">Этот оператор обеспечивает неявное преобразование между пользовательским типом и другим типом, если при преобразовании исключается утрата данных.</span><span class="sxs-lookup"><span data-stu-id="c05ce-104">Use it to enable implicit conversions between a user-defined type and another type, if the conversion is guaranteed not to cause a loss of data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c05ce-105">Пример</span><span class="sxs-lookup"><span data-stu-id="c05ce-105">Example</span></span>  
 [!code-csharp[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]  
  
 <span data-ttu-id="c05ce-106">Неявное преобразование позволяет устранить ненужные операции приведения и повышает удобочитаемость исходного кода.</span><span class="sxs-lookup"><span data-stu-id="c05ce-106">By eliminating unnecessary casts, implicit conversions can improve source code readability.</span></span> <span data-ttu-id="c05ce-107">Однако поскольку при неявных преобразованиях разработчикам не требуется явным образом приводить один тип к другому, нужно осторожно применять неявные преобразования, чтобы обеспечить правильные результаты.</span><span class="sxs-lookup"><span data-stu-id="c05ce-107">However, because implicit conversions do not require programmers to explicitly cast from one type to the other, care must be taken to prevent unexpected results.</span></span> <span data-ttu-id="c05ce-108">В общем случае операторы неявного преобразования не должны создавать исключений и не должны терять данные, чтобы их можно было безопасно использовать.</span><span class="sxs-lookup"><span data-stu-id="c05ce-108">In general, implicit conversion operators should never throw exceptions and never lose information so that they can be used safely without the programmer's awareness.</span></span> <span data-ttu-id="c05ce-109">Если оператор преобразования не соответствует таким условиям, его нужно пометить словом `explicit`.</span><span class="sxs-lookup"><span data-stu-id="c05ce-109">If a conversion operator cannot meet those criteria, it should be marked `explicit`.</span></span> <span data-ttu-id="c05ce-110">Дополнительные сведения см. в разделе [Использование операторов преобразования](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="c05ce-110">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c05ce-111">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c05ce-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c05ce-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c05ce-112">See Also</span></span>  
 [<span data-ttu-id="c05ce-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="c05ce-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c05ce-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c05ce-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c05ce-115">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="c05ce-115">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="c05ce-116">explicit</span><span class="sxs-lookup"><span data-stu-id="c05ce-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
 [<span data-ttu-id="c05ce-117">operator (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c05ce-117">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)  
 [<span data-ttu-id="c05ce-118">Практическое руководство. Реализация определенных пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="c05ce-118">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
