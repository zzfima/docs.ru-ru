---
title: var. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: ff8348a725f43fa8789c73fa58549da26126369c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712888"
---
# <a name="var-c-reference"></a><span data-ttu-id="3ffc4-102">var (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="3ffc4-102">var (C# Reference)</span></span>

<span data-ttu-id="3ffc4-103">Начиная с Visual C# 3.0, переменные, объявленные в области действия метода, получают неявный "тип" `var`.</span><span class="sxs-lookup"><span data-stu-id="3ffc4-103">Beginning in Visual C# 3.0, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="3ffc4-104">Неявно типизированные локальные переменные является строго типизированными, как если бы вы объявили тип самостоятельно, однако его определяет компилятор.</span><span class="sxs-lookup"><span data-stu-id="3ffc4-104">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="3ffc4-105">Следующие два объявления `i` функционально эквивалентны:</span><span class="sxs-lookup"><span data-stu-id="3ffc4-105">The following two declarations of `i` are functionally equivalent:</span></span>

```csharp
var i = 10; // Implicitly typed.
int i = 10; // Explicitly typed.
```

<span data-ttu-id="3ffc4-106">Дополнительные сведения см. в разделах [Неявно типизированные локальные переменные](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) и [Связи типов в операциях запроса LINQ](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="3ffc4-106">For more information, see [Implicitly Typed Local Variables](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Type Relationships in LINQ Query Operations](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>

## <a name="example"></a><span data-ttu-id="3ffc4-107">Пример</span><span class="sxs-lookup"><span data-stu-id="3ffc4-107">Example</span></span>

<span data-ttu-id="3ffc4-108">В следующем примере показаны два выражения запросов.</span><span class="sxs-lookup"><span data-stu-id="3ffc4-108">The following example shows two query expressions.</span></span> <span data-ttu-id="3ffc4-109">В первом выражении использование `var` разрешено, но не является обязательным, поскольку тип результата запроса может быть задан явно как `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="3ffc4-109">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="3ffc4-110">Однако во втором выражении благодаря `var` результат может быть коллекцией анонимных типов, и имя этого типа доступно только для компилятора.</span><span class="sxs-lookup"><span data-stu-id="3ffc4-110">However, in the second expression, `var` allows the result to be a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="3ffc4-111">Использование `var` делает создание нового класса для результата необязательным.</span><span class="sxs-lookup"><span data-stu-id="3ffc4-111">Use of `var` eliminates the requirement to create a new class for the result.</span></span> <span data-ttu-id="3ffc4-112">Обратите внимание на то, что во втором примере переменная итерации `foreach``item` также типизирована неявно.</span><span class="sxs-lookup"><span data-stu-id="3ffc4-112">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>

[!code-csharp[csrefKeywordsTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#18)]

## <a name="see-also"></a><span data-ttu-id="3ffc4-113">См. также</span><span class="sxs-lookup"><span data-stu-id="3ffc4-113">See also</span></span>

- [<span data-ttu-id="3ffc4-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="3ffc4-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3ffc4-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3ffc4-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3ffc4-116">Неявно типизированные локальные переменные</span><span class="sxs-lookup"><span data-stu-id="3ffc4-116">Implicitly Typed Local Variables</span></span>](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
