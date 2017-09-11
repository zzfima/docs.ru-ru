---
title: "operator (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- operator_CSharpKeyword
- operator
dev_langs:
- CSharp
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
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
ms.openlocfilehash: 76d403493861e9c587672412cd2989c419b8717a
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="operator-c-reference"></a><span data-ttu-id="a14e0-102">operator (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a14e0-102">operator (C# Reference)</span></span>
<span data-ttu-id="a14e0-103">Ключевое слово `operator` используется для перегрузки встроенного оператора или выполнения пользовательского преобразования в объявлении класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="a14e0-103">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a14e0-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a14e0-104">Example</span></span>  
 <span data-ttu-id="a14e0-105">Ниже приведен сильно упрощенный класс для дробных чисел.</span><span class="sxs-lookup"><span data-stu-id="a14e0-105">The following is a very simplified class for fractional numbers.</span></span> <span data-ttu-id="a14e0-106">Он перегружает операторы + и * для выполнения сложения и умножения, а также предоставляет оператор преобразования, который преобразует тип Fraction в тип double.</span><span class="sxs-lookup"><span data-stu-id="a14e0-106">It overloads the + and * operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a Fraction type to a double type.</span></span>  
  
 <span data-ttu-id="a14e0-107">[!code-cs[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a14e0-107">[!code-cs[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a14e0-108">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a14e0-108">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a14e0-109">См. также</span><span class="sxs-lookup"><span data-stu-id="a14e0-109">See Also</span></span>  
 <span data-ttu-id="a14e0-110">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a14e0-110">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a14e0-111">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a14e0-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a14e0-112">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="a14e0-112">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="a14e0-113">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span><span class="sxs-lookup"><span data-stu-id="a14e0-113">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span></span>  
 <span data-ttu-id="a14e0-114">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span><span class="sxs-lookup"><span data-stu-id="a14e0-114">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span></span>  
 [<span data-ttu-id="a14e0-115">Практическое руководство. Реализация определенных пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="a14e0-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

