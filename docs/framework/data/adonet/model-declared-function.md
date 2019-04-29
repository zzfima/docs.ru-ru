---
title: объявляемая моделью функция
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: c9abf9a3340cd22ab5d654588b1d22e10b5c05fa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772116"
---
# <a name="model-declared-function"></a><span data-ttu-id="9f767-102">объявляемая моделью функция</span><span class="sxs-lookup"><span data-stu-id="9f767-102">model-declared function</span></span>
<span data-ttu-id="9f767-103">Объект *объявляемая моделью функция* является функцией, которая объявлена в концептуальной модели, но не определен в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="9f767-103">A *model-declared function* is a function that is declared in a conceptual model, but is not defined in that conceptual model.</span></span> <span data-ttu-id="9f767-104">Функция может быть определена в среде размещения или хранения.</span><span class="sxs-lookup"><span data-stu-id="9f767-104">The function might be defined in the hosting or storage environment.</span></span> <span data-ttu-id="9f767-105">Например, объявляемая моделью функция может быть сопоставлена функции, определенной в базе данных, экспонируя таким образом функцию в концептуальной модели на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="9f767-105">For example, a model-declared function might be mapped to a function that is defined in a database, thus exposing server-side functionality in the conceptual model.</span></span>  
  
 <span data-ttu-id="9f767-106">Объявление объявляемой моделью функции содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="9f767-106">The declaration of a model-declared function contains the following information:</span></span>  
  
- <span data-ttu-id="9f767-107">Имя функции.</span><span class="sxs-lookup"><span data-stu-id="9f767-107">The name of the function.</span></span> <span data-ttu-id="9f767-108">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="9f767-108">(Required)</span></span>  
  
- <span data-ttu-id="9f767-109">Тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="9f767-109">The type of the return value.</span></span> <span data-ttu-id="9f767-110">(Необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="9f767-110">(Optional)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9f767-111">Если возвращаемое значение не задано, возвращаемого значения не будет.</span><span class="sxs-lookup"><span data-stu-id="9f767-111">If no return value is specified, the return type is void.</span></span>  
  
- <span data-ttu-id="9f767-112">Сведения о параметрах, включая имя и тип параметров.</span><span class="sxs-lookup"><span data-stu-id="9f767-112">Parameter information, including parameter name and type.</span></span> <span data-ttu-id="9f767-113">(Необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="9f767-113">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f767-114">Пример</span><span class="sxs-lookup"><span data-stu-id="9f767-114">Example</span></span>  
 <span data-ttu-id="9f767-115">[ADO.NET Entity Framework](./ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="9f767-115">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="9f767-116">В языке CSDL, одна реализация объявляемой моделью функции является импорт функции (с помощью [элемент FunctionImport](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)).</span><span class="sxs-lookup"><span data-stu-id="9f767-116">In CSDL, one implementation of a model-declared function is a function import (using the [FunctionImport element](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)).</span></span> <span data-ttu-id="9f767-117">Далее на языке CSDL определяется контейнер сущностей с определением импорта функции.</span><span class="sxs-lookup"><span data-stu-id="9f767-117">The following CSDL defines an entity container with a function import definition.</span></span> <span data-ttu-id="9f767-118">Обратите внимание, что возвращаемый тип для функции отсутствует, поскольку возвращаемый тип не задан.</span><span class="sxs-lookup"><span data-stu-id="9f767-118">Note that the return type for the function is void since no return type is specified.</span></span>  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a><span data-ttu-id="9f767-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9f767-119">See also</span></span>

- [<span data-ttu-id="9f767-120">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="9f767-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="9f767-121">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="9f767-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
