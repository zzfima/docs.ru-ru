---
title: Литералы NULL и вывод типов (Entity SQL)
ms.date: 03/30/2017
ms.assetid: edd56afb-af1b-4e7d-b210-cb8998143426
ms.openlocfilehash: 22b548f2fc889b20f76a41001438f75c25f99c00
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118096"
---
# <a name="null-literals-and-type-inference-entity-sql"></a><span data-ttu-id="a1785-102">Литералы NULL и вывод типов (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a1785-102">Null Literals and Type Inference (Entity SQL)</span></span>
<span data-ttu-id="a1785-103">Литералы NULL совместимы с любым типом в системе типов языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1785-103">Null literals are compatible with any type in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] type system.</span></span> <span data-ttu-id="a1785-104">Тем не менее, для типа литерала null был определен правильно [!INCLUDE[esql](../../../../../../includes/esql-md.md)] накладывает некоторые ограничения на использования литерала null.</span><span class="sxs-lookup"><span data-stu-id="a1785-104">However, for the type of a null literal to be inferred correctly, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] imposes certain constraints on where a null literal can be used.</span></span>  
  
## <a name="typed-nulls"></a><span data-ttu-id="a1785-105">Типизированные значения NULL</span><span class="sxs-lookup"><span data-stu-id="a1785-105">Typed Nulls</span></span>  
 <span data-ttu-id="a1785-106">Типизированные значения NULL могут использоваться где угодно.</span><span class="sxs-lookup"><span data-stu-id="a1785-106">Typed nulls can be used anywhere.</span></span> <span data-ttu-id="a1785-107">Для типизированных значений NULL не требуется логический вывод типа, поскольку тип уже известен.</span><span class="sxs-lookup"><span data-stu-id="a1785-107">Type inference is not required for typed nulls because the type is known.</span></span> <span data-ttu-id="a1785-108">Например, с помощью следующей конструкции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)] можно создать значение NULL типа Int16:</span><span class="sxs-lookup"><span data-stu-id="a1785-108">For example, you can construct a null of type Int16 with the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] construct:</span></span>  
  
 `(cast(null as Int16))`  
  
## <a name="free-floating-null-literals"></a><span data-ttu-id="a1785-109">Свободные литералы NULL </span><span class="sxs-lookup"><span data-stu-id="a1785-109">Free-Floating Null Literals</span></span>  
 <span data-ttu-id="a1785-110">Свободные литералы NULL используются в следующих ситуациях.</span><span class="sxs-lookup"><span data-stu-id="a1785-110">Free-floating null literals can be used in the following contexts:</span></span>  
  
-   <span data-ttu-id="a1785-111">Как аргумент выражений CAST и TREAT.</span><span class="sxs-lookup"><span data-stu-id="a1785-111">As an argument to a CAST or TREAT expression.</span></span> <span data-ttu-id="a1785-112">Это предпочтительный способ создания типизированного выражения NULL.</span><span class="sxs-lookup"><span data-stu-id="a1785-112">This is the recommended way to produce a typed null expression.</span></span>  
  
-   <span data-ttu-id="a1785-113">Как аргумент метода или функции.</span><span class="sxs-lookup"><span data-stu-id="a1785-113">As an argument to a method or a function.</span></span> <span data-ttu-id="a1785-114">Применяются стандартные правила перегрузки.</span><span class="sxs-lookup"><span data-stu-id="a1785-114">Standard overload rules apply.</span></span>  
  
-   <span data-ttu-id="a1785-115">Как один из аргументов арифметического выражения, например +, - или /.</span><span class="sxs-lookup"><span data-stu-id="a1785-115">As one of the arguments to an arithmetic expression such as +, -, or /.</span></span> <span data-ttu-id="a1785-116">Остальные аргументы не могут быть литералами NULL, иначе вывод типа будет невозможен.</span><span class="sxs-lookup"><span data-stu-id="a1785-116">The other arguments cannot be null literals, otherwise type inference is not possible.</span></span>  
  
-   <span data-ttu-id="a1785-117">Как один из аргументов логического выражения (И, ИЛИ, НЕ).</span><span class="sxs-lookup"><span data-stu-id="a1785-117">As any of the arguments to a logical expression (AND, OR, or NOT).</span></span> <span data-ttu-id="a1785-118">Все аргументы должны относиться к логическому типу.</span><span class="sxs-lookup"><span data-stu-id="a1785-118">All the arguments are known to be of type Boolean.</span></span>  
  
-   <span data-ttu-id="a1785-119">Как аргумент выражений IS NULL и IS NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="a1785-119">As the argument to an IS NULL or IS NOT NULL expression.</span></span>  
  
-   <span data-ttu-id="a1785-120">Как один из аргументов выражения LIKE.</span><span class="sxs-lookup"><span data-stu-id="a1785-120">As one or more of the arguments to a LIKE expression.</span></span> <span data-ttu-id="a1785-121">Все аргументы должны быть строками.</span><span class="sxs-lookup"><span data-stu-id="a1785-121">All arguments are expected to be strings.</span></span>  
  
-   <span data-ttu-id="a1785-122">Как один или несколько аргументов конструктора именованного типа.</span><span class="sxs-lookup"><span data-stu-id="a1785-122">As one or more of the arguments to a named-type constructor.</span></span>  
  
-   <span data-ttu-id="a1785-123">Как один или несколько аргументов конструктора мультинабора.</span><span class="sxs-lookup"><span data-stu-id="a1785-123">As one or more of the arguments to a multiset constructor.</span></span> <span data-ttu-id="a1785-124">По крайней мере один аргумент конструктора мультинабора должен быть выражением, отличным от литерала NULL.</span><span class="sxs-lookup"><span data-stu-id="a1785-124">At least one argument to the multiset constructor must be an expression that is not a null literal.</span></span>  
  
-   <span data-ttu-id="a1785-125">Как один из аргументов выражений THEN и ELSE в выражении CASE.</span><span class="sxs-lookup"><span data-stu-id="a1785-125">As one or more of the THEN or ELSE expressions in a CASE expression.</span></span> <span data-ttu-id="a1785-126">По крайней мере одно из выражений THEN или ELSE в выражении CASE должно быть отлично от литерала NULL.</span><span class="sxs-lookup"><span data-stu-id="a1785-126">At least one of the THEN or ELSE expressions in the CASE expression must be an expression other than a null literal.</span></span>  
  
 <span data-ttu-id="a1785-127">Ни в каких других ситуациях свободные литералы NULL использоваться не могут.</span><span class="sxs-lookup"><span data-stu-id="a1785-127">Free-floating null literals cannot be used in other scenarios.</span></span> <span data-ttu-id="a1785-128">Например, их нельзя использовать в качестве аргументов конструктора строки.</span><span class="sxs-lookup"><span data-stu-id="a1785-128">For example,  they cannot be used as arguments to a row constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1785-129">См. также</span><span class="sxs-lookup"><span data-stu-id="a1785-129">See also</span></span>

- [<span data-ttu-id="a1785-130">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a1785-130">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
