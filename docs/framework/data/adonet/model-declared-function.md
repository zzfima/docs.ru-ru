---
title: объявляемая моделью функция
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: 5db7d49fd4b839cef47db8086b4ef39ce4dc6aea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725146"
---
# <a name="model-declared-function"></a><span data-ttu-id="43020-102">объявляемая моделью функция</span><span class="sxs-lookup"><span data-stu-id="43020-102">model-declared function</span></span>
<span data-ttu-id="43020-103">Объект *объявляемая моделью функция* является функцией, которая объявлена в концептуальной модели, но не определен в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="43020-103">A *model-declared function* is a function that is declared in a conceptual model, but is not defined in that conceptual model.</span></span> <span data-ttu-id="43020-104">Функция может быть определена в среде размещения или хранения.</span><span class="sxs-lookup"><span data-stu-id="43020-104">The function might be defined in the hosting or storage environment.</span></span> <span data-ttu-id="43020-105">Например, объявляемая моделью функция может быть сопоставлена функции, определенной в базе данных, экспонируя таким образом функцию в концептуальной модели на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="43020-105">For example, a model-declared function might be mapped to a function that is defined in a database, thus exposing server-side functionality in the conceptual model.</span></span>  
  
 <span data-ttu-id="43020-106">Объявление объявляемой моделью функции содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="43020-106">The declaration of a model-declared function contains the following information:</span></span>  
  
-   <span data-ttu-id="43020-107">Имя функции.</span><span class="sxs-lookup"><span data-stu-id="43020-107">The name of the function.</span></span> <span data-ttu-id="43020-108">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="43020-108">(Required)</span></span>  
  
-   <span data-ttu-id="43020-109">Тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="43020-109">The type of the return value.</span></span> <span data-ttu-id="43020-110">(Необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="43020-110">(Optional)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="43020-111">Если возвращаемое значение не задано, возвращаемого значения не будет.</span><span class="sxs-lookup"><span data-stu-id="43020-111">If no return value is specified, the return type is void.</span></span>  
  
-   <span data-ttu-id="43020-112">Сведения о параметрах, включая имя и тип параметров.</span><span class="sxs-lookup"><span data-stu-id="43020-112">Parameter information, including parameter name and type.</span></span> <span data-ttu-id="43020-113">(Необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="43020-113">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="43020-114">Пример</span><span class="sxs-lookup"><span data-stu-id="43020-114">Example</span></span>  
 <span data-ttu-id="43020-115">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="43020-115">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="43020-116">В языке CSDL, одна реализация объявляемой моделью функции является [импорта функции](https://msdn.microsoft.com/library/125704ae-56c7-4233-80b7-389a10f3a65d).</span><span class="sxs-lookup"><span data-stu-id="43020-116">In CSDL, one implementation of a model-declared function is a [function import](https://msdn.microsoft.com/library/125704ae-56c7-4233-80b7-389a10f3a65d).</span></span> <span data-ttu-id="43020-117">Далее на языке CSDL определяется контейнер сущностей с определением импорта функции.</span><span class="sxs-lookup"><span data-stu-id="43020-117">The following CSDL defines an entity container with a function import definition.</span></span> <span data-ttu-id="43020-118">Обратите внимание, что тип возвращаемого значения для функции отсутствует, поскольку тип возвращаемого значения не задан.</span><span class="sxs-lookup"><span data-stu-id="43020-118">Note that the return type for the function is void since no return type is specified.</span></span>  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a><span data-ttu-id="43020-119">См. также</span><span class="sxs-lookup"><span data-stu-id="43020-119">See also</span></span>
- [<span data-ttu-id="43020-120">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="43020-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="43020-121">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="43020-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
