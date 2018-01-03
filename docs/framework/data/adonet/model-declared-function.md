---
title: "объявляемая моделью функция"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2f5c7828dc1ea79a548b35109b428da05c2b4560
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="model-declared-function"></a><span data-ttu-id="9af15-102">объявляемая моделью функция</span><span class="sxs-lookup"><span data-stu-id="9af15-102">model-declared function</span></span>
<span data-ttu-id="9af15-103">Объект *объявляемая моделью функция* — функция, которая объявлена в концептуальной модели, но не определена в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="9af15-103">A *model-declared function* is a function that is declared in a conceptual model, but is not defined in that conceptual model.</span></span> <span data-ttu-id="9af15-104">Функция может быть определена в среде размещения или хранения.</span><span class="sxs-lookup"><span data-stu-id="9af15-104">The function might be defined in the hosting or storage environment.</span></span> <span data-ttu-id="9af15-105">Например, объявляемая моделью функция может быть сопоставлена функции, определенной в базе данных, экспонируя таким образом функцию в концептуальной модели на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="9af15-105">For example, a model-declared function might be mapped to a function that is defined in a database, thus exposing server-side functionality in the conceptual model.</span></span>  
  
 <span data-ttu-id="9af15-106">Объявление объявляемой моделью функции содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="9af15-106">The declaration of a model-declared function contains the following information:</span></span>  
  
-   <span data-ttu-id="9af15-107">Имя функции.</span><span class="sxs-lookup"><span data-stu-id="9af15-107">The name of the function.</span></span> <span data-ttu-id="9af15-108">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="9af15-108">(Required)</span></span>  
  
-   <span data-ttu-id="9af15-109">Тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="9af15-109">The type of the return value.</span></span> <span data-ttu-id="9af15-110">(Необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="9af15-110">(Optional)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9af15-111">Если возвращаемое значение не задано, возвращаемого значения не будет.</span><span class="sxs-lookup"><span data-stu-id="9af15-111">If no return value is specified, the return type is void.</span></span>  
  
-   <span data-ttu-id="9af15-112">Сведения о параметрах, включая имя и тип параметров.</span><span class="sxs-lookup"><span data-stu-id="9af15-112">Parameter information, including parameter name and type.</span></span> <span data-ttu-id="9af15-113">(Необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="9af15-113">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="9af15-114">Пример</span><span class="sxs-lookup"><span data-stu-id="9af15-114">Example</span></span>  
 <span data-ttu-id="9af15-115">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="9af15-115">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="9af15-116">В языке CSDL, имеет одну реализацию объявляемая моделью функция [импорт функции](http://msdn.microsoft.com/en-us/125704ae-56c7-4233-80b7-389a10f3a65d).</span><span class="sxs-lookup"><span data-stu-id="9af15-116">In CSDL, one implementation of a model-declared function is a [function import](http://msdn.microsoft.com/en-us/125704ae-56c7-4233-80b7-389a10f3a65d).</span></span> <span data-ttu-id="9af15-117">Далее на языке CSDL определяется контейнер сущностей с определением импорта функции.</span><span class="sxs-lookup"><span data-stu-id="9af15-117">The following CSDL defines an entity container with a function import definition.</span></span> <span data-ttu-id="9af15-118">Обратите внимание, что тип возвращаемого значения для функции отсутствует, поскольку тип возвращаемого значения не задан.</span><span class="sxs-lookup"><span data-stu-id="9af15-118">Note that the return type for the function is void since no return type is specified.</span></span>  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a><span data-ttu-id="9af15-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9af15-119">See Also</span></span>  
 [<span data-ttu-id="9af15-120">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="9af15-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="9af15-121">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="9af15-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
