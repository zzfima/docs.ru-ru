---
title: Приоритет операторов (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: 722ebe5f0ec530f8c7f86e9f9901451b060903f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159137"
---
# <a name="operator-precedence-entity-sql"></a><span data-ttu-id="14b54-102">Приоритет операторов (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="14b54-102">Operator Precedence (Entity SQL)</span></span>
<span data-ttu-id="14b54-103">Когда [!INCLUDE[esql](../../../../../../includes/esql-md.md)] запроса содержит несколько операторов, порядок применения операторов определяет последовательность, в которой выполняются операции.</span><span class="sxs-lookup"><span data-stu-id="14b54-103">When an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query has multiple operators, operator precedence determines the sequence in which the operations are performed.</span></span> <span data-ttu-id="14b54-104">Порядок выполнения может существенно повлиять на результат выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="14b54-104">The order of execution can significantly affect the query result.</span></span>  
  
 <span data-ttu-id="14b54-105">Уровни приоритета операторов показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="14b54-105">Operators have the precedence levels shown in the following table.</span></span> <span data-ttu-id="14b54-106">Оператор с более высоким уровнем выполняется раньше оператора с более низким уровнем.</span><span class="sxs-lookup"><span data-stu-id="14b54-106">An operator with a higher level is evaluated before an operator with a lower level.</span></span>  
  
|<span data-ttu-id="14b54-107">Уровень</span><span class="sxs-lookup"><span data-stu-id="14b54-107">Level</span></span>|<span data-ttu-id="14b54-108">Тип операции</span><span class="sxs-lookup"><span data-stu-id="14b54-108">Operation type</span></span>|<span data-ttu-id="14b54-109">Оператор</span><span class="sxs-lookup"><span data-stu-id="14b54-109">Operator</span></span>|  
|-----------|--------------------|--------------|  
|<span data-ttu-id="14b54-110">1</span><span class="sxs-lookup"><span data-stu-id="14b54-110">1</span></span>|<span data-ttu-id="14b54-111">Первичный</span><span class="sxs-lookup"><span data-stu-id="14b54-111">Primary</span></span>|`. , [] ()`|  
|<span data-ttu-id="14b54-112">2</span><span class="sxs-lookup"><span data-stu-id="14b54-112">2</span></span>|<span data-ttu-id="14b54-113">Унарный</span><span class="sxs-lookup"><span data-stu-id="14b54-113">Unary</span></span>|`! not`|  
|<span data-ttu-id="14b54-114">3</span><span class="sxs-lookup"><span data-stu-id="14b54-114">3</span></span>|<span data-ttu-id="14b54-115">Мультипликативный</span><span class="sxs-lookup"><span data-stu-id="14b54-115">Multiplicative</span></span>|`* / %`|  
|<span data-ttu-id="14b54-116">4</span><span class="sxs-lookup"><span data-stu-id="14b54-116">4</span></span>|<span data-ttu-id="14b54-117">Аддитивный</span><span class="sxs-lookup"><span data-stu-id="14b54-117">Additive</span></span>|`+ -`|  
|<span data-ttu-id="14b54-118">5</span><span class="sxs-lookup"><span data-stu-id="14b54-118">5</span></span>|<span data-ttu-id="14b54-119">Упорядочение</span><span class="sxs-lookup"><span data-stu-id="14b54-119">Ordering</span></span>|`< > <= >=`|  
|<span data-ttu-id="14b54-120">6</span><span class="sxs-lookup"><span data-stu-id="14b54-120">6</span></span>|<span data-ttu-id="14b54-121">Равенство</span><span class="sxs-lookup"><span data-stu-id="14b54-121">Equality</span></span>|`= != <>`|  
|<span data-ttu-id="14b54-122">7</span><span class="sxs-lookup"><span data-stu-id="14b54-122">7</span></span>|<span data-ttu-id="14b54-123">Условное И</span><span class="sxs-lookup"><span data-stu-id="14b54-123">Conditional AND</span></span>|`and &&`|  
|<span data-ttu-id="14b54-124">8</span><span class="sxs-lookup"><span data-stu-id="14b54-124">8</span></span>|<span data-ttu-id="14b54-125">Условное ИЛИ</span><span class="sxs-lookup"><span data-stu-id="14b54-125">Conditional OR</span></span>|`or &#124;&#124;`|  
  
 <span data-ttu-id="14b54-126">Если два оператора в выражении имеют один и тот же уровень приоритета, они выполняются в порядке слева направо по мере их появления в выражении.</span><span class="sxs-lookup"><span data-stu-id="14b54-126">When two operators in an expression have the same operator precedence level, they are evaluated left to right, based on their position in the query.</span></span> <span data-ttu-id="14b54-127">Например, выражение `x+y-z` вычисляется как `(x+y)-z`.</span><span class="sxs-lookup"><span data-stu-id="14b54-127">For example, `x+y-z` is evaluated as `(x+y)-z`.</span></span>  
  
 <span data-ttu-id="14b54-128">Чтобы переопределить порядок вычисления операторов в выражении, следует использовать скобки.</span><span class="sxs-lookup"><span data-stu-id="14b54-128">You can use parentheses to override the defined precedence of the operators in a query.</span></span> <span data-ttu-id="14b54-129">Вначале все выражение внутри скобок вычисляется до получения одного значения, которое затем может быть использовано любым оператором за пределами скобок.</span><span class="sxs-lookup"><span data-stu-id="14b54-129">Everything within parentheses is evaluated first to yield a single result before that result can be used by any operator outside the parentheses.</span></span> <span data-ttu-id="14b54-130">Например `x+y*z` умножает `y` по `z` , а затем добавляет `x`, но `(x+y)*z` добавляет `x` для `y` и умножает результат на `z`.</span><span class="sxs-lookup"><span data-stu-id="14b54-130">For example, `x+y*z` multiplies `y` by `z` and then adds `x`, but `(x+y)*z` adds `x` to `y` and then multiplies the result by `z`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14b54-131">См. также</span><span class="sxs-lookup"><span data-stu-id="14b54-131">See also</span></span>

- [<span data-ttu-id="14b54-132">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="14b54-132">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
