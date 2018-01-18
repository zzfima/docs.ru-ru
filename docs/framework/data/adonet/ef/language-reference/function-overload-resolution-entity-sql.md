---
title: "Разрешение перегрузки функций (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c648054-3808-4a69-9d3e-98e6a4f9c5ca
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: cafbdd1a06ce506516fa985e9af147f55b4ea3d4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="function-overload-resolution-entity-sql"></a><span data-ttu-id="b5e96-102">Разрешение перегрузки функций (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b5e96-102">Function Overload Resolution (Entity SQL)</span></span>
<span data-ttu-id="b5e96-103">В данном разделе описывается, каким образом разрешаются функции [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5e96-103">This topic describes how [!INCLUDE[esql](../../../../../../includes/esql-md.md)] functions are resolved.</span></span>  
  
 <span data-ttu-id="b5e96-104">С одним именем можно определить более одной функции при условии, что эти функции имеют уникальные сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="b5e96-104">More than one function can be defined with the same name, as long as the functions have unique signatures.</span></span>  
  
 <span data-ttu-id="b5e96-105">В этом случае для определения, на какие функции ссылается данное выражение, следует применить следующие критерии.</span><span class="sxs-lookup"><span data-stu-id="b5e96-105">When this is the case, the following criteria must be applied to determine which function is referenced by a given expression.</span></span> <span data-ttu-id="b5e96-106">Эти критерии применяются последовательно.</span><span class="sxs-lookup"><span data-stu-id="b5e96-106">These criteria are applied in sequence.</span></span> <span data-ttu-id="b5e96-107">Первый критерий, применимый только к одной функции, определяет разрешенную функцию.</span><span class="sxs-lookup"><span data-stu-id="b5e96-107">The first criterion that applies only to a single function is the resolved function.</span></span>  
  
1.  <span data-ttu-id="b5e96-108">**Параметр с номером**.</span><span class="sxs-lookup"><span data-stu-id="b5e96-108">**Parameter number**.</span></span> <span data-ttu-id="b5e96-109">Функция имеет то же число параметров, которое указано в выражении.</span><span class="sxs-lookup"><span data-stu-id="b5e96-109">The function has the same number of parameters specified in the expression.</span></span>  
  
2.  <span data-ttu-id="b5e96-110">**Точное совпадение типа**.</span><span class="sxs-lookup"><span data-stu-id="b5e96-110">**Exact match on type**.</span></span> <span data-ttu-id="b5e96-111">Тип каждого аргумента функции точно соответствует типу параметра или является литералом NULL.</span><span class="sxs-lookup"><span data-stu-id="b5e96-111">Each argument type of the function exactly matches the parameter type, or is the null literal.</span></span>  
  
3.  <span data-ttu-id="b5e96-112">**Совпадение подтипов**.</span><span class="sxs-lookup"><span data-stu-id="b5e96-112">**Match on subtype**.</span></span> <span data-ttu-id="b5e96-113">Тип каждого аргумента функции точно соответствует подтипу типа параметра или аргумент является литералом NULL.</span><span class="sxs-lookup"><span data-stu-id="b5e96-113">Each argument type of the function exactly matches or is a sub-type of the parameter type, or the argument is the null literal.</span></span> <span data-ttu-id="b5e96-114">В случае, если несколько функций отличаются только числом требуемых преобразований подтипа, разрешаемой является функция с наименьшим числом преобразований подтипа.</span><span class="sxs-lookup"><span data-stu-id="b5e96-114">In the event that several functions differ only in the number of sub-type conversions required, the function with the least number of sub-type conversions is the resolved function.</span></span>  
  
4.  <span data-ttu-id="b5e96-115">**Совпадение подтипов или повышение типа**.</span><span class="sxs-lookup"><span data-stu-id="b5e96-115">**Match on subtype or type promotion**.</span></span> <span data-ttu-id="b5e96-116">Тип каждого аргумента функции точно соответствует, является подтипом или может быть повышен до типа параметра или аргумент является литералом NULL.</span><span class="sxs-lookup"><span data-stu-id="b5e96-116">Each argument type of the function exactly matches, is a sub-type of, or can be promoted to the parameter type, or the argument is the null literal.</span></span> <span data-ttu-id="b5e96-117">С другой стороны, в случае, если несколько функций отличаются только числом требуемых преобразований и повышений подтипа, то разрешаемой является функция с наименьшим числом преобразований и повышений подтипа.</span><span class="sxs-lookup"><span data-stu-id="b5e96-117">Again, in the event that several functions differ only in the number of sub-type conversions and promotions, the function with the least number of sub-type conversions and promotions is the resolved function.</span></span>  
  
 <span data-ttu-id="b5e96-118">Если ни один из этих критериев не позволяет выбрать единственную функцию, то выражение вызова функции неоднозначно.</span><span class="sxs-lookup"><span data-stu-id="b5e96-118">If none of these criteria result in a single function being selected, the function invocation expression is ambiguous.</span></span>  
  
 <span data-ttu-id="b5e96-119">Даже если с помощью этих правил можно извлечь единственную функцию, аргументы могут не соответствовать параметрам.</span><span class="sxs-lookup"><span data-stu-id="b5e96-119">Even if a single function can be extracted using these rules, the arguments still might not match the parameters.</span></span> <span data-ttu-id="b5e96-120">В этом случае возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="b5e96-120">An error is raised in this case.</span></span>  
  
 <span data-ttu-id="b5e96-121">Что касается определяемых пользователем функций, то приоритет имеет определение для встроенной функции запроса, даже если существует функция, определенная в модели, с сигнатурой, которая больше подходит для пользовательской функции.</span><span class="sxs-lookup"><span data-stu-id="b5e96-121">For user-defined functions, the definition for an inline query function takes precedence even when a model-defined function exists with a signature that is a better match for the user-defined function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5e96-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b5e96-122">See Also</span></span>  
 [<span data-ttu-id="b5e96-123">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b5e96-123">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="b5e96-124">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b5e96-124">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="b5e96-125">Функции</span><span class="sxs-lookup"><span data-stu-id="b5e96-125">Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
