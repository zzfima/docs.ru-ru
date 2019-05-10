---
title: 'LINQ to Entities: рекомендации и известные проблемы'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: acd71129-5ff0-4b4e-b266-c72cc0c53601
ms.openlocfilehash: 303e46e79786ce7f062db4a1a3ffb6c321169af8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64631286"
---
# <a name="known-issues-and-considerations-in-linq-to-entities"></a><span data-ttu-id="37712-102">LINQ to Entities: рекомендации и известные проблемы</span><span class="sxs-lookup"><span data-stu-id="37712-102">Known Issues and Considerations in LINQ to Entities</span></span>
<span data-ttu-id="37712-103">Этот раздел содержит сведения об известных проблемах, относящихся к запросам [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37712-103">This section provides information about known issues with [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries.</span></span>  
  
- [<span data-ttu-id="37712-104">Запросы LINQ, которые нельзя кэшировать</span><span class="sxs-lookup"><span data-stu-id="37712-104">LINQ Queries That cannot be Cached</span></span>](#LINQQueriesThatAreNotCached)  
  
- [<span data-ttu-id="37712-105">Потеря данных об упорядочении</span><span class="sxs-lookup"><span data-stu-id="37712-105">Ordering Information Lost</span></span>](#OrderingInfoLost)  
  
- [<span data-ttu-id="37712-106">Целые числа без знака не поддерживается</span><span class="sxs-lookup"><span data-stu-id="37712-106">Unsigned Integers Not Supported</span></span>](#UnsignedIntsUnsupported)  
  
- [<span data-ttu-id="37712-107">Ошибки преобразования типов</span><span class="sxs-lookup"><span data-stu-id="37712-107">Type Conversion Errors</span></span>](#TypeConversionErrors)  
  
- [<span data-ttu-id="37712-108">Обращение к нескалярным переменным не поддерживается</span><span class="sxs-lookup"><span data-stu-id="37712-108">Referencing Non-Scalar Variables Not Supported</span></span>](#RefNonScalarClosures)  
  
- [<span data-ttu-id="37712-109">Вложенные запросы может произойти сбой с SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="37712-109">Nested Queries May Fail with SQL Server 2000</span></span>](#NestedQueriesSQL2000)  
  
- [<span data-ttu-id="37712-110">Проецирование анонимного типа</span><span class="sxs-lookup"><span data-stu-id="37712-110">Projecting to an Anonymous Type</span></span>](#ProjectToAnonymousType)  
  
<a name="LINQQueriesThatAreNotCached"></a>   
## <a name="linq-queries-that-cannot-be-cached"></a><span data-ttu-id="37712-111">Запросы LINQ, которые нельзя кэшировать</span><span class="sxs-lookup"><span data-stu-id="37712-111">LINQ Queries That cannot be Cached</span></span>  
 <span data-ttu-id="37712-112">Начиная с .NET Framework 4.5, запросы LINQ to Entities автоматически сохраняются в кэше.</span><span class="sxs-lookup"><span data-stu-id="37712-112">Starting with .NET Framework 4.5, LINQ to Entities queries are automatically cached.</span></span> <span data-ttu-id="37712-113">Тем не менее запросы LINQ to Entities, которые применяют оператор `Enumerable.Contains` к коллекции в памяти, автоматически не кэшируются.</span><span class="sxs-lookup"><span data-stu-id="37712-113">However, LINQ to Entities queries that apply the `Enumerable.Contains` operator to in-memory collections are not automatically cached.</span></span> <span data-ttu-id="37712-114">Также в скомпилированных запросах LINQ не допускаются коллекции в памяти с параметрами.</span><span class="sxs-lookup"><span data-stu-id="37712-114">Also parameterizing in-memory collections in compiled LINQ queries is not allowed.</span></span>  
  
<a name="OrderingInfoLost"></a>   
## <a name="ordering-information-lost"></a><span data-ttu-id="37712-115">Потеря данных об упорядочении</span><span class="sxs-lookup"><span data-stu-id="37712-115">Ordering Information Lost</span></span>  
 <span data-ttu-id="37712-116">Проецирование столбцов на анонимные типы приведет к потере данных об упорядочении в некоторых запросах к базе данных [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)], для которой установлен уровень совместимости «80».</span><span class="sxs-lookup"><span data-stu-id="37712-116">Projecting columns into an anonymous type will cause ordering information to be lost in some queries that are executed against a [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)] database set to a compatibility level of "80".</span></span>  <span data-ttu-id="37712-117">Это происходит в том случае, если имя столбца в списке упорядочения соответствует имени столбца в селекторе, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="37712-117">This occurs when a column name in the order-by list matches a column name in the selector, as shown in the following example:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt543840)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt543840)]  
  
<a name="UnsignedIntsUnsupported"></a>   
## <a name="unsigned-integers-not-supported"></a><span data-ttu-id="37712-118">Целые числа без знака не поддерживаются</span><span class="sxs-lookup"><span data-stu-id="37712-118">Unsigned Integers Not Supported</span></span>  
 <span data-ttu-id="37712-119">Указание целых чисел без знака в запросах [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] не поддерживается, так как [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] не поддерживает этот тип данных.</span><span class="sxs-lookup"><span data-stu-id="37712-119">Specifying an unsigned integer type in a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query is not supported because the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] does not support unsigned integers.</span></span> <span data-ttu-id="37712-120">Если указать целое число без знака, <xref:System.ArgumentException> исключение во время преобразования выражения запроса, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="37712-120">If you specify an unsigned integer, an <xref:System.ArgumentException> exception will be thrown during the query expression translation, as shown in the following example.</span></span> <span data-ttu-id="37712-121">В этом примере производится запрос заказа с идентификатором 48000.</span><span class="sxs-lookup"><span data-stu-id="37712-121">This example queries for an order with ID 48000.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#uintasqueryparam)]
 [!code-vb[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#uintasqueryparam)]  
  
<a name="TypeConversionErrors"></a>   
## <a name="type-conversion-errors"></a><span data-ttu-id="37712-122">Ошибки преобразования типа</span><span class="sxs-lookup"><span data-stu-id="37712-122">Type Conversion Errors</span></span>  
 <span data-ttu-id="37712-123">Когда в Visual Basic свойство сопоставляется со столбцом типа данных SQL Server bit, имеющим значение 1 при помощи функции `CByte`, то возникнет исключение <xref:System.Data.SqlClient.SqlException> с сообщением «Ошибка арифметического переполнения».</span><span class="sxs-lookup"><span data-stu-id="37712-123">In Visual Basic, when a property is mapped to a column of SQL Server bit type with a value of 1 using the `CByte` function, a <xref:System.Data.SqlClient.SqlException> is thrown with an "Arithmetic overflow error" message.</span></span> <span data-ttu-id="37712-124">В следующем примере производится запрос столбца `Product.MakeFlag` в образце базы данных AdventureWorks, и при переборе результатов запроса выдается исключение.</span><span class="sxs-lookup"><span data-stu-id="37712-124">The following example queries the `Product.MakeFlag` column in the AdventureWorks sample database and an exception is thrown when the query results are iterated over.</span></span>  
  
 [!code-vb[DP L2E Conceptual Examples#SBUDT544355](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt544355)]  
  
<a name="RefNonScalarClosures"></a>   
## <a name="referencing-non-scalar-variables-not-supported"></a><span data-ttu-id="37712-125">Обращение к нескалярным переменным не поддерживается</span><span class="sxs-lookup"><span data-stu-id="37712-125">Referencing Non-Scalar Variables Not Supported</span></span>  
 <span data-ttu-id="37712-126">Обращение к нескалярным переменным, например к сущностям, в запросе не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="37712-126">Referencing a non-scalar variables, such as an entity, in a query is not supported.</span></span> <span data-ttu-id="37712-127">При выполнении такого запроса возникает исключение <xref:System.NotSupportedException> с сообщением «Невозможно создать константу типа `EntityType`.</span><span class="sxs-lookup"><span data-stu-id="37712-127">When such a query executes, a <xref:System.NotSupportedException> exception is thrown with a message that states "Unable to create a constant value of type `EntityType`.</span></span> <span data-ttu-id="37712-128">В этом контексте поддерживаются только типы-примитивы (такие как Int32, String, и Guid)».</span><span class="sxs-lookup"><span data-stu-id="37712-128">Only primitive types ('such as Int32, String, and Guid') are supported in this context."</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37712-129">Обращение к набору скалярных переменных поддерживается.</span><span class="sxs-lookup"><span data-stu-id="37712-129">Referencing a collection of scalar variables is supported.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt555877)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt555877)]  
  
<a name="NestedQueriesSQL2000"></a>   
## <a name="nested-queries-may-fail-with-sql-server-2000"></a><span data-ttu-id="37712-130">Вложенные запросы могут не работать с SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="37712-130">Nested Queries May Fail with SQL Server 2000</span></span>  
 <span data-ttu-id="37712-131">В SQL Server 2000 запросы LINQ to Entities могут не работать, если они порождают вложенные запросы Transact-SQL с тремя и более уровнями вложенности.</span><span class="sxs-lookup"><span data-stu-id="37712-131">With SQL Server 2000, LINQ to Entities queries may fail if they produce nested Transact-SQL queries that are three or more levels deep.</span></span>  
  
<a name="ProjectToAnonymousType"></a>   
## <a name="projecting-to-an-anonymous-type"></a><span data-ttu-id="37712-132">Проектирование анонимного типа</span><span class="sxs-lookup"><span data-stu-id="37712-132">Projecting to an Anonymous Type</span></span>  
 <span data-ttu-id="37712-133">Если при определении первоначального пути запроса в него включены связанные объекты с помощью метода <xref:System.Data.Objects.ObjectQuery%601.Include%2A> для <xref:System.Data.Objects.ObjectQuery%601>, а затем возвращаемые объекты анонимного типа проектировались с помощью LINQ, то объекты, указанные в методе добавления, не включаются в результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="37712-133">If you define your initial query path to include related objects by using the <xref:System.Data.Objects.ObjectQuery%601.Include%2A> method on the <xref:System.Data.Objects.ObjectQuery%601> and then use LINQ to project the returned objects to an anonymous type, the objects specified in the include method are not included in the query results.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype1)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype1)]  
  
 <span data-ttu-id="37712-134">Для получения связанных объектов не следует проектировать возвращаемые типы как анонимный тип.</span><span class="sxs-lookup"><span data-stu-id="37712-134">To get related objects, do not project returned types to an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype2)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype2)]  
  
## <a name="see-also"></a><span data-ttu-id="37712-135">См. также</span><span class="sxs-lookup"><span data-stu-id="37712-135">See also</span></span>

- [<span data-ttu-id="37712-136">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="37712-136">LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
