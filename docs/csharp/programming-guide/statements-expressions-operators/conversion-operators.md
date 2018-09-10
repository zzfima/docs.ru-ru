---
title: Операторы преобразования (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
ms.openlocfilehash: cbf6a83d43a1b3a69e82a35d5d0875f62422cd3f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44183318"
---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="c7dae-102">Операторы преобразования (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="c7dae-102">Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="c7dae-103">Разработчики на C# могут объявлять преобразования классов или структур в другие классы, структуры или базовые типы и обратно.</span><span class="sxs-lookup"><span data-stu-id="c7dae-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="c7dae-104">Преобразования определяются как операторы и называются по имени типа, в который осуществляется преобразование.</span><span class="sxs-lookup"><span data-stu-id="c7dae-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="c7dae-105">В качестве содержащего типа должен выступать либо тип преобразуемого аргумента, либо тип результата преобразования, но не оба эти типа.</span><span class="sxs-lookup"><span data-stu-id="c7dae-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="c7dae-106">Обзор операторов преобразования</span><span class="sxs-lookup"><span data-stu-id="c7dae-106">Conversion Operators Overview</span></span>  
 <span data-ttu-id="c7dae-107">Операторы преобразования имеют следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="c7dae-107">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="c7dae-108">Преобразования, объявленные как `implicit`, выполняются автоматически при необходимости.</span><span class="sxs-lookup"><span data-stu-id="c7dae-108">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="c7dae-109">Преобразования, объявленные как `explicit`, требуют вызова приведения.</span><span class="sxs-lookup"><span data-stu-id="c7dae-109">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="c7dae-110">Все преобразования должны объявляться как `static`.</span><span class="sxs-lookup"><span data-stu-id="c7dae-110">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c7dae-111">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c7dae-111">Related Sections</span></span>  
 <span data-ttu-id="c7dae-112">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="c7dae-112">For more information:</span></span>  
  
-   [<span data-ttu-id="c7dae-113">Использование операторов преобразования</span><span class="sxs-lookup"><span data-stu-id="c7dae-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="c7dae-114">Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="c7dae-114">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="c7dae-115">Практическое руководство. Реализация определенных пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="c7dae-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="c7dae-116">explicit</span><span class="sxs-lookup"><span data-stu-id="c7dae-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="c7dae-117">implicit</span><span class="sxs-lookup"><span data-stu-id="c7dae-117">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="c7dae-118">static</span><span class="sxs-lookup"><span data-stu-id="c7dae-118">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="c7dae-119">См. также</span><span class="sxs-lookup"><span data-stu-id="c7dae-119">See Also</span></span>

- <xref:System.Convert>  
- [<span data-ttu-id="c7dae-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c7dae-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="c7dae-121">Связанные пользовательские явные преобразования в C#</span><span class="sxs-lookup"><span data-stu-id="c7dae-121">Chained user-defined explicit conversions in C#</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
