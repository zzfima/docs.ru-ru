---
title: "Операторы преобразования (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5277c1160c604ee56ff575df5bd603e115588d21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="b05df-102">Операторы преобразования (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="b05df-102">Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="b05df-103">Разработчики на C# могут объявлять преобразования классов или структур в другие классы, структуры или базовые типы и обратно.</span><span class="sxs-lookup"><span data-stu-id="b05df-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="b05df-104">Преобразования определяются как операторы и называются по имени типа, в который осуществляется преобразование.</span><span class="sxs-lookup"><span data-stu-id="b05df-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="b05df-105">В качестве содержащего типа должен выступать либо тип преобразуемого аргумента, либо тип результата преобразования, но не оба эти типа.</span><span class="sxs-lookup"><span data-stu-id="b05df-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="b05df-106">Обзор операторов преобразования</span><span class="sxs-lookup"><span data-stu-id="b05df-106">Conversion Operators Overview</span></span>  
 <span data-ttu-id="b05df-107">Операторы преобразования имеют следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="b05df-107">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="b05df-108">Преобразования, объявленные как `implicit`, выполняются автоматически при необходимости.</span><span class="sxs-lookup"><span data-stu-id="b05df-108">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="b05df-109">Преобразования, объявленные как `explicit`, требуют вызова приведения.</span><span class="sxs-lookup"><span data-stu-id="b05df-109">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="b05df-110">Все преобразования должны объявляться как `static`.</span><span class="sxs-lookup"><span data-stu-id="b05df-110">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b05df-111">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b05df-111">Related Sections</span></span>  
 <span data-ttu-id="b05df-112">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="b05df-112">For more information:</span></span>  
  
-   [<span data-ttu-id="b05df-113">Использование операторов преобразования</span><span class="sxs-lookup"><span data-stu-id="b05df-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="b05df-114">Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="b05df-114">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="b05df-115">Практическое руководство. Реализация определенных пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="b05df-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="b05df-116">explicit</span><span class="sxs-lookup"><span data-stu-id="b05df-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="b05df-117">implicit</span><span class="sxs-lookup"><span data-stu-id="b05df-117">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="b05df-118">static</span><span class="sxs-lookup"><span data-stu-id="b05df-118">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="b05df-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b05df-119">See Also</span></span>  
 <xref:System.Convert>  
 [<span data-ttu-id="b05df-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b05df-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b05df-121">Связанные пользовательские явные преобразования в C#</span><span class="sxs-lookup"><span data-stu-id="b05df-121">Chained user-defined explicit conversions in C#</span></span>](http://go.microsoft.com/fwlink/?LinkId=112384)
