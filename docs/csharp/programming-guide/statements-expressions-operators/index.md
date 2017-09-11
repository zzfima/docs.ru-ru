---
title: "Операторы и выражения (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- expressions [C#]
- operators [C#]
- C# language, statements
- C# language, operators
- C# language, expressions
- statements [C#]
ms.assetid: 20f8469d-5a6a-4084-ad90-0856b7e97e45
caps.latest.revision: 22
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
ms.openlocfilehash: 71988a5b9aa59b2655b4fd7b91522fe69c8064b6
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="statements-expressions-and-operators-c-programming-guide"></a><span data-ttu-id="2afc0-102">Операторы и выражения (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="2afc0-102">Statements, Expressions, and Operators (C# Programming Guide)</span></span>
<span data-ttu-id="2afc0-103">Код приложения на C# состоит из операторов, которые включают ключевые слова, выражения и символьные операторы.</span><span class="sxs-lookup"><span data-stu-id="2afc0-103">The C# code that comprises an application consists of statements made up of keywords, expressions and operators.</span></span> <span data-ttu-id="2afc0-104">В этом разделе содержатся сведения об этих базовых элементах программы на C#.</span><span class="sxs-lookup"><span data-stu-id="2afc0-104">This section contains information regarding these fundamental elements of a C# program.</span></span>  
  
 <span data-ttu-id="2afc0-105">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="2afc0-105">For more information, see:</span></span>  
  
-   [<span data-ttu-id="2afc0-106">Операторы</span><span class="sxs-lookup"><span data-stu-id="2afc0-106">Statements</span></span>](../../../csharp/programming-guide/statements-expressions-operators/statements.md)  
  
-   [<span data-ttu-id="2afc0-107">Выражения</span><span class="sxs-lookup"><span data-stu-id="2afc0-107">Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
    -   [<span data-ttu-id="2afc0-108">Элементы, воплощающие выражение</span><span class="sxs-lookup"><span data-stu-id="2afc0-108">Expression-bodied members</span></span>](expression-bodied-members.md)
 
-   [<span data-ttu-id="2afc0-109">Операторы</span><span class="sxs-lookup"><span data-stu-id="2afc0-109">Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
-   [<span data-ttu-id="2afc0-110">Анонимные функции</span><span class="sxs-lookup"><span data-stu-id="2afc0-110">Anonymous Functions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [<span data-ttu-id="2afc0-111">Перегружаемые операторы</span><span class="sxs-lookup"><span data-stu-id="2afc0-111">Overloadable Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)  
  
-   [<span data-ttu-id="2afc0-112">Операторы преобразования</span><span class="sxs-lookup"><span data-stu-id="2afc0-112">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
  
    -   [<span data-ttu-id="2afc0-113">Использование операторов преобразования</span><span class="sxs-lookup"><span data-stu-id="2afc0-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
    -   [<span data-ttu-id="2afc0-114">Практическое руководство. Реализация определенных пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="2afc0-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="2afc0-115">Практическое руководство. Перегрузка операторов для реализации класса комплексных чисел</span><span class="sxs-lookup"><span data-stu-id="2afc0-115">How to: Use Operator Overloading to Create a Complex Number Class</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-operator-overloading-to-create-a-complex-number-class.md)  
  
-   [<span data-ttu-id="2afc0-116">Сравнения на равенство</span><span class="sxs-lookup"><span data-stu-id="2afc0-116">Equality Comparisons</span></span>](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="2afc0-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="2afc0-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2afc0-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2afc0-118">See Also</span></span>  
 <span data-ttu-id="2afc0-119">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2afc0-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="2afc0-120">Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="2afc0-120">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)

