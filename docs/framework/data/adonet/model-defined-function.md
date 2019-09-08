---
title: функция определенной модели
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 1418eccecea647204620455969696c6390bd4a18
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783614"
---
# <a name="model-defined-function"></a><span data-ttu-id="fb4cf-102">функция определенной модели</span><span class="sxs-lookup"><span data-stu-id="fb4cf-102">model-defined function</span></span>
<span data-ttu-id="fb4cf-103">*Определяемая моделью функция* — это функция, определенная в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="fb4cf-103">A *model-defined function* is a function that is defined in a conceptual model.</span></span> <span data-ttu-id="fb4cf-104">Текст функции, определяемой моделью, выражается в [Entity SQL](./ef/language-reference/entity-sql-language.md), что позволяет выражать функцию независимо от правил или языков, поддерживаемых в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="fb4cf-104">The body of a model-defined function is expressed in [Entity SQL](./ef/language-reference/entity-sql-language.md), which allows for the function to be expressed independently of rules or languages supported in the data source.</span></span>  
  
 <span data-ttu-id="fb4cf-105">Определение определяемой моделью функции содержит следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="fb4cf-105">A definition for a model-defined function contains the following information:</span></span>  
  
- <span data-ttu-id="fb4cf-106">Имя функции.</span><span class="sxs-lookup"><span data-stu-id="fb4cf-106">A function name.</span></span> <span data-ttu-id="fb4cf-107">(Обязательный атрибут).</span><span class="sxs-lookup"><span data-stu-id="fb4cf-107">(Required)</span></span>  
  
- <span data-ttu-id="fb4cf-108">Тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="fb4cf-108">The type of the return value.</span></span> <span data-ttu-id="fb4cf-109">(Необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="fb4cf-109">(Optional)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fb4cf-110">Если тип возвращаемого значения не задан, возвращаемого значения не будет.</span><span class="sxs-lookup"><span data-stu-id="fb4cf-110">If no return type is specified, the return value is void.</span></span>  
  
- <span data-ttu-id="fb4cf-111">Сведения о параметрах.</span><span class="sxs-lookup"><span data-stu-id="fb4cf-111">Parameter information.</span></span> <span data-ttu-id="fb4cf-112">(Необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="fb4cf-112">(Optional)</span></span>  
  
- <span data-ttu-id="fb4cf-113">Выражение [Entity SQL](./ef/language-reference/entity-sql-language.md) , определяющее текст функции.</span><span class="sxs-lookup"><span data-stu-id="fb4cf-113">An [Entity SQL](./ef/language-reference/entity-sql-language.md) expression that defines the body of the function.</span></span>  
  
 <span data-ttu-id="fb4cf-114">Обратите внимание, что определяемые моделью функции не поддерживают выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="fb4cf-114">Note that model-defined functions do not support output parameters.</span></span> <span data-ttu-id="fb4cf-115">Это ограничение введено, чтобы определяемые моделью функции можно было сочетать.</span><span class="sxs-lookup"><span data-stu-id="fb4cf-115">This restriction is in place so that model-defined functions can be composed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb4cf-116">Пример</span><span class="sxs-lookup"><span data-stu-id="fb4cf-116">Example</span></span>  
 <span data-ttu-id="fb4cf-117">На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="fb4cf-117">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 ![Снимок экрана, на котором показана модель с опубликованной датой.](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 <span data-ttu-id="fb4cf-119">[Entity Framework ADO.NET](./ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](./ef/language-reference/csdl-specification.md)), для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="fb4cf-119">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="fb4cf-120">Следующий язык CSDL определяет функцию в концептуальной модели, которая возвращает числа лет с момента публикации экземпляра `Book` (ранее приведенного на схеме).</span><span class="sxs-lookup"><span data-stu-id="fb4cf-120">The following CSDL defines a function in the conceptual model that returns the numbers of years since an instance of a `Book` (in the diagram above) was published.</span></span>  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a><span data-ttu-id="fb4cf-121">См. также</span><span class="sxs-lookup"><span data-stu-id="fb4cf-121">See also</span></span>

- [<span data-ttu-id="fb4cf-122">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="fb4cf-122">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="fb4cf-123">Сущностная модель данных</span><span class="sxs-lookup"><span data-stu-id="fb4cf-123">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="fb4cf-124">EDM: Примитивные типы данных</span><span class="sxs-lookup"><span data-stu-id="fb4cf-124">Entity Data Model: Primitive Data Types</span></span>](entity-data-model-primitive-data-types.md)
