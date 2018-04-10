---
title: Операторы и выражения (Руководство по программированию на C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
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
ms.openlocfilehash: b7c634cb0c0e5f86e324999360d2bc64a457d5da
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="statements-expressions-and-operators-c-programming-guide"></a><span data-ttu-id="5b5c5-102">Операторы и выражения (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="5b5c5-102">Statements, Expressions, and Operators (C# Programming Guide)</span></span>
<span data-ttu-id="5b5c5-103">Код приложения на C# состоит из операторов, которые включают ключевые слова, выражения и символьные операторы.</span><span class="sxs-lookup"><span data-stu-id="5b5c5-103">The C# code that comprises an application consists of statements made up of keywords, expressions and operators.</span></span> <span data-ttu-id="5b5c5-104">В этом разделе содержатся сведения об этих базовых элементах программы на C#.</span><span class="sxs-lookup"><span data-stu-id="5b5c5-104">This section contains information regarding these fundamental elements of a C# program.</span></span>  
  
 <span data-ttu-id="5b5c5-105">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="5b5c5-105">For more information, see:</span></span>  
  
-   [<span data-ttu-id="5b5c5-106">Операторы</span><span class="sxs-lookup"><span data-stu-id="5b5c5-106">Statements</span></span>](../../../csharp/programming-guide/statements-expressions-operators/statements.md)  
  
-   [<span data-ttu-id="5b5c5-107">Выражения</span><span class="sxs-lookup"><span data-stu-id="5b5c5-107">Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
    -   [<span data-ttu-id="5b5c5-108">Элементы, воплощающие выражение</span><span class="sxs-lookup"><span data-stu-id="5b5c5-108">Expression-bodied members</span></span>](expression-bodied-members.md)
 
-   [<span data-ttu-id="5b5c5-109">Операторы</span><span class="sxs-lookup"><span data-stu-id="5b5c5-109">Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
-   [<span data-ttu-id="5b5c5-110">Анонимные функции</span><span class="sxs-lookup"><span data-stu-id="5b5c5-110">Anonymous Functions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [<span data-ttu-id="5b5c5-111">Перегружаемые операторы</span><span class="sxs-lookup"><span data-stu-id="5b5c5-111">Overloadable Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)  
  
-   [<span data-ttu-id="5b5c5-112">Операторы преобразования</span><span class="sxs-lookup"><span data-stu-id="5b5c5-112">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
  
    -   [<span data-ttu-id="5b5c5-113">Использование операторов преобразования</span><span class="sxs-lookup"><span data-stu-id="5b5c5-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
    -   [<span data-ttu-id="5b5c5-114">Практическое руководство. Реализация определенных пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="5b5c5-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="5b5c5-115">Практическое руководство. Перегрузка операторов для реализации класса комплексных чисел</span><span class="sxs-lookup"><span data-stu-id="5b5c5-115">How to: Use Operator Overloading to Create a Complex Number Class</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-operator-overloading-to-create-a-complex-number-class.md)  
  
-   [<span data-ttu-id="5b5c5-116">Сравнения на равенство</span><span class="sxs-lookup"><span data-stu-id="5b5c5-116">Equality Comparisons</span></span>](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="5b5c5-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5b5c5-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5b5c5-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5b5c5-118">See Also</span></span>  
 [<span data-ttu-id="5b5c5-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5b5c5-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5b5c5-120">Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="5b5c5-120">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)
