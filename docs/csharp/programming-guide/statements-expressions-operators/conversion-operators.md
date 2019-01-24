---
title: Руководство по программированию на C#. Операторы преобразования
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
ms.openlocfilehash: 927640b63773d24be93cc90427668f9568a39652
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362734"
---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="a4715-102">Руководство по программированию на C#. Операторы преобразования</span><span class="sxs-lookup"><span data-stu-id="a4715-102">Conversion operators (C# Programming Guide)</span></span>

<span data-ttu-id="a4715-103">Разработчики на C# могут объявлять преобразования классов или структур в другие классы, структуры или базовые типы и обратно.</span><span class="sxs-lookup"><span data-stu-id="a4715-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="a4715-104">Преобразования определяются как операторы и называются по имени типа, в который осуществляется преобразование.</span><span class="sxs-lookup"><span data-stu-id="a4715-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="a4715-105">В качестве содержащего типа должен выступать либо тип преобразуемого аргумента, либо тип результата преобразования, но не оба эти типа.</span><span class="sxs-lookup"><span data-stu-id="a4715-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="a4715-106">Общие сведения об операторах преобразования</span><span class="sxs-lookup"><span data-stu-id="a4715-106">Conversion operators overview</span></span>

 <span data-ttu-id="a4715-107">Операторы преобразования имеют следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="a4715-107">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="a4715-108">Преобразования, объявленные как `implicit`, выполняются автоматически при необходимости.</span><span class="sxs-lookup"><span data-stu-id="a4715-108">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="a4715-109">Преобразования, объявленные как `explicit`, требуют вызова приведения.</span><span class="sxs-lookup"><span data-stu-id="a4715-109">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="a4715-110">Все преобразования должны объявляться как `static`.</span><span class="sxs-lookup"><span data-stu-id="a4715-110">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a4715-111">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a4715-111">Related sections</span></span>

 <span data-ttu-id="a4715-112">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="a4715-112">For more information:</span></span>  
  
-   [<span data-ttu-id="a4715-113">Использование операторов преобразования</span><span class="sxs-lookup"><span data-stu-id="a4715-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="a4715-114">Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="a4715-114">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="a4715-115">Практическое руководство. Реализация определяемых пользователем преобразований между структурами</span><span class="sxs-lookup"><span data-stu-id="a4715-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="a4715-116">explicit</span><span class="sxs-lookup"><span data-stu-id="a4715-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="a4715-117">implicit</span><span class="sxs-lookup"><span data-stu-id="a4715-117">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="a4715-118">static</span><span class="sxs-lookup"><span data-stu-id="a4715-118">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="a4715-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a4715-119">See also</span></span>

- <xref:System.Convert>  
- [<span data-ttu-id="a4715-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a4715-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a4715-121">Связанные пользовательские явные преобразования в C#</span><span class="sxs-lookup"><span data-stu-id="a4715-121">Chained user-defined explicit conversions in C#</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
