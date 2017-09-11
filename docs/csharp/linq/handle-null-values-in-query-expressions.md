---
title: "Обработка значений NULL в выражениях запросов"
description: "Практическое руководство. Обработка значений NULL в выражениях запросов"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f4f189504c57c9c01268b10bc96ad3c9af49ddbd
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="handle-null-values-in-query-expressions"></a><span data-ttu-id="00b33-104">Обработка значений NULL в выражениях запросов</span><span class="sxs-lookup"><span data-stu-id="00b33-104">Handle null values in query expressions</span></span>

<span data-ttu-id="00b33-105">В этом примере показано, как обрабатывать возможные нулевые значения в исходных коллекциях.</span><span class="sxs-lookup"><span data-stu-id="00b33-105">This example shows how to handle possible null values in source collections.</span></span> <span data-ttu-id="00b33-106">Коллекция объектов, например <xref:System.Collections.Generic.IEnumerable%601>, может содержать элементы со значением [NULL](../language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="00b33-106">An object collection such as an <xref:System.Collections.Generic.IEnumerable%601> can contain elements whose value is [null](../language-reference/keywords/null.md).</span></span> <span data-ttu-id="00b33-107">Если исходная коллекция имеет значение NULL или содержит элемент со значением NULL, а запрос не обрабатывает такие значения, при выполнении этого запроса возникает исключение <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="00b33-107">If a source collection is null or contains an element whose value is null, and your query does not handle null values, a <xref:System.NullReferenceException> will be thrown when you execute the query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00b33-108">Пример</span><span class="sxs-lookup"><span data-stu-id="00b33-108">Example</span></span>

 <span data-ttu-id="00b33-109">Чтобы избежать исключения в связи с пустой ссылкой, можно составить защитный код, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="00b33-109">You can code defensively to avoid a null reference exception as shown in the following example:</span></span>  
  
 <span data-ttu-id="00b33-110">[!code-cs[csProgGuideLINQ#82](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="00b33-110">[!code-cs[csProgGuideLINQ#82](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]</span></span>  
  
 <span data-ttu-id="00b33-111">В предыдущем примере предложение `where` отфильтровывает все пустые элементы в последовательности категорий.</span><span class="sxs-lookup"><span data-stu-id="00b33-111">In the previous example, the `where` clause filters out all null elements in the categories sequence.</span></span> <span data-ttu-id="00b33-112">Этот метод не связан с проверкой на наличие пустых значений в предложении join.</span><span class="sxs-lookup"><span data-stu-id="00b33-112">This technique is independent of the null check in the join clause.</span></span> <span data-ttu-id="00b33-113">Условное выражение со значением NULL в этом примере работает, поскольку `Products.CategoryID` типа `int?` является сокращением от `Nullable<int>`.</span><span class="sxs-lookup"><span data-stu-id="00b33-113">The conditional expression with null in this example works because `Products.CategoryID` is of type `int?` which is shorthand for `Nullable<int>`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00b33-114">Пример</span><span class="sxs-lookup"><span data-stu-id="00b33-114">Example</span></span>

 <span data-ttu-id="00b33-115">Если в предложении join тип, допускающий значение NULL, имеет только один из ключей сравнения, остальные типы в выражении запроса можно привести к типу, допускающему значение NULL.</span><span class="sxs-lookup"><span data-stu-id="00b33-115">In a join clause, if only one of the comparison keys is a nullable value type, you can cast the other to a nullable type in the query expression.</span></span> <span data-ttu-id="00b33-116">В следующем примере предполагается, что `EmployeeID` — это столбец, содержащий значения типа `int?`:</span><span class="sxs-lookup"><span data-stu-id="00b33-116">In the following example, assume that `EmployeeID` is a column that contains values of type `int?`:</span></span>  
  
 <span data-ttu-id="00b33-117">[!code-cs[csProgGuideLINQ#83](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="00b33-117">[!code-cs[csProgGuideLINQ#83](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00b33-118">См. также</span><span class="sxs-lookup"><span data-stu-id="00b33-118">See also</span></span>  
 <span data-ttu-id="00b33-119"><xref:System.Nullable%601></span><span class="sxs-lookup"><span data-stu-id="00b33-119"><xref:System.Nullable%601></span></span>   
 <span data-ttu-id="00b33-120">[Выражения запросов LINQ](index.md) </span><span class="sxs-lookup"><span data-stu-id="00b33-120">[LINQ query expressions](index.md) </span></span>  
 [<span data-ttu-id="00b33-121">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="00b33-121">Nullable types</span></span>](../programming-guide/nullable-types/index.md)

