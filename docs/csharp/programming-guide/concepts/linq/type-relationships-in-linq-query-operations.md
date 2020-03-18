---
title: Отношения между типами в операциях запросов LINQ (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- inferring type information [LINQ in C#]
- data sources [LINQ in C#], type relationships
- queries [LINQ in C#], type relationships
- relationships [LINQ in C#]
- type relationships [LINQ in C#]
- variable relationships [LINQ in C#]
- type information inferred [LINQ in C#]
- data transformations [LINQ in C#]
- LINQ [C#], type relationships
ms.assetid: 99118938-d47c-4d7e-bb22-2657a9f95268
ms.openlocfilehash: 41853e6858fae9e8d449aeed95a6a84f343d5874
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635617"
---
# <a name="type-relationships-in-linq-query-operations-c"></a><span data-ttu-id="048e4-102">Отношения между типами в операциях запросов LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="048e4-102">Type Relationships in LINQ Query Operations (C#)</span></span>
<span data-ttu-id="048e4-103">Для эффективного написания запросов следует понимать, как типы переменных связаны друг с другом в полной операции запроса.</span><span class="sxs-lookup"><span data-stu-id="048e4-103">To write queries effectively, you should understand how types of the variables in a complete query operation all relate to each other.</span></span> <span data-ttu-id="048e4-104">В таком случае вам будет проще работать с примерами LINQ и примерами кода в документации.</span><span class="sxs-lookup"><span data-stu-id="048e4-104">If you understand these relationships you will more easily comprehend the LINQ samples and code examples in the documentation.</span></span> <span data-ttu-id="048e4-105">Более того, можно будет представить, что происходит в фоновом режиме при неявном типизировании переменных с помощью `var`.</span><span class="sxs-lookup"><span data-stu-id="048e4-105">Furthermore, you will understand what occurs behind the scenes when variables are implicitly typed by using `var`.</span></span>  
  
 <span data-ttu-id="048e4-106">Операции запросов LINQ строго типизированы в источнике данных, в самом запросе и при выполнении запроса.</span><span class="sxs-lookup"><span data-stu-id="048e4-106">LINQ query operations are strongly typed in the data source, in the query itself, and in the query execution.</span></span> <span data-ttu-id="048e4-107">Тип переменных в запросе должен быть совместим с типом элементов в источнике данных и с типом переменной итерации в операторе `foreach`.</span><span class="sxs-lookup"><span data-stu-id="048e4-107">The type of the variables in the query must be compatible with the type of the elements in the data source and with the type of the iteration variable in the `foreach` statement.</span></span> <span data-ttu-id="048e4-108">Строгая типизация гарантирует перехват ошибок во время компиляции, когда их можно будет исправить прежде, чем с ними столкнутся пользователи.</span><span class="sxs-lookup"><span data-stu-id="048e4-108">This strong typing guarantees that type errors are caught at compile time when they can be corrected before users encounter them.</span></span>  
  
 <span data-ttu-id="048e4-109">Для демонстрации связи типов большая часть примеров использует явную типизацию для всех переменных.</span><span class="sxs-lookup"><span data-stu-id="048e4-109">In order to demonstrate these type relationships, most of the examples that follow use explicit typing for all variables.</span></span> <span data-ttu-id="048e4-110">Последний пример показывает применение тех же принципов даже при использовании неявной типизации с помощью [var](../../../language-reference/keywords/var.md).</span><span class="sxs-lookup"><span data-stu-id="048e4-110">The last example shows how the same principles apply even when you use implicit typing by using [var](../../../language-reference/keywords/var.md).</span></span>  
  
## <a name="queries-that-do-not-transform-the-source-data"></a><span data-ttu-id="048e4-111">Запросы, не выполняющие преобразование исходных данных</span><span class="sxs-lookup"><span data-stu-id="048e4-111">Queries that do not Transform the Source Data</span></span>  
 <span data-ttu-id="048e4-112">На следующем рисунке показана операция запроса LINQ to Objects, не выполняющая преобразование данных.</span><span class="sxs-lookup"><span data-stu-id="048e4-112">The following illustration shows a LINQ to Objects query operation that performs no transformations on the data.</span></span> <span data-ttu-id="048e4-113">Источник содержит последовательность строк, результат запроса также является последовательностью строк.</span><span class="sxs-lookup"><span data-stu-id="048e4-113">The source contains a sequence of strings and the query output is also a sequence of strings.</span></span>  
  
 ![Схема, показывающая отношения между типами данных в запросе LINQ.](./media/type-relationships-in-linq-query-operations/linq-query-data-type-relation.png)  
  
1. <span data-ttu-id="048e4-115">Аргумент типа источника данных определяет тип переменной диапазона.</span><span class="sxs-lookup"><span data-stu-id="048e4-115">The type argument of the data source determines the type of the range variable.</span></span>  
  
2. <span data-ttu-id="048e4-116">Тип выбранного объекта определяет тип переменной запроса.</span><span class="sxs-lookup"><span data-stu-id="048e4-116">The type of the object that is selected determines the type of the query variable.</span></span> <span data-ttu-id="048e4-117">Здесь `name` является строкой.</span><span class="sxs-lookup"><span data-stu-id="048e4-117">Here `name` is a string.</span></span> <span data-ttu-id="048e4-118">Следовательно, переменная запроса представляет собой `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="048e4-118">Therefore, the query variable is an `IEnumerable<string>`.</span></span>  
  
3. <span data-ttu-id="048e4-119">Итерация переменной запроса выполняется в операторе `foreach`.</span><span class="sxs-lookup"><span data-stu-id="048e4-119">The query variable is iterated over in the `foreach` statement.</span></span> <span data-ttu-id="048e4-120">Поскольку переменная запроса является последовательностью строк, переменная итерации также является строкой.</span><span class="sxs-lookup"><span data-stu-id="048e4-120">Because the query variable is a sequence of strings, the iteration variable is also a string.</span></span>  
  
## <a name="queries-that-transform-the-source-data"></a><span data-ttu-id="048e4-121">Запросы, выполняющие преобразование исходных данных</span><span class="sxs-lookup"><span data-stu-id="048e4-121">Queries that Transform the Source Data</span></span>  
 <span data-ttu-id="048e4-122">На следующем рисунке показана операция запроса [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], выполняющая простое преобразование данных.</span><span class="sxs-lookup"><span data-stu-id="048e4-122">The following illustration shows a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query operation that performs a simple transformation on the data.</span></span> <span data-ttu-id="048e4-123">В качестве входных данных запрос получает последовательность объектов `Customer` и выбирает в результате только свойство `Name`.</span><span class="sxs-lookup"><span data-stu-id="048e4-123">The query takes a sequence of `Customer` objects as input, and selects only the `Name` property in the result.</span></span> <span data-ttu-id="048e4-124">Поскольку `Name` является строкой, запрос формирует последовательность строк в качестве выходных данных.</span><span class="sxs-lookup"><span data-stu-id="048e4-124">Because `Name` is a string, the query produces a sequence of strings as output.</span></span>  
  
 ![Схема, показывающая запрос, преобразующий тип данных.](./media/type-relationships-in-linq-query-operations/linq-query-transform-data-type.png)  
  
1. <span data-ttu-id="048e4-126">Аргумент типа источника данных определяет тип переменной диапазона.</span><span class="sxs-lookup"><span data-stu-id="048e4-126">The type argument of the data source determines the type of the range variable.</span></span>  
  
2. <span data-ttu-id="048e4-127">Оператор `select` возвращает свойство `Name` вместо целого объекта `Customer`.</span><span class="sxs-lookup"><span data-stu-id="048e4-127">The `select` statement returns the `Name` property instead of the complete `Customer` object.</span></span> <span data-ttu-id="048e4-128">Поскольку `Name` является строкой, аргумент типа `custNameQuery` является `string`, а не `Customer`.</span><span class="sxs-lookup"><span data-stu-id="048e4-128">Because `Name` is a string, the type argument of `custNameQuery` is `string`, not `Customer`.</span></span>  
  
3. <span data-ttu-id="048e4-129">Поскольку `custNameQuery` представляет собой последовательность строк, переменная итерации цикла `foreach` также должна быть `string`.</span><span class="sxs-lookup"><span data-stu-id="048e4-129">Because `custNameQuery` is a sequence of strings, the `foreach` loop's iteration variable must also be a `string`.</span></span>  
  
 <span data-ttu-id="048e4-130">На следующем рисунке показано немного более сложное преобразование.</span><span class="sxs-lookup"><span data-stu-id="048e4-130">The following illustration shows a slightly more complex transformation.</span></span> <span data-ttu-id="048e4-131">Оператор `select` возвращает анонимный тип, захватывающий только два члена исходного объекта `Customer`.</span><span class="sxs-lookup"><span data-stu-id="048e4-131">The `select` statement returns an anonymous type that captures just two members of the original `Customer` object.</span></span>  
  
 ![Схема, показывающая более сложный запрос, преобразующий тип данных.](./media/type-relationships-in-linq-query-operations/linq-complex-query-transform-data-type.png)  
  
1. <span data-ttu-id="048e4-133">Аргумент типа источника данных всегда является типом переменной диапазона в запросе.</span><span class="sxs-lookup"><span data-stu-id="048e4-133">The type argument of the data source is always the type of the range variable in the query.</span></span>  
  
2. <span data-ttu-id="048e4-134">Так как оператор `select` создает анонимный тип, переменная запроса должна неявно типизирована с помощью `var`.</span><span class="sxs-lookup"><span data-stu-id="048e4-134">Because the `select` statement produces an anonymous type, the query variable must be implicitly typed by using `var`.</span></span>  
  
3. <span data-ttu-id="048e4-135">Поскольку тип переменной запроса неявный, переменная итерации в цикле `foreach` также должна быть неявной.</span><span class="sxs-lookup"><span data-stu-id="048e4-135">Because the type of the query variable is implicit, the iteration variable in the `foreach` loop must also be implicit.</span></span>  
  
## <a name="letting-the-compiler-infer-type-information"></a><span data-ttu-id="048e4-136">Разрешение компилятору определять сведения о типе</span><span class="sxs-lookup"><span data-stu-id="048e4-136">Letting the compiler infer type information</span></span>  
 <span data-ttu-id="048e4-137">Несмотря на то, что необходимо обладать знаниями об отношениях типов в операции запроса, существует возможность передачи выполнения всех действий компилятору.</span><span class="sxs-lookup"><span data-stu-id="048e4-137">Although you should understand the type relationships in a query operation, you have the option to let the compiler do all the work for you.</span></span> <span data-ttu-id="048e4-138">Ключевое слово [var](../../../language-reference/keywords/var.md) можно использовать для любой локальной переменной в операции запроса.</span><span class="sxs-lookup"><span data-stu-id="048e4-138">The keyword [var](../../../language-reference/keywords/var.md) can be used for any local variable in a query operation.</span></span> <span data-ttu-id="048e4-139">Следующий рисунок похож на пример 2, рассмотренный выше.</span><span class="sxs-lookup"><span data-stu-id="048e4-139">The following illustration is similar to example number 2 that was discussed earlier.</span></span> <span data-ttu-id="048e4-140">Однако компилятор предоставляет строгий тип для каждой переменной в операции запроса.</span><span class="sxs-lookup"><span data-stu-id="048e4-140">However, the compiler supplies the strong type for each variable in the query operation.</span></span>  
  
 ![Схема, показывающая поток для типа с неявной типизацией.](./media/type-relationships-in-linq-query-operations/linq-type-flow-implicit-typing.png)  
  
 <span data-ttu-id="048e4-142">Дополнительные сведения о `var` см. в разделе [Неявно типизированные локальные переменные](../../classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="048e4-142">For more information about `var`, see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
