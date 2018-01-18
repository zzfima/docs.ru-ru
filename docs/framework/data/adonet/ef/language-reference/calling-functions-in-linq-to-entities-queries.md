---
title: "Вызов функций в запросах LINQ to Entities"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: dd81543f3a89f4f673f999b1fa80575de6d64654
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="98235-102">Вызов функций в запросах LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="98235-102">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="98235-103">В подразделах этого раздела описывается вызов функций в запросах LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="98235-103">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="98235-104">Классы <xref:System.Data.Objects.EntityFunctions> и <xref:System.Data.Objects.SqlClient.SqlFunctions> обеспечивают доступ к каноническим функциям и функциям базы данных посредством платформы Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="98235-104">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="98235-105">Дополнительные сведения см. в разделе [как: вызов канонических функций](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) и [как: вызов функции базы данных](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).</span><span class="sxs-lookup"><span data-stu-id="98235-105">For more information, see [How to: Call Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) and [How to: Call Database Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="98235-106">Процесс вызова пользовательской функции состоит из трех основных шагов.</span><span class="sxs-lookup"><span data-stu-id="98235-106">The process for calling a custom function requires three basic steps:</span></span>  
  
1.  <span data-ttu-id="98235-107">Определите функцию в концептуальной модели или объявите функцию в модели хранения.</span><span class="sxs-lookup"><span data-stu-id="98235-107">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2.  <span data-ttu-id="98235-108">Добавьте метод в приложение и сопоставьте его с функцией в модели с помощью <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="98235-108">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3.  <span data-ttu-id="98235-109">Вызовите функцию в запросе LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="98235-109">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="98235-110">Дополнительные сведения см. в подразделах этого раздела.</span><span class="sxs-lookup"><span data-stu-id="98235-110">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98235-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="98235-111">In This Section</span></span>  
 [<span data-ttu-id="98235-112">Практическое руководство. Вызов канонических функций</span><span class="sxs-lookup"><span data-stu-id="98235-112">How to: Call Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="98235-113">Практическое руководство. Вызов функций базы данных</span><span class="sxs-lookup"><span data-stu-id="98235-113">How to: Call Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)  
  
 [<span data-ttu-id="98235-114">Практическое руководство. Вызов настраиваемых функций базы данных</span><span class="sxs-lookup"><span data-stu-id="98235-114">How to: Call Custom Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="98235-115">Практическое руководство. Вызов определенных моделью функций в запросах</span><span class="sxs-lookup"><span data-stu-id="98235-115">How to: Call Model-Defined Functions in Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="98235-116">Практическое руководство. Вызов определенных моделью функций как методов объектов</span><span class="sxs-lookup"><span data-stu-id="98235-116">How to: Call Model-Defined Functions as Object Methods</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="98235-117">См. также</span><span class="sxs-lookup"><span data-stu-id="98235-117">See Also</span></span>  
 [<span data-ttu-id="98235-118">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="98235-118">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [<span data-ttu-id="98235-119">Канонические функции</span><span class="sxs-lookup"><span data-stu-id="98235-119">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)  
 [<span data-ttu-id="98235-120">Общие сведения о файлах .edmx</span><span class="sxs-lookup"><span data-stu-id="98235-120">.edmx File Overview</span></span>](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="98235-121">Как: определения пользовательских функций в концептуальной модели</span><span class="sxs-lookup"><span data-stu-id="98235-121">How to: Define Custom Functions in the Conceptual Model</span></span>](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f)
