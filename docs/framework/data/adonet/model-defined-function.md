---
title: функция определенной модели
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 5c91c221735f3385370ec2fbb532d5b3c5dd2898
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32763778"
---
# <a name="model-defined-function"></a><span data-ttu-id="d0fb2-102">функция определенной модели</span><span class="sxs-lookup"><span data-stu-id="d0fb2-102">model-defined function</span></span>
<span data-ttu-id="d0fb2-103">Объект *определяемой моделью функции* — это функция, которая определена в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="d0fb2-103">A *model-defined function* is a function that is defined in a conceptual model.</span></span> <span data-ttu-id="d0fb2-104">Тело функции, определенной модели представляется в формате [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), что позволяет выполнять функцию должна быть представлена независимо от правил или языков, поддерживаемых в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="d0fb2-104">The body of a model-defined function is expressed in [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), which allows for the function to be expressed independently of rules or languages supported in the data source.</span></span>  
  
 <span data-ttu-id="d0fb2-105">Определение определяемой моделью функции содержит следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="d0fb2-105">A definition for a model-defined function contains the following information:</span></span>  
  
-   <span data-ttu-id="d0fb2-106">Имя функции.</span><span class="sxs-lookup"><span data-stu-id="d0fb2-106">A function name.</span></span> <span data-ttu-id="d0fb2-107">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="d0fb2-107">(Required)</span></span>  
  
-   <span data-ttu-id="d0fb2-108">Тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="d0fb2-108">The type of the return value.</span></span> <span data-ttu-id="d0fb2-109">(Необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="d0fb2-109">(Optional)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d0fb2-110">Если тип возвращаемого значения не задан, возвращаемого значения не будет.</span><span class="sxs-lookup"><span data-stu-id="d0fb2-110">If no return type is specified, the return value is void.</span></span>  
  
-   <span data-ttu-id="d0fb2-111">Сведения о параметрах.</span><span class="sxs-lookup"><span data-stu-id="d0fb2-111">Parameter information.</span></span> <span data-ttu-id="d0fb2-112">(Необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="d0fb2-112">(Optional)</span></span>  
  
-   <span data-ttu-id="d0fb2-113">[Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) выражение, определяющее тела функции.</span><span class="sxs-lookup"><span data-stu-id="d0fb2-113">An [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) expression that defines the body of the function.</span></span>  
  
 <span data-ttu-id="d0fb2-114">Обратите внимание, что определяемые моделью функции не поддерживают выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="d0fb2-114">Note that model-defined functions do not support output parameters.</span></span> <span data-ttu-id="d0fb2-115">Это ограничение введено, чтобы определяемые моделью функции можно было сочетать.</span><span class="sxs-lookup"><span data-stu-id="d0fb2-115">This restriction is in place so that model-defined functions can be composed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0fb2-116">Пример</span><span class="sxs-lookup"><span data-stu-id="d0fb2-116">Example</span></span>  
 <span data-ttu-id="d0fb2-117">На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="d0fb2-117">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 <span data-ttu-id="d0fb2-118">![Модель с опубликованной датой](../../../../docs/framework/data/adonet/media/modelwithpublisheddate.gif "ModelWithPublishedDate")</span><span class="sxs-lookup"><span data-stu-id="d0fb2-118">![Model With Published Date](../../../../docs/framework/data/adonet/media/modelwithpublisheddate.gif "ModelWithPublishedDate")</span></span>  
  
 <span data-ttu-id="d0fb2-119">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="d0fb2-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="d0fb2-120">Следующий язык CSDL определяет функцию в концептуальной модели, которая возвращает числа лет с момента публикации экземпляра `Book` (ранее приведенного на схеме).</span><span class="sxs-lookup"><span data-stu-id="d0fb2-120">The following CSDL defines a function in the conceptual model that returns the numbers of years since an instance of a `Book` (in the diagram above) was published.</span></span>  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a><span data-ttu-id="d0fb2-121">См. также</span><span class="sxs-lookup"><span data-stu-id="d0fb2-121">See Also</span></span>  
 [<span data-ttu-id="d0fb2-122">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="d0fb2-122">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="d0fb2-123">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="d0fb2-123">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [<span data-ttu-id="d0fb2-124">Модель EDM. Примитивные типы данных</span><span class="sxs-lookup"><span data-stu-id="d0fb2-124">Entity Data Model: Primitive Data Types</span></span>](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
