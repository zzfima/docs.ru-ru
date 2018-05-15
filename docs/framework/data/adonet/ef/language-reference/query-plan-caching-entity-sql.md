---
title: Кэширование плана запроса (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 90b0c685-5ef2-461b-98b4-c3c0a2b253c7
ms.openlocfilehash: 0e00d7f9382fca2af630a8e1d50a5cde5178da05
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="query-plan-caching-entity-sql"></a><span data-ttu-id="d52e1-102">Кэширование плана запроса (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d52e1-102">Query Plan Caching (Entity SQL)</span></span>
<span data-ttu-id="d52e1-103">При каждой попытке выполнения запроса конвейер запросов обращается в кэш планов запросов, чтобы определить, что конкретный запрос уже скомпилирован и доступен.</span><span class="sxs-lookup"><span data-stu-id="d52e1-103">Whenever an attempt to execute a query is made, the query pipeline looks up its query plan cache to see whether the exact query is already compiled and available.</span></span> <span data-ttu-id="d52e1-104">Если это так, то кэшированный план используется повторно вместо построения нового плана.</span><span class="sxs-lookup"><span data-stu-id="d52e1-104">If so, it reuses the cached plan rather than building a new one.</span></span> <span data-ttu-id="d52e1-105">Если совпадение в кэше планов запросов не обнаружено, запрос компилируется и кэшируется.</span><span class="sxs-lookup"><span data-stu-id="d52e1-105">If a match is not found in the query plan cache, the query is compiled and cached.</span></span> <span data-ttu-id="d52e1-106">Запрос идентифицируется его текстом [!INCLUDE[esql](../../../../../../includes/esql-md.md)] и коллекцией параметров (имен и типов).</span><span class="sxs-lookup"><span data-stu-id="d52e1-106">A query is identified by its [!INCLUDE[esql](../../../../../../includes/esql-md.md)] text and parameter collection (names and types).</span></span> <span data-ttu-id="d52e1-107">Все текстовые сравнения выполняются с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="d52e1-107">All text comparisons are case-sensitive.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="d52e1-108">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="d52e1-108">Configuration</span></span>  
 <span data-ttu-id="d52e1-109">Кэширование планов запросов можно настроить с помощью <xref:System.Data.EntityClient.EntityCommand>.</span><span class="sxs-lookup"><span data-stu-id="d52e1-109">Query plan caching is configurable through the <xref:System.Data.EntityClient.EntityCommand>.</span></span>  
  
 <span data-ttu-id="d52e1-110">Чтобы включить или выключить кэширование планов запросов с помощью свойства <xref:System.Data.EntityClient.EntityCommand.EnablePlanCaching%2A?displayProperty=nameWithType>, назначьте этому свойству значение `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="d52e1-110">To enable or disable query plan caching through <xref:System.Data.EntityClient.EntityCommand.EnablePlanCaching%2A?displayProperty=nameWithType>, set this property to `true` or `false`.</span></span> <span data-ttu-id="d52e1-111">Отключение кэширования планов для отдельных динамических запросов, которые вряд ли будут использованы повторно, повышает производительность.</span><span class="sxs-lookup"><span data-stu-id="d52e1-111">Disabling plan caching for individual dynamic queries that are unlikely to be used more then once improves performance.</span></span>  
  
 <span data-ttu-id="d52e1-112">Можно включить кэширование планов запросов с помощью <xref:System.Data.Objects.ObjectQuery.EnablePlanCaching%2A>.</span><span class="sxs-lookup"><span data-stu-id="d52e1-112">You can enable query plan caching through <xref:System.Data.Objects.ObjectQuery.EnablePlanCaching%2A>.</span></span>  
  
## <a name="recommended-practice"></a><span data-ttu-id="d52e1-113">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="d52e1-113">Recommended Practice</span></span>  
 <span data-ttu-id="d52e1-114">Как правило, следует избегать динамических запросов.</span><span class="sxs-lookup"><span data-stu-id="d52e1-114">Dynamic queries should be avoided, in general.</span></span> <span data-ttu-id="d52e1-115">Динамический запрос в следующем примере уязвим для атак путем внедрения кода SQL, так как входные данные пользователя принимаются напрямую без проверки.</span><span class="sxs-lookup"><span data-stu-id="d52e1-115">The following dynamic query example is vulnerable to SQL injection attacks, because it takes user input directly without any validation.</span></span>  
  
 `"SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp WHERE sp.EmployeeID = " + employeeTextBox.Text;`  
  
 <span data-ttu-id="d52e1-116">Если используются динамически формируемые запросы, подумайте об отключении кэширования плана запроса, чтобы избежать ненужного расходования памяти для записей кэша, которые вряд ли будут использоваться повторно.</span><span class="sxs-lookup"><span data-stu-id="d52e1-116">If you do use dynamically generated queries, consider disabling query plan caching to avoid unnecessary memory consumption for cache entries that are unlikely to be reused.</span></span>  
  
 <span data-ttu-id="d52e1-117">Кэширование планов запросов для статических запросов и параметризованных запросов может увеличить производительность.</span><span class="sxs-lookup"><span data-stu-id="d52e1-117">Query plan caching on static queries and parameterized queries can provide performance benefits.</span></span> <span data-ttu-id="d52e1-118">Ниже приводится пример статического запроса:</span><span class="sxs-lookup"><span data-stu-id="d52e1-118">The following is an example of a static query:</span></span>  
  
```  
"SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp";  
```  
  
 <span data-ttu-id="d52e1-119">Для правильного сопоставления запросов кэшу планов запросов они должны соответствовать следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="d52e1-119">For queries to be matched properly by the query plan cache, they should comply with the following requirements:</span></span>  
  
-   <span data-ttu-id="d52e1-120">Текст запроса должен быть постоянным шаблоном, предпочтительно постоянной строкой или ресурсом.</span><span class="sxs-lookup"><span data-stu-id="d52e1-120">Query text should be a constant pattern, preferably a constant string or a resource.</span></span>  
  
-   <span data-ttu-id="d52e1-121">Экземпляр <xref:System.Data.EntityClient.EntityParameter> или <xref:System.Data.Objects.ObjectParameter> должен быть использован всегда, когда нужно передать введенное пользователем значение.</span><span class="sxs-lookup"><span data-stu-id="d52e1-121"><xref:System.Data.EntityClient.EntityParameter> or <xref:System.Data.Objects.ObjectParameter> should be used wherever a user-supplied value must be passed.</span></span>  
  
 <span data-ttu-id="d52e1-122">Необходимо избегать следующих шаблонов запросов, которые напрасно занимают слоты в кэше планов запросов.</span><span class="sxs-lookup"><span data-stu-id="d52e1-122">You should avoid the following query patterns, which unnecessarily consume slots in the query plan cache:</span></span>  
  
-   <span data-ttu-id="d52e1-123">Изменение регистра символов в тексте.</span><span class="sxs-lookup"><span data-stu-id="d52e1-123">Changes to letter case in the text.</span></span>  
  
-   <span data-ttu-id="d52e1-124">Изменение пробельных символов.</span><span class="sxs-lookup"><span data-stu-id="d52e1-124">Changes to white space.</span></span>  
  
-   <span data-ttu-id="d52e1-125">Изменение литеральных значений.</span><span class="sxs-lookup"><span data-stu-id="d52e1-125">Changes to literal values.</span></span>  
  
-   <span data-ttu-id="d52e1-126">Изменение текста внутри комментариев.</span><span class="sxs-lookup"><span data-stu-id="d52e1-126">Changes to text inside comments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d52e1-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d52e1-127">See Also</span></span>  
 [<span data-ttu-id="d52e1-128">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d52e1-128">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
