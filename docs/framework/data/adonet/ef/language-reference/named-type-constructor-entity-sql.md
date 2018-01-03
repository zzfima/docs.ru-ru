---
title: "Конструктор именованных типов (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ab743f3132dc15548735771b13967898b4c3f15f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="named-type-constructor-entity-sql"></a><span data-ttu-id="c4e29-102">Конструктор именованных типов (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c4e29-102">Named Type Constructor (Entity SQL)</span></span>
<span data-ttu-id="c4e29-103">Используется для создания экземпляров номинальных типов концептуальной модели, например сложных типов или типов сущностей.</span><span class="sxs-lookup"><span data-stu-id="c4e29-103">Used to create instances of conceptual model nominal types such as Entity or Complex types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4e29-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4e29-104">Syntax</span></span>  
  
```  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="c4e29-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c4e29-105">Arguments</span></span>  
 `identifier`  
 <span data-ttu-id="c4e29-106">Значение, представляющее собой простой или заключенный в кавычки идентификатор.</span><span class="sxs-lookup"><span data-stu-id="c4e29-106">Value that is a simple or quoted identifier.</span></span> <span data-ttu-id="c4e29-107">Дополнительные сведения см. в разделе [идентификаторы](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="c4e29-107">For more information see, [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)</span></span>  
  
 `expression`  
 <span data-ttu-id="c4e29-108">Атрибуты типа, которые, как предполагается, должны располагаться в таком же порядке, как и в декларации этого типа.</span><span class="sxs-lookup"><span data-stu-id="c4e29-108">Attributes of the type that are assumed to be in the same order as they appear in the declaration of the type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4e29-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c4e29-109">Return Value</span></span>  
 <span data-ttu-id="c4e29-110">Экземпляры именованных сложных типов и типов сущностей.</span><span class="sxs-lookup"><span data-stu-id="c4e29-110">Instances of named complex types and entity types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4e29-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="c4e29-111">Remarks</span></span>  
 <span data-ttu-id="c4e29-112">В следующих примерах показано, как создавать номинальные и сложные типы.</span><span class="sxs-lookup"><span data-stu-id="c4e29-112">The following examples show how to construct nominal and complex types:</span></span>  
  
 <span data-ttu-id="c4e29-113">Приведенное далее выражение создает экземпляр типа `Person` .</span><span class="sxs-lookup"><span data-stu-id="c4e29-113">The expression below creates an instance of a `Person` type:</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="c4e29-114">Приведенное далее выражение создает экземпляр сложного типа.</span><span class="sxs-lookup"><span data-stu-id="c4e29-114">The expression below creates an instance of a complex type:</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="c4e29-115">Приведенное далее выражение создает экземпляр вложенного сложного типа.</span><span class="sxs-lookup"><span data-stu-id="c4e29-115">The expression below creates an instance of a nested complex type:</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="c4e29-116">Приведенное далее выражение создает экземпляр сущности с вложенным сложным типом.</span><span class="sxs-lookup"><span data-stu-id="c4e29-116">The expression below creates an instance of an entity with a nested complex type:</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="c4e29-117">В следующем примере показано, как инициализировать свойство сложного типа значением null:`MyModel.ZipCode(‘98118’, null)`.</span><span class="sxs-lookup"><span data-stu-id="c4e29-117">The following example shows how to initialize a property of a complex type to null:`MyModel.ZipCode(‘98118’, null)`</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4e29-118">Пример</span><span class="sxs-lookup"><span data-stu-id="c4e29-118">Example</span></span>  
 <span data-ttu-id="c4e29-119">В следующем запросе Entity SQL конструктор именованного типа используется для создания экземпляра типа концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="c4e29-119">The following Entity SQL query uses the named type constructor to create an instance of a conceptual model type.</span></span> <span data-ttu-id="c4e29-120">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="c4e29-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c4e29-121">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="c4e29-121">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="c4e29-122">Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="c4e29-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="c4e29-123">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="c4e29-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NAMED_TYPE_CONSTRUCTOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#named_type_constructor)]  
  
## <a name="see-also"></a><span data-ttu-id="c4e29-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c4e29-124">See Also</span></span>  
 [<span data-ttu-id="c4e29-125">Сборка типов</span><span class="sxs-lookup"><span data-stu-id="c4e29-125">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [<span data-ttu-id="c4e29-126">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c4e29-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
