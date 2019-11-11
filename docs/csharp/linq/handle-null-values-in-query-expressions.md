---
title: Обработка значений NULL в выражениях запросов (LINQ в C#)
description: Узнайте, как обрабатывать значения NULL в выражениях запросов LINQ в C#.
ms.date: 12/01/2016
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.openlocfilehash: c9a3aaec05fa029a8db66826bdcb4a1d106176e3
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736853"
---
# <a name="handle-null-values-in-query-expressions"></a><span data-ttu-id="cc941-103">Обработка значений NULL в выражениях запросов</span><span class="sxs-lookup"><span data-stu-id="cc941-103">Handle null values in query expressions</span></span>

<span data-ttu-id="cc941-104">В этом примере показано, как обрабатывать возможные нулевые значения в исходных коллекциях.</span><span class="sxs-lookup"><span data-stu-id="cc941-104">This example shows how to handle possible null values in source collections.</span></span> <span data-ttu-id="cc941-105">Коллекция объектов, например <xref:System.Collections.Generic.IEnumerable%601>, может содержать элементы со значением [NULL](../language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="cc941-105">An object collection such as an <xref:System.Collections.Generic.IEnumerable%601> can contain elements whose value is [null](../language-reference/keywords/null.md).</span></span> <span data-ttu-id="cc941-106">Если исходная коллекция имеет значение NULL или содержит элемент со значением NULL, а запрос не обрабатывает такие значения, при выполнении этого запроса возникает исключение <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="cc941-106">If a source collection is null or contains an element whose value is null, and your query does not handle null values, a <xref:System.NullReferenceException> will be thrown when you execute the query.</span></span>

## <a name="example"></a><span data-ttu-id="cc941-107">Пример</span><span class="sxs-lookup"><span data-stu-id="cc941-107">Example</span></span>

<span data-ttu-id="cc941-108">Чтобы избежать исключения в связи с пустой ссылкой, можно составить защитный код, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="cc941-108">You can code defensively to avoid a null reference exception as shown in the following example:</span></span>

[!code-csharp[csProgGuideLINQ#82](~/samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]

<span data-ttu-id="cc941-109">В предыдущем примере предложение `where` отфильтровывает все пустые элементы в последовательности категорий.</span><span class="sxs-lookup"><span data-stu-id="cc941-109">In the previous example, the `where` clause filters out all null elements in the categories sequence.</span></span> <span data-ttu-id="cc941-110">Этот метод не связан с проверкой на наличие пустых значений в предложении join.</span><span class="sxs-lookup"><span data-stu-id="cc941-110">This technique is independent of the null check in the join clause.</span></span> <span data-ttu-id="cc941-111">Условное выражение со значением NULL в этом примере работает, поскольку `Products.CategoryID` типа `int?` является сокращением от `Nullable<int>`.</span><span class="sxs-lookup"><span data-stu-id="cc941-111">The conditional expression with null in this example works because `Products.CategoryID` is of type `int?` which is shorthand for `Nullable<int>`.</span></span>

## <a name="example"></a><span data-ttu-id="cc941-112">Пример</span><span class="sxs-lookup"><span data-stu-id="cc941-112">Example</span></span>

<span data-ttu-id="cc941-113">Если в предложении join тип, допускающий значение NULL, имеет только один из ключей сравнения, остальные типы в выражении запроса можно привести к типу, допускающему значение NULL.</span><span class="sxs-lookup"><span data-stu-id="cc941-113">In a join clause, if only one of the comparison keys is a nullable value type, you can cast the other to a nullable type in the query expression.</span></span> <span data-ttu-id="cc941-114">В следующем примере предполагается, что `EmployeeID` — это столбец, содержащий значения типа `int?`:</span><span class="sxs-lookup"><span data-stu-id="cc941-114">In the following example, assume that `EmployeeID` is a column that contains values of type `int?`:</span></span>

[!code-csharp[csProgGuideLINQ#83](~/samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]

## <a name="see-also"></a><span data-ttu-id="cc941-115">См. также</span><span class="sxs-lookup"><span data-stu-id="cc941-115">See also</span></span>

- <xref:System.Nullable%601>
- [<span data-ttu-id="cc941-116">LINQ</span><span class="sxs-lookup"><span data-stu-id="cc941-116">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="cc941-117">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="cc941-117">Nullable value types</span></span>](../language-reference/builtin-types/nullable-value-types.md)
