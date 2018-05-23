---
title: Операторы преобразования (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
ms.openlocfilehash: 97e93230658b5d1da676b029169b63bc9006ddb1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="673f2-102">Операторы преобразования (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="673f2-102">Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="673f2-103">Разработчики на C# могут объявлять преобразования классов или структур в другие классы, структуры или базовые типы и обратно.</span><span class="sxs-lookup"><span data-stu-id="673f2-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="673f2-104">Преобразования определяются как операторы и называются по имени типа, в который осуществляется преобразование.</span><span class="sxs-lookup"><span data-stu-id="673f2-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="673f2-105">В качестве содержащего типа должен выступать либо тип преобразуемого аргумента, либо тип результата преобразования, но не оба эти типа.</span><span class="sxs-lookup"><span data-stu-id="673f2-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="673f2-106">Обзор операторов преобразования</span><span class="sxs-lookup"><span data-stu-id="673f2-106">Conversion Operators Overview</span></span>  
 <span data-ttu-id="673f2-107">Операторы преобразования имеют следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="673f2-107">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="673f2-108">Преобразования, объявленные как `implicit`, выполняются автоматически при необходимости.</span><span class="sxs-lookup"><span data-stu-id="673f2-108">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="673f2-109">Преобразования, объявленные как `explicit`, требуют вызова приведения.</span><span class="sxs-lookup"><span data-stu-id="673f2-109">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="673f2-110">Все преобразования должны объявляться как `static`.</span><span class="sxs-lookup"><span data-stu-id="673f2-110">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="673f2-111">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="673f2-111">Related Sections</span></span>  
 <span data-ttu-id="673f2-112">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="673f2-112">For more information:</span></span>  
  
-   [<span data-ttu-id="673f2-113">Использование операторов преобразования</span><span class="sxs-lookup"><span data-stu-id="673f2-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="673f2-114">Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="673f2-114">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="673f2-115">Практическое руководство. Реализация определенных пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="673f2-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="673f2-116">explicit</span><span class="sxs-lookup"><span data-stu-id="673f2-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="673f2-117">implicit</span><span class="sxs-lookup"><span data-stu-id="673f2-117">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="673f2-118">static</span><span class="sxs-lookup"><span data-stu-id="673f2-118">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="673f2-119">См. также</span><span class="sxs-lookup"><span data-stu-id="673f2-119">See Also</span></span>  
 <xref:System.Convert>  
 [<span data-ttu-id="673f2-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="673f2-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="673f2-121">Связанные пользовательские явные преобразования в C#</span><span class="sxs-lookup"><span data-stu-id="673f2-121">Chained user-defined explicit conversions in C#</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
