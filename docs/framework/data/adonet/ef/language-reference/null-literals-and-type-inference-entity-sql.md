---
title: Литералы NULL и вывод типов (Entity SQL)
ms.date: 03/30/2017
ms.assetid: edd56afb-af1b-4e7d-b210-cb8998143426
ms.openlocfilehash: 2499579237155ff3f7291f795bd1ce9e8a84163c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529113"
---
# <a name="null-literals-and-type-inference-entity-sql"></a><span data-ttu-id="a3c1d-102">Литералы NULL и вывод типов (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a3c1d-102">Null Literals and Type Inference (Entity SQL)</span></span>
<span data-ttu-id="a3c1d-103">Литералы NULL совместимы с любым типом в системе типов языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3c1d-103">Null literals are compatible with any type in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] type system.</span></span> <span data-ttu-id="a3c1d-104">Тем не менее, для типа литерала null был определен правильно [!INCLUDE[esql](../../../../../../includes/esql-md.md)] накладывает некоторые ограничения на использования литерала null.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-104">However, for the type of a null literal to be inferred correctly, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] imposes certain constraints on where a null literal can be used.</span></span>  
  
## <a name="typed-nulls"></a><span data-ttu-id="a3c1d-105">Типизированные значения NULL</span><span class="sxs-lookup"><span data-stu-id="a3c1d-105">Typed Nulls</span></span>  
 <span data-ttu-id="a3c1d-106">Типизированные значения NULL могут использоваться где угодно.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-106">Typed nulls can be used anywhere.</span></span> <span data-ttu-id="a3c1d-107">Для типизированных значений NULL не требуется логический вывод типа, поскольку тип уже известен.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-107">Type inference is not required for typed nulls because the type is known.</span></span> <span data-ttu-id="a3c1d-108">Например, с помощью следующей конструкции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)] можно создать значение NULL типа Int16:</span><span class="sxs-lookup"><span data-stu-id="a3c1d-108">For example, you can construct a null of type Int16 with the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] construct:</span></span>  
  
 `(cast(null as Int16))`  
  
## <a name="free-floating-null-literals"></a><span data-ttu-id="a3c1d-109">Свободные литералы NULL </span><span class="sxs-lookup"><span data-stu-id="a3c1d-109">Free-Floating Null Literals</span></span>  
 <span data-ttu-id="a3c1d-110">Свободные литералы NULL используются в следующих ситуациях.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-110">Free-floating null literals can be used in the following contexts:</span></span>  
  
-   <span data-ttu-id="a3c1d-111">Как аргумент выражений CAST и TREAT.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-111">As an argument to a CAST or TREAT expression.</span></span> <span data-ttu-id="a3c1d-112">Это предпочтительный способ создания типизированного выражения NULL.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-112">This is the recommended way to produce a typed null expression.</span></span>  
  
-   <span data-ttu-id="a3c1d-113">Как аргумент метода или функции.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-113">As an argument to a method or a function.</span></span> <span data-ttu-id="a3c1d-114">Применяются стандартные правила перегрузки.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-114">Standard overload rules apply.</span></span>  
  
-   <span data-ttu-id="a3c1d-115">Как один из аргументов арифметического выражения, например +, - или /.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-115">As one of the arguments to an arithmetic expression such as +, -, or /.</span></span> <span data-ttu-id="a3c1d-116">Остальные аргументы не могут быть литералами NULL, иначе вывод типа будет невозможен.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-116">The other arguments cannot be null literals, otherwise type inference is not possible.</span></span>  
  
-   <span data-ttu-id="a3c1d-117">Как один из аргументов логического выражения (И, ИЛИ, НЕ).</span><span class="sxs-lookup"><span data-stu-id="a3c1d-117">As any of the arguments to a logical expression (AND, OR, or NOT).</span></span> <span data-ttu-id="a3c1d-118">Все аргументы должны относиться к логическому типу.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-118">All the arguments are known to be of type Boolean.</span></span>  
  
-   <span data-ttu-id="a3c1d-119">Как аргумент выражений IS NULL и IS NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-119">As the argument to an IS NULL or IS NOT NULL expression.</span></span>  
  
-   <span data-ttu-id="a3c1d-120">Как один из аргументов выражения LIKE.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-120">As one or more of the arguments to a LIKE expression.</span></span> <span data-ttu-id="a3c1d-121">Все аргументы должны быть строками.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-121">All arguments are expected to be strings.</span></span>  
  
-   <span data-ttu-id="a3c1d-122">Как один или несколько аргументов конструктора именованного типа.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-122">As one or more of the arguments to a named-type constructor.</span></span>  
  
-   <span data-ttu-id="a3c1d-123">Как один или несколько аргументов конструктора мультинабора.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-123">As one or more of the arguments to a multiset constructor.</span></span> <span data-ttu-id="a3c1d-124">По крайней мере один аргумент конструктора мультинабора должен быть выражением, отличным от литерала NULL.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-124">At least one argument to the multiset constructor must be an expression that is not a null literal.</span></span>  
  
-   <span data-ttu-id="a3c1d-125">Как один из аргументов выражений THEN и ELSE в выражении CASE.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-125">As one or more of the THEN or ELSE expressions in a CASE expression.</span></span> <span data-ttu-id="a3c1d-126">По крайней мере одно из выражений THEN или ELSE в выражении CASE должно быть отлично от литерала NULL.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-126">At least one of the THEN or ELSE expressions in the CASE expression must be an expression other than a null literal.</span></span>  
  
 <span data-ttu-id="a3c1d-127">Ни в каких других ситуациях свободные литералы NULL использоваться не могут.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-127">Free-floating null literals cannot be used in other scenarios.</span></span> <span data-ttu-id="a3c1d-128">Например, их нельзя использовать в качестве аргументов конструктора строки.</span><span class="sxs-lookup"><span data-stu-id="a3c1d-128">For example,  they cannot be used as arguments to a row constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c1d-129">См. также</span><span class="sxs-lookup"><span data-stu-id="a3c1d-129">See also</span></span>
- [<span data-ttu-id="a3c1d-130">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a3c1d-130">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
