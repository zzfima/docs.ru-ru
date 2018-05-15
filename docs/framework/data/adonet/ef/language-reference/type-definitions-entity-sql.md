---
title: Определения типов (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 306b204a-ade5-47ef-95b5-c785d2da4a7e
ms.openlocfilehash: 7abbe5dfed005a10955a385cadf12725a9450512
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="type-definitions-entity-sql"></a><span data-ttu-id="1f1a0-102">Определения типов (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1f1a0-102">Type Definitions (Entity SQL)</span></span>
<span data-ttu-id="1f1a0-103">Определение типа используется в операторе объявления встроенной функции [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f1a0-103">A type definition is used in the declaration statement of an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Inline function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f1a0-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f1a0-104">Remarks</span></span>  
 <span data-ttu-id="1f1a0-105">В операторе объявления для встроенной функции состоит из [ФУНКЦИЯ](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) ключевое слово и идентификатор, представляющий имя функции (например, «MyAvg»), следуют в списке определений параметров в скобки (для Пример «dues Collection(Decimal)").</span><span class="sxs-lookup"><span data-stu-id="1f1a0-105">The declaration statement for an inline function consists of the [FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) keyword followed by the identifier representing the function name (for example, "MyAvg") followed by a parameter definition list in parenthesis (for example, "dues Collection(Decimal)").</span></span>  
  
 <span data-ttu-id="1f1a0-106">Список определений параметров содержит ноль или более определений параметров.</span><span class="sxs-lookup"><span data-stu-id="1f1a0-106">The parameter definition list consists of zero or more parameter definitions.</span></span> <span data-ttu-id="1f1a0-107">Каждое определение параметра состоит из идентификатора (имя параметра для функции, например «dues»), за которым следует определение типа (например, «Collection(Decimal)»).</span><span class="sxs-lookup"><span data-stu-id="1f1a0-107">Each parameter definition consists of an identifier (the name of the parameter to the function, for example, "dues") followed by a type definition (for example, "Collection(Decimal)").</span></span>  
  
 <span data-ttu-id="1f1a0-108">Определения типов могут представлять:</span><span class="sxs-lookup"><span data-stu-id="1f1a0-108">The type definitions can be either:</span></span>  
  
-   <span data-ttu-id="1f1a0-109">Тип идентификатора (например, «Int32» или «AdventureWorks.Order»).</span><span class="sxs-lookup"><span data-stu-id="1f1a0-109">The type of the identifier (for example, "Int32" or "AdventureWorks.Order").</span></span>  
  
-   <span data-ttu-id="1f1a0-110">Ключевое слово `COLLECTION`, за которым следует определение другого типа в скобках (например, «Collection(AdventureWorks.Order)»).</span><span class="sxs-lookup"><span data-stu-id="1f1a0-110">The keyword `COLLECTION` followed by another type definition in parenthesis (for example, "Collection(AdventureWorks.Order)").</span></span>  
  
-   <span data-ttu-id="1f1a0-111">Ключевое слово ROW, за которым следует список определений свойств в скобках (например, «Row(x AdventureWorks.Order)»).</span><span class="sxs-lookup"><span data-stu-id="1f1a0-111">The keyword ROW followed by a list of property definitions in parenthesis (for example, "Row(x AdventureWorks.Order)").</span></span> <span data-ttu-id="1f1a0-112">Определения свойств имеют формат, например «`identifier type_definition`, `identifier type_definition`,...».</span><span class="sxs-lookup"><span data-stu-id="1f1a0-112">Property definitions have a format such as "`identifier type_definition`, `identifier type_definition`, ...".</span></span>  
  
-   <span data-ttu-id="1f1a0-113">Ключевое слово REF, за которым следует тип идентификатора в скобках (например, «Ref(AdventureWorks.Order)»).</span><span class="sxs-lookup"><span data-stu-id="1f1a0-113">The keyword REF followed by the type of the identifier in parenthesis (for example, "Ref(AdventureWorks.Order)").</span></span> <span data-ttu-id="1f1a0-114">Для оператора определения типа REF требуется присутствие типа сущности в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="1f1a0-114">The REF type definition operator requires an entity type as the argument.</span></span> <span data-ttu-id="1f1a0-115">В качестве аргумента нельзя указать тип-примитив.</span><span class="sxs-lookup"><span data-stu-id="1f1a0-115">You cannot specify a primitive type as the argument.</span></span>  
  
 <span data-ttu-id="1f1a0-116">Определения типов также можно вкладывать друг в друга (например, «Collection(Row(x Ref(AdventureWorks.Order)))»).</span><span class="sxs-lookup"><span data-stu-id="1f1a0-116">You can also nest type definitions (for example, "Collection(Row(x Ref(AdventureWorks.Order)))").</span></span>  
  
 <span data-ttu-id="1f1a0-117">Определения типов имеют следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="1f1a0-117">The type definition options are:</span></span>  
  
-   <span data-ttu-id="1f1a0-118">`IdentifierName supported_type`или</span><span class="sxs-lookup"><span data-stu-id="1f1a0-118">`IdentifierName supported_type`, or</span></span>  
  
-   <span data-ttu-id="1f1a0-119">`IdentifierName` COLLECTION(`type_definition`), или</span><span class="sxs-lookup"><span data-stu-id="1f1a0-119">`IdentifierName` COLLECTION(`type_definition`), or</span></span>  
  
-   <span data-ttu-id="1f1a0-120">`IdentifierName` ROW(`property_definition`), или</span><span class="sxs-lookup"><span data-stu-id="1f1a0-120">`IdentifierName` ROW(`property_definition`), or</span></span>  
  
-   <span data-ttu-id="1f1a0-121">`IdentifierName` REF(`supported_entity_type`)</span><span class="sxs-lookup"><span data-stu-id="1f1a0-121">`IdentifierName` REF(`supported_entity_type`)</span></span>  
  
 <span data-ttu-id="1f1a0-122">Параметр, определяющий свойство, - `IdentifierName type_definition`.</span><span class="sxs-lookup"><span data-stu-id="1f1a0-122">The property definition option is `IdentifierName type_definition`.</span></span>  
  
 <span data-ttu-id="1f1a0-123">Поддерживаются все типы в текущем пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="1f1a0-123">Supported types are any types in the current namespace.</span></span> <span data-ttu-id="1f1a0-124">Включаются как типы-примитивы, так и типы сущностей.</span><span class="sxs-lookup"><span data-stu-id="1f1a0-124">These include both primitive and entity types.</span></span>  
  
 <span data-ttu-id="1f1a0-125">В поддерживаемые типы сущностей входят только типы сущностей текущего пространства имен.</span><span class="sxs-lookup"><span data-stu-id="1f1a0-125">Supported entity types refer to only entity types in the current namespace.</span></span> <span data-ttu-id="1f1a0-126">Сюда не входят типы-примитивы.</span><span class="sxs-lookup"><span data-stu-id="1f1a0-126">They do not include primitive types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1f1a0-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="1f1a0-127">Examples</span></span>  
 <span data-ttu-id="1f1a0-128">Ниже приводится пример простого определения типа.</span><span class="sxs-lookup"><span data-stu-id="1f1a0-128">The following is an example of a simple type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 EDM.Decimal) AS (  
   Round(p1)  
)  
MyRound(CAST(1.7 as EDM.Decimal))  
```  
  
 <span data-ttu-id="1f1a0-129">Ниже приводится пример определения типа COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="1f1a0-129">The following is an example of a COLLECTION type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Collection(EDM.Decimal)) AS (  
   Select Round(p1) from p1  
)  
MyRound({CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)})  
```  
  
 <span data-ttu-id="1f1a0-130">Ниже приводится пример определения типа ROW.</span><span class="sxs-lookup"><span data-stu-id="1f1a0-130">The following is an example of a ROW type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Row(x EDM.Decimal)) AS (  
   Round(p1.x)  
)  
select MyRound(row(a as x)) from {CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)} as a  
```  
  
 <span data-ttu-id="1f1a0-131">Ниже приводится пример определения типа REF.</span><span class="sxs-lookup"><span data-stu-id="1f1a0-131">The following is an example of a REF type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function UnReference(p1 Ref(AdventureWorks.Order)) AS (  
   Deref(p1)  
)  
select Ref(x) from AdventureWorksEntities.SalesOrderHeaders as x  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f1a0-132">См. также</span><span class="sxs-lookup"><span data-stu-id="1f1a0-132">See Also</span></span>  
 [<span data-ttu-id="1f1a0-133">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1f1a0-133">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="1f1a0-134">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1f1a0-134">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
