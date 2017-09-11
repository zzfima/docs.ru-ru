---
title: "implicit (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- implicit
- implicit_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e4452a3bb6da2d0d294ca26d6b957f2c1c4402fd
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="implicit-c-reference"></a><span data-ttu-id="167d6-102">implicit (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="167d6-102">implicit (C# Reference)</span></span>
<span data-ttu-id="167d6-103">Ключевое слово `implicit` служит для объявления неявного оператора преобразования пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="167d6-103">The `implicit` keyword is used to declare an implicit user-defined type conversion operator.</span></span> <span data-ttu-id="167d6-104">Этот оператор обеспечивает неявное преобразование между пользовательским типом и другим типом, если при преобразовании исключается утрата данных.</span><span class="sxs-lookup"><span data-stu-id="167d6-104">Use it to enable implicit conversions between a user-defined type and another type, if the conversion is guaranteed not to cause a loss of data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="167d6-105">Пример</span><span class="sxs-lookup"><span data-stu-id="167d6-105">Example</span></span>  
 <span data-ttu-id="167d6-106">[!code-cs[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="167d6-106">[!code-cs[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]</span></span>  
  
 <span data-ttu-id="167d6-107">Неявное преобразование позволяет устранить ненужные операции приведения и повышает удобочитаемость исходного кода.</span><span class="sxs-lookup"><span data-stu-id="167d6-107">By eliminating unnecessary casts, implicit conversions can improve source code readability.</span></span> <span data-ttu-id="167d6-108">Однако поскольку при неявных преобразованиях разработчикам не требуется явным образом приводить один тип к другому, нужно осторожно применять неявные преобразования, чтобы обеспечить правильные результаты.</span><span class="sxs-lookup"><span data-stu-id="167d6-108">However, because implicit conversions do not require programmers to explicitly cast from one type to the other, care must be taken to prevent unexpected results.</span></span> <span data-ttu-id="167d6-109">В общем случае операторы неявного преобразования не должны создавать исключений и не должны терять данные, чтобы их можно было безопасно использовать.</span><span class="sxs-lookup"><span data-stu-id="167d6-109">In general, implicit conversion operators should never throw exceptions and never lose information so that they can be used safely without the programmer's awareness.</span></span> <span data-ttu-id="167d6-110">Если оператор преобразования не соответствует таким условиям, его нужно пометить словом `explicit`.</span><span class="sxs-lookup"><span data-stu-id="167d6-110">If a conversion operator cannot meet those criteria, it should be marked `explicit`.</span></span> <span data-ttu-id="167d6-111">Дополнительные сведения см. в разделе [Использование операторов преобразования](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="167d6-111">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="167d6-112">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="167d6-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="167d6-113">См. также</span><span class="sxs-lookup"><span data-stu-id="167d6-113">See Also</span></span>  
 <span data-ttu-id="167d6-114">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="167d6-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="167d6-115">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="167d6-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="167d6-116">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="167d6-116">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="167d6-117">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span><span class="sxs-lookup"><span data-stu-id="167d6-117">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span></span>  
 <span data-ttu-id="167d6-118">[Оператор (справочник по C#)](../../../csharp/language-reference/keywords/operator.md) </span><span class="sxs-lookup"><span data-stu-id="167d6-118">[operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md) </span></span>  
 [<span data-ttu-id="167d6-119">Практическое руководство. Реализация определенных пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="167d6-119">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

