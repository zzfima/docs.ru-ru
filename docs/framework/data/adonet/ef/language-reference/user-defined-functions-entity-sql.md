---
title: "Пользовательские функции (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: df1b2a7c605134d57fcc21f9253373d4e0febb37
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="user-defined-functions-entity-sql"></a><span data-ttu-id="cb52e-102">Пользовательские функции (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cb52e-102">User-Defined Functions (Entity SQL)</span></span>
<span data-ttu-id="cb52e-103">Entity SQL поддерживает вызов встроенных определяемых пользователем функций в запросе.</span><span class="sxs-lookup"><span data-stu-id="cb52e-103">Entity SQL supports calling user-defined functions in a query.</span></span> <span data-ttu-id="cb52e-104">Можно определить эти встроенные функции с помощью запроса (см. [как: вызов пользовательской функции](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02)) или как часть концептуальной модели (в разделе [как: определение пользовательских функций в концептуальной модели](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f)).</span><span class="sxs-lookup"><span data-stu-id="cb52e-104">You can define these functions inline with the query (see [How to: Call a User-Defined Function](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02)) or as part of the conceptual model (see [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f)).</span></span> <span data-ttu-id="cb52e-105">Функции концептуальной модели, определяются как команда Entity SQL в [DefiningExpression](http://msdn.microsoft.com/en-us/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) элемент [функция](http://msdn.microsoft.com/en-us/dc3beca7-55cf-4977-8db0-5064cdbab134) элемента в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="cb52e-105">Conceptual model functions are defined as an Entity SQL command in the [DefiningExpression](http://msdn.microsoft.com/en-us/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) element of a [Function](http://msdn.microsoft.com/en-us/dc3beca7-55cf-4977-8db0-5064cdbab134) element in the conceptual model.</span></span>  
  
 <span data-ttu-id="cb52e-106">Entity SQL позволяет определить функции в самой команде запроса.</span><span class="sxs-lookup"><span data-stu-id="cb52e-106">Entity SQL enables you to define functions in the query command itself.</span></span> <span data-ttu-id="cb52e-107">[ФУНКЦИЯ](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) оператор определяет встроенные функции.</span><span class="sxs-lookup"><span data-stu-id="cb52e-107">The [FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) operator defines inline functions.</span></span> <span data-ttu-id="cb52e-108">В одной команде можно задать несколько функций с одним и тем же именем при условии, что эти функции имеют уникальные сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="cb52e-108">You can define multiple functions in a single command, and these functions can have the same function name, as long as the function signatures are unique.</span></span> <span data-ttu-id="cb52e-109">Для получения дополнительной информации см. [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="cb52e-109">For more information, see [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb52e-110">См. также</span><span class="sxs-lookup"><span data-stu-id="cb52e-110">See Also</span></span>  
 [<span data-ttu-id="cb52e-111">Функции</span><span class="sxs-lookup"><span data-stu-id="cb52e-111">Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
