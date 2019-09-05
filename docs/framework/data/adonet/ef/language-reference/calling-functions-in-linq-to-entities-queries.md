---
title: Вызов функций в запросах LINQ to Entities
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: 267bb393d9e75c66eb18139e8897da34bd86e159
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251267"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="918d4-102">Вызов функций в запросах LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="918d4-102">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="918d4-103">В подразделах этого раздела описывается вызов функций в запросах LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="918d4-103">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="918d4-104">Классы <xref:System.Data.Objects.EntityFunctions> и <xref:System.Data.Objects.SqlClient.SqlFunctions> обеспечивают доступ к каноническим функциям и функциям базы данных посредством платформы Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="918d4-104">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="918d4-105">Дополнительные сведения см. в разделе [Практическое руководство. Вызывайте канонические [функции](how-to-call-canonical-functions.md) и как: Вызывайте функции](how-to-call-database-functions.md)базы данных.</span><span class="sxs-lookup"><span data-stu-id="918d4-105">For more information, see [How to: Call Canonical Functions](how-to-call-canonical-functions.md) and [How to: Call Database Functions](how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="918d4-106">Процесс вызова пользовательской функции состоит из трех основных шагов.</span><span class="sxs-lookup"><span data-stu-id="918d4-106">The process for calling a custom function requires three basic steps:</span></span>  
  
1. <span data-ttu-id="918d4-107">Определите функцию в концептуальной модели или объявите функцию в модели хранения.</span><span class="sxs-lookup"><span data-stu-id="918d4-107">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2. <span data-ttu-id="918d4-108">Добавьте метод в приложение и сопоставьте его с функцией в модели с помощью <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="918d4-108">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3. <span data-ttu-id="918d4-109">Вызовите функцию в запросе LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="918d4-109">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="918d4-110">Дополнительные сведения см. в подразделах этого раздела.</span><span class="sxs-lookup"><span data-stu-id="918d4-110">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="918d4-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="918d4-111">In This Section</span></span>  
 [<span data-ttu-id="918d4-112">Практическое руководство. Вызов канонических функций</span><span class="sxs-lookup"><span data-stu-id="918d4-112">How to: Call Canonical Functions</span></span>](how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="918d4-113">Практическое руководство. Вызов функций базы данных</span><span class="sxs-lookup"><span data-stu-id="918d4-113">How to: Call Database Functions</span></span>](how-to-call-database-functions.md)  
  
 [<span data-ttu-id="918d4-114">Практическое руководство. Вызов пользовательских функций базы данных</span><span class="sxs-lookup"><span data-stu-id="918d4-114">How to: Call Custom Database Functions</span></span>](how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="918d4-115">Практическое руководство. Вызов определяемых моделью функций в запросах</span><span class="sxs-lookup"><span data-stu-id="918d4-115">How to: Call Model-Defined Functions in Queries</span></span>](how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="918d4-116">Практическое руководство. Вызов определяемых моделью функций в качестве методов объекта</span><span class="sxs-lookup"><span data-stu-id="918d4-116">How to: Call Model-Defined Functions as Object Methods</span></span>](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="918d4-117">См. также</span><span class="sxs-lookup"><span data-stu-id="918d4-117">See also</span></span>

- [<span data-ttu-id="918d4-118">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="918d4-118">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="918d4-119">Канонические функции</span><span class="sxs-lookup"><span data-stu-id="918d4-119">Canonical Functions</span></span>](canonical-functions.md)
- <span data-ttu-id="918d4-120">[Общие сведения о файле EDMX](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="918d4-120">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- <span data-ttu-id="918d4-121">[Практическое руководство. Определение пользовательских функций в концептуальной модели](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="918d4-121">[How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span></span>
