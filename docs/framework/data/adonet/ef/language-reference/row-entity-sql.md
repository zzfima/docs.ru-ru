---
title: ROW (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 06da96e8-55d7-486c-991a-4e514d837ff9
ms.openlocfilehash: dfd0031f49cbdf41797cecf21c149fafde4d7a8c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249253"
---
# <a name="row-entity-sql"></a><span data-ttu-id="88fc7-102">ROW (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="88fc7-102">ROW (Entity SQL)</span></span>
<span data-ttu-id="88fc7-103">Создает анонимные структурно типизированные записи из одного или нескольких значений.</span><span class="sxs-lookup"><span data-stu-id="88fc7-103">Constructs anonymous, structurally typed records from one or more values.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88fc7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88fc7-104">Syntax</span></span>  
  
```  
ROW ( expression [ AS alias ] [,...] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="88fc7-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="88fc7-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="88fc7-106">Любое допустимое выражение запроса, которое возвращает значение для создания в типе строки.</span><span class="sxs-lookup"><span data-stu-id="88fc7-106">Any valid query expression that returns a value to construct in a row type.</span></span>  
  
 `alias`  
 <span data-ttu-id="88fc7-107">Определяет псевдоним для значения, указанного в типе строки.</span><span class="sxs-lookup"><span data-stu-id="88fc7-107">Specifies an alias for the value specified in a row type.</span></span> <span data-ttu-id="88fc7-108">Если псевдоним не указан, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] пытается сформировать его на основе правил создания псевдонимов [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="88fc7-108">If an alias is not provided, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to generate an alias based on the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] alias generation rules.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88fc7-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="88fc7-109">Return Value</span></span>  
 <span data-ttu-id="88fc7-110">Тип строки.</span><span class="sxs-lookup"><span data-stu-id="88fc7-110">A row type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88fc7-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="88fc7-111">Remarks</span></span>  
 <span data-ttu-id="88fc7-112">В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] конструкторы строк можно использовать для создания анонимных структурно типизированных записей из одного или нескольких значений.</span><span class="sxs-lookup"><span data-stu-id="88fc7-112">You use row constructors in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to construct anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="88fc7-113">Итоговый тип конструктора строк является типом строки, типы полей которого соответствуют типам значений, которые использовались для создания этой строки.</span><span class="sxs-lookup"><span data-stu-id="88fc7-113">The result type of a row constructor is a row type whose field types correspond to the types of the values that were used to construct the row.</span></span> <span data-ttu-id="88fc7-114">Например, следующее выражение создает значение типа `Record(a int, b string, c int)`.</span><span class="sxs-lookup"><span data-stu-id="88fc7-114">For example, the following expression constructs a value of type `Record(a int, b string, c int)`.</span></span>  
  
```  
ROW(1 AS a, "abc" AS b, a+34 AS c)  
```  
  
 <span data-ttu-id="88fc7-115">Если в конструкторе строк не указан псевдоним для выражения, то платформа Entity Framework попытается сформировать его.</span><span class="sxs-lookup"><span data-stu-id="88fc7-115">If you do not provide an alias for an expression in a row constructor, the Entity Framework will try to generate one.</span></span> <span data-ttu-id="88fc7-116">Дополнительные сведения см. в разделе «Правила присвоения псевдонимов» темы [Идентификаторы](identifiers-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="88fc7-116">For more information, see the "Aliasing Rules" section of the [Identifiers](identifiers-entity-sql.md) topic.</span></span>  
  
 <span data-ttu-id="88fc7-117">В конструкторе строк псевдонимы присваиваются выражениям по следующим правилам.</span><span class="sxs-lookup"><span data-stu-id="88fc7-117">The following rules apply to expression aliasing in a row constructor:</span></span>  
  
- <span data-ttu-id="88fc7-118">Выражение в конструкторе строк не может ссылаться на другие псевдонимы в этом же конструкторе.</span><span class="sxs-lookup"><span data-stu-id="88fc7-118">Expressions in a row constructor cannot refer to other aliases in the same constructor.</span></span>  
  
- <span data-ttu-id="88fc7-119">Два выражения в одном конструкторе строк не могут иметь одинаковый псевдоним.</span><span class="sxs-lookup"><span data-stu-id="88fc7-119">Two expressions in the same row constructor cannot have the same alias.</span></span>  
  
 <span data-ttu-id="88fc7-120">Дополнительные сведения о конструкторах запросов см. в разделе [Создание типов](constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="88fc7-120">For more information about query constructors, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="88fc7-121">Пример</span><span class="sxs-lookup"><span data-stu-id="88fc7-121">Example</span></span>  
 <span data-ttu-id="88fc7-122">В следующем запросе Entity SQL оператор ROW используется для создания анонимных структурно типизированных записей.</span><span class="sxs-lookup"><span data-stu-id="88fc7-122">The following Entity SQL query uses the ROW operator to construct anonymous, structurally typed records.</span></span> <span data-ttu-id="88fc7-123">Запрос основан на модели AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="88fc7-123">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="88fc7-124">Для компиляции и запуска этого запроса выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="88fc7-124">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="88fc7-125">Выполните процедуру, описанную в [разделе инструкции. Выполнение запроса, возвращающего Структуралтипе](../how-to-execute-a-query-that-returns-structuraltype-results.md)результаты.</span><span class="sxs-lookup"><span data-stu-id="88fc7-125">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="88fc7-126">Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="88fc7-126">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ROW](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#row)]  
  
## <a name="see-also"></a><span data-ttu-id="88fc7-127">См. также</span><span class="sxs-lookup"><span data-stu-id="88fc7-127">See also</span></span>

- [<span data-ttu-id="88fc7-128">Сборка типов</span><span class="sxs-lookup"><span data-stu-id="88fc7-128">Constructing Types</span></span>](constructing-types-entity-sql.md)
- [<span data-ttu-id="88fc7-129">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="88fc7-129">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="88fc7-130">Определения типов</span><span class="sxs-lookup"><span data-stu-id="88fc7-130">Type Definitions</span></span>](type-definitions-entity-sql.md)
