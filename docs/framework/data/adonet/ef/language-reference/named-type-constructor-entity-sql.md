---
title: Конструктор именованных типов (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: f95f0dcb92068675b2efff0af7e97b349976bf42
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59329470"
---
# <a name="named-type-constructor-entity-sql"></a><span data-ttu-id="e9c01-102">Конструктор именованных типов (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e9c01-102">Named Type Constructor (Entity SQL)</span></span>
<span data-ttu-id="e9c01-103">Используется для создания экземпляров номинальных типов концептуальной модели, например сложных типов или типов сущностей.</span><span class="sxs-lookup"><span data-stu-id="e9c01-103">Used to create instances of conceptual model nominal types such as Entity or Complex types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9c01-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9c01-104">Syntax</span></span>  
  
```  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="e9c01-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e9c01-105">Arguments</span></span>  
 `identifier`  
 <span data-ttu-id="e9c01-106">Значение, представляющее собой простой или заключенный в кавычки идентификатор.</span><span class="sxs-lookup"><span data-stu-id="e9c01-106">Value that is a simple or quoted identifier.</span></span> <span data-ttu-id="e9c01-107">Дополнительные сведения см. [идентификаторы](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="e9c01-107">For more information see, [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)</span></span>  
  
 `expression`  
 <span data-ttu-id="e9c01-108">Атрибуты типа, которые, как предполагается, должны располагаться в таком же порядке, как и в декларации этого типа.</span><span class="sxs-lookup"><span data-stu-id="e9c01-108">Attributes of the type that are assumed to be in the same order as they appear in the declaration of the type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9c01-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e9c01-109">Return Value</span></span>  
 <span data-ttu-id="e9c01-110">Экземпляры именованных сложных типов и типов сущностей.</span><span class="sxs-lookup"><span data-stu-id="e9c01-110">Instances of named complex types and entity types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9c01-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="e9c01-111">Remarks</span></span>  
 <span data-ttu-id="e9c01-112">В следующих примерах показано, как создавать номинальные и сложные типы.</span><span class="sxs-lookup"><span data-stu-id="e9c01-112">The following examples show how to construct nominal and complex types:</span></span>  
  
 <span data-ttu-id="e9c01-113">Приведенное далее выражение создает экземпляр типа `Person` .</span><span class="sxs-lookup"><span data-stu-id="e9c01-113">The expression below creates an instance of a `Person` type:</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="e9c01-114">Приведенное далее выражение создает экземпляр сложного типа.</span><span class="sxs-lookup"><span data-stu-id="e9c01-114">The expression below creates an instance of a complex type:</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="e9c01-115">Приведенное далее выражение создает экземпляр вложенного сложного типа.</span><span class="sxs-lookup"><span data-stu-id="e9c01-115">The expression below creates an instance of a nested complex type:</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="e9c01-116">Приведенное далее выражение создает экземпляр сущности с вложенным сложным типом.</span><span class="sxs-lookup"><span data-stu-id="e9c01-116">The expression below creates an instance of an entity with a nested complex type:</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="e9c01-117">В следующем примере показано, как инициализировать свойство сложного типа значением null:`MyModel.ZipCode(‘98118’, null)`.</span><span class="sxs-lookup"><span data-stu-id="e9c01-117">The following example shows how to initialize a property of a complex type to null:`MyModel.ZipCode(‘98118’, null)`</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9c01-118">Пример</span><span class="sxs-lookup"><span data-stu-id="e9c01-118">Example</span></span>  
 <span data-ttu-id="e9c01-119">В следующем запросе Entity SQL конструктор именованного типа используется для создания экземпляра типа концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="e9c01-119">The following Entity SQL query uses the named type constructor to create an instance of a conceptual model type.</span></span> <span data-ttu-id="e9c01-120">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="e9c01-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e9c01-121">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="e9c01-121">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="e9c01-122">Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e9c01-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="e9c01-123">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="e9c01-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NAMED_TYPE_CONSTRUCTOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#named_type_constructor)]  
  
## <a name="see-also"></a><span data-ttu-id="e9c01-124">См. также</span><span class="sxs-lookup"><span data-stu-id="e9c01-124">See also</span></span>

- [<span data-ttu-id="e9c01-125">Сборка типов</span><span class="sxs-lookup"><span data-stu-id="e9c01-125">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)
- [<span data-ttu-id="e9c01-126">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e9c01-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
