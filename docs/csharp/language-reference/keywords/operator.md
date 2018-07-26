---
title: operator (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: d633a46e21f913aa8c05289dccfb63e71efd697e
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37959550"
---
# <a name="operator-c-reference"></a><span data-ttu-id="27d5d-102">operator (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="27d5d-102">operator (C# Reference)</span></span>
<span data-ttu-id="27d5d-103">Ключевое слово `operator` используется для перегрузки встроенного оператора или выполнения пользовательского преобразования в объявлении класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="27d5d-103">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27d5d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="27d5d-104">Example</span></span>  
 <span data-ttu-id="27d5d-105">Ниже приведен сильно упрощенный класс для дробных чисел.</span><span class="sxs-lookup"><span data-stu-id="27d5d-105">The following is a very simplified class for fractional numbers.</span></span> <span data-ttu-id="27d5d-106">Он перегружает операторы `+` и `*` для выполнения сложения и умножения, а также предоставляет оператор преобразования, который преобразует тип `Fraction` в тип `double`.</span><span class="sxs-lookup"><span data-stu-id="27d5d-106">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="27d5d-107">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="27d5d-107">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="27d5d-108">См. также</span><span class="sxs-lookup"><span data-stu-id="27d5d-108">See Also</span></span>  
 [<span data-ttu-id="27d5d-109">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="27d5d-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="27d5d-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="27d5d-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="27d5d-111">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="27d5d-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="27d5d-112">implicit</span><span class="sxs-lookup"><span data-stu-id="27d5d-112">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
 [<span data-ttu-id="27d5d-113">explicit</span><span class="sxs-lookup"><span data-stu-id="27d5d-113">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
 [<span data-ttu-id="27d5d-114">Практическое руководство. Реализация определенных пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="27d5d-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
