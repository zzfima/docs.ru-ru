---
title: "Обработка значений NULL в выражениях запросов"
description: "Практическое руководство. Обработка значений NULL в выражениях запросов"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.openlocfilehash: d16256e31b073a599504ffef6501ed34430a7694
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="handle-null-values-in-query-expressions"></a><span data-ttu-id="91c20-104">Обработка значений NULL в выражениях запросов</span><span class="sxs-lookup"><span data-stu-id="91c20-104">Handle null values in query expressions</span></span>

<span data-ttu-id="91c20-105">В этом примере показано, как обрабатывать возможные нулевые значения в исходных коллекциях.</span><span class="sxs-lookup"><span data-stu-id="91c20-105">This example shows how to handle possible null values in source collections.</span></span> <span data-ttu-id="91c20-106">Коллекция объектов, например <xref:System.Collections.Generic.IEnumerable%601>, может содержать элементы со значением [NULL](../language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="91c20-106">An object collection such as an <xref:System.Collections.Generic.IEnumerable%601> can contain elements whose value is [null](../language-reference/keywords/null.md).</span></span> <span data-ttu-id="91c20-107">Если исходная коллекция имеет значение NULL или содержит элемент со значением NULL, а запрос не обрабатывает такие значения, при выполнении этого запроса возникает исключение <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="91c20-107">If a source collection is null or contains an element whose value is null, and your query does not handle null values, a <xref:System.NullReferenceException> will be thrown when you execute the query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91c20-108">Пример</span><span class="sxs-lookup"><span data-stu-id="91c20-108">Example</span></span>

 <span data-ttu-id="91c20-109">Чтобы избежать исключения в связи с пустой ссылкой, можно составить защитный код, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="91c20-109">You can code defensively to avoid a null reference exception as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#82](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]  
  
 <span data-ttu-id="91c20-110">В предыдущем примере предложение `where` отфильтровывает все пустые элементы в последовательности категорий.</span><span class="sxs-lookup"><span data-stu-id="91c20-110">In the previous example, the `where` clause filters out all null elements in the categories sequence.</span></span> <span data-ttu-id="91c20-111">Этот метод не связан с проверкой на наличие пустых значений в предложении join.</span><span class="sxs-lookup"><span data-stu-id="91c20-111">This technique is independent of the null check in the join clause.</span></span> <span data-ttu-id="91c20-112">Условное выражение со значением NULL в этом примере работает, поскольку `Products.CategoryID` типа `int?` является сокращением от `Nullable<int>`.</span><span class="sxs-lookup"><span data-stu-id="91c20-112">The conditional expression with null in this example works because `Products.CategoryID` is of type `int?` which is shorthand for `Nullable<int>`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91c20-113">Пример</span><span class="sxs-lookup"><span data-stu-id="91c20-113">Example</span></span>

 <span data-ttu-id="91c20-114">Если в предложении join тип, допускающий значение NULL, имеет только один из ключей сравнения, остальные типы в выражении запроса можно привести к типу, допускающему значение NULL.</span><span class="sxs-lookup"><span data-stu-id="91c20-114">In a join clause, if only one of the comparison keys is a nullable value type, you can cast the other to a nullable type in the query expression.</span></span> <span data-ttu-id="91c20-115">В следующем примере предполагается, что `EmployeeID` — это столбец, содержащий значения типа `int?`:</span><span class="sxs-lookup"><span data-stu-id="91c20-115">In the following example, assume that `EmployeeID` is a column that contains values of type `int?`:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#83](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="91c20-116">См. также</span><span class="sxs-lookup"><span data-stu-id="91c20-116">See also</span></span>  
 <xref:System.Nullable%601>  
 [<span data-ttu-id="91c20-117">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="91c20-117">LINQ query expressions</span></span>](index.md)  
 [<span data-ttu-id="91c20-118">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="91c20-118">Nullable types</span></span>](../programming-guide/nullable-types/index.md)
