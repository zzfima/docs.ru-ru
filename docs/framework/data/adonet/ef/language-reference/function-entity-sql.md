---
title: FUNCTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
ms.openlocfilehash: 1c02583400f9092dcb5008239bfd1fd73c63c326
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485551"
---
# <a name="function-entity-sql"></a><span data-ttu-id="34e89-102">FUNCTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="34e89-102">FUNCTION (Entity SQL)</span></span>
<span data-ttu-id="34e89-103">Определяет функцию в рамках команды запроса Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="34e89-103">Defines a function in the scope of an Entity SQL query command.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34e89-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34e89-104">Syntax</span></span>  
  
```  
FUNCTION function-name  
( [ { parameter_name <type_definition>   
        [ ,...n ]  
  ]  
) AS ( function_expression )   
  
<type_definition>::=  
    { data_type | COLLECTION ( <type_definition> )   
                | REF ( data_type )   
                | ROW ( row_expression )   
        }   
```  
  
## <a name="arguments"></a><span data-ttu-id="34e89-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="34e89-105">Arguments</span></span>  
 `function-name`  
 <span data-ttu-id="34e89-106">Имя функции.</span><span class="sxs-lookup"><span data-stu-id="34e89-106">Name of the function.</span></span>  
  
 `parameter-name`  
 <span data-ttu-id="34e89-107">Имя параметра функции.</span><span class="sxs-lookup"><span data-stu-id="34e89-107">Name of a parameter in the function.</span></span>  
  
 `function_expression`  
 <span data-ttu-id="34e89-108">Допустимое выражение Entity SQL, представляющее функцию.</span><span class="sxs-lookup"><span data-stu-id="34e89-108">A valid Entity SQL expression that is the function.</span></span> <span data-ttu-id="34e89-109">Команда в функции может действовать, используя параметры `parameter_name` , переданные функции.</span><span class="sxs-lookup"><span data-stu-id="34e89-109">The command in the function can act on `parameter_name` parameters passed to the function.</span></span>  
  
 `data_type`  
 <span data-ttu-id="34e89-110">Имя поддерживаемого типа.</span><span class="sxs-lookup"><span data-stu-id="34e89-110">Name of a supported type.</span></span>  
  
 <span data-ttu-id="34e89-111">COLLECTION ( <type_definition`>` )</span><span class="sxs-lookup"><span data-stu-id="34e89-111">COLLECTION ( <type_definition`>` )</span></span>  
 <span data-ttu-id="34e89-112">Выражение, возвращающее коллекцию поддерживаемых типов, строк или ссылок.</span><span class="sxs-lookup"><span data-stu-id="34e89-112">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
 <span data-ttu-id="34e89-113">REF **(**`data_type`**)**</span><span class="sxs-lookup"><span data-stu-id="34e89-113">REF **(**`data_type`**)**</span></span>  
 <span data-ttu-id="34e89-114">Выражение, возвращающее ссылку на тип сущности.</span><span class="sxs-lookup"><span data-stu-id="34e89-114">An expression that returns a reference to an entity type.</span></span>  
  
 <span data-ttu-id="34e89-115">ROW **(**`row_expression`**)**</span><span class="sxs-lookup"><span data-stu-id="34e89-115">ROW **(**`row_expression`**)**</span></span>  
 <span data-ttu-id="34e89-116">Выражение, возвращающее анонимные структурно типизированные записи из одного или нескольких значений.</span><span class="sxs-lookup"><span data-stu-id="34e89-116">An expression that returns anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="34e89-117">Дополнительные сведения см. в разделе [ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="34e89-117">For more information, see [ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34e89-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="34e89-118">Remarks</span></span>  
 <span data-ttu-id="34e89-119">Объявить встроенными можно несколько функций с одинаковыми именами при условии, что эти функции имеют различные сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="34e89-119">Multiple functions with the same name can be declared inline, as long as the function signatures are different.</span></span> <span data-ttu-id="34e89-120">Для получения дополнительной информации см. [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="34e89-120">For more information, see [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).</span></span>  
  
 <span data-ttu-id="34e89-121">Встроенная функция может быть вызвана командой SQL только после определения ее в этой команде.</span><span class="sxs-lookup"><span data-stu-id="34e89-121">An inline function can be called in an Entity SQL command only after it has been defined in that command.</span></span> <span data-ttu-id="34e89-122">Однако встроенная функция может быть вызвана в пределах другой встроенной функции как до, так и после определения вызываемой функции.</span><span class="sxs-lookup"><span data-stu-id="34e89-122">However, an inline function can be called inside another inline function either before or after the called function has been defined.</span></span> <span data-ttu-id="34e89-123">В следующем примере функция A вызывает функцию B до того, как функция B была определена.</span><span class="sxs-lookup"><span data-stu-id="34e89-123">In the following example, function A calls function B before function B is defined:</span></span>  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 <span data-ttu-id="34e89-124">Дополнительные сведения см. в разделе [как: вызов пользовательской функции](https://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02).</span><span class="sxs-lookup"><span data-stu-id="34e89-124">For more information, see [How to: Call a User-Defined Function](https://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02).</span></span>  
  
 <span data-ttu-id="34e89-125">Функции также могут быть объявлены внутри самой модели.</span><span class="sxs-lookup"><span data-stu-id="34e89-125">Functions can also be declared in the model itself.</span></span> <span data-ttu-id="34e89-126">Функции, объявленные в модели, выполняются так же, как и функции, объявленные встроенными в команде.</span><span class="sxs-lookup"><span data-stu-id="34e89-126">Functions declared in the model are executed in the same way as functions declared inline in the command.</span></span> <span data-ttu-id="34e89-127">Дополнительные сведения см. в разделе [определяемые пользователем функции](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="34e89-127">For more information, see [User-Defined Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="34e89-128">Пример</span><span class="sxs-lookup"><span data-stu-id="34e89-128">Example</span></span>  
 <span data-ttu-id="34e89-129">В следующей команде Entity SQL определяется функция `Products` , использующая целочисленное значение для фильтрации возвращаемых продуктов.</span><span class="sxs-lookup"><span data-stu-id="34e89-129">The following Entity SQL command defines a function `Products` that takes an integer value to filter the returned products.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function1)]  
  
## <a name="example"></a><span data-ttu-id="34e89-130">Пример</span><span class="sxs-lookup"><span data-stu-id="34e89-130">Example</span></span>  
 <span data-ttu-id="34e89-131">В следующей команде Entity SQL определяется функция `StringReturnsCollection` , использующая коллекцию строк для фильтрации возвращаемых контактов.</span><span class="sxs-lookup"><span data-stu-id="34e89-131">The following Entity SQL command defines a function `StringReturnsCollection` that takes a collection of strings to filter the returned contacts.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function2)]  
  
## <a name="see-also"></a><span data-ttu-id="34e89-132">См. также</span><span class="sxs-lookup"><span data-stu-id="34e89-132">See Also</span></span>  
 [<span data-ttu-id="34e89-133">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="34e89-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="34e89-134">Язык Entity SQL</span><span class="sxs-lookup"><span data-stu-id="34e89-134">Entity SQL Language</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
