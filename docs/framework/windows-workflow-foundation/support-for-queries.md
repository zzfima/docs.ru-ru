---
title: Поддержка запросов
ms.date: 03/30/2017
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
ms.openlocfilehash: 30695fcd791a0d69c31a897068d69838c80c3957
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641519"
---
# <a name="support-for-queries"></a><span data-ttu-id="24765-102">Поддержка запросов</span><span class="sxs-lookup"><span data-stu-id="24765-102">Support for Queries</span></span>
<span data-ttu-id="24765-103">Хранилище экземпляров рабочих процессов SQL записывает набор известных свойств в хранилище.</span><span class="sxs-lookup"><span data-stu-id="24765-103">The SQL Workflow Instance Store records a set of well-known properties in the store.</span></span> <span data-ttu-id="24765-104">Пользователи могут выполнить запрос экземпляров на основе этих свойств.</span><span class="sxs-lookup"><span data-stu-id="24765-104">Users can query for instances based on these properties.</span></span> <span data-ttu-id="24765-105">В следующем списке приведены некоторые из этих известных свойств.</span><span class="sxs-lookup"><span data-stu-id="24765-105">The following list contains some of these well-known properties:</span></span>  
  
- <span data-ttu-id="24765-106">**Имя сайта.**</span><span class="sxs-lookup"><span data-stu-id="24765-106">**Site Name.**</span></span> <span data-ttu-id="24765-107">Имя веб-узла, содержащего службу.</span><span class="sxs-lookup"><span data-stu-id="24765-107">Name of the Web site that contains the service.</span></span>  
  
- <span data-ttu-id="24765-108">**Путь относительно приложения.**</span><span class="sxs-lookup"><span data-stu-id="24765-108">**Relative Application Path.**</span></span> <span data-ttu-id="24765-109">Путь приложения относительно веб-узла.</span><span class="sxs-lookup"><span data-stu-id="24765-109">Path of the application relative to the Web site.</span></span>  
  
- <span data-ttu-id="24765-110">**Относительный путь службы.**</span><span class="sxs-lookup"><span data-stu-id="24765-110">**Relative Service Path.**</span></span> <span data-ttu-id="24765-111">Путь службы относительно приложения.</span><span class="sxs-lookup"><span data-stu-id="24765-111">Path of the service relative to the application.</span></span>  
  
- <span data-ttu-id="24765-112">**Имя службы.**</span><span class="sxs-lookup"><span data-stu-id="24765-112">**Service Name.**</span></span> <span data-ttu-id="24765-113">Имя службы.</span><span class="sxs-lookup"><span data-stu-id="24765-113">Name of the service.</span></span>  
  
- <span data-ttu-id="24765-114">**Пространство имен службы.**</span><span class="sxs-lookup"><span data-stu-id="24765-114">**Service Namespace.**</span></span> <span data-ttu-id="24765-115">Имя пространства имен, которое использует служба.</span><span class="sxs-lookup"><span data-stu-id="24765-115">Name of the namespace that the service uses.</span></span>  
  
- <span data-ttu-id="24765-116">**Текущий компьютер.**</span><span class="sxs-lookup"><span data-stu-id="24765-116">**Current Machine.**</span></span>  
  
- <span data-ttu-id="24765-117">**Последний компьютер**.</span><span class="sxs-lookup"><span data-stu-id="24765-117">**Last Machine**.</span></span> <span data-ttu-id="24765-118">Компьютер, на котором экземпляр службы рабочего процесса был запущен последний раз.</span><span class="sxs-lookup"><span data-stu-id="24765-118">The computer on which the workflow service instance ran the last time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24765-119">Для резидентных сценариев, использующих узел службы рабочего процесса, заполняются только последние четыре свойства.</span><span class="sxs-lookup"><span data-stu-id="24765-119">For self-hosted scenarios using Workflow Service Host, only the last four properties are populated.</span></span> <span data-ttu-id="24765-120">Для сценариев приложения рабочего процесса заполняется только последнее свойство.</span><span class="sxs-lookup"><span data-stu-id="24765-120">For Workflow Application scenarios, only the last property is populated.</span></span>  
  
 <span data-ttu-id="24765-121">Среда выполнения рабочего процесса предоставляет значения для первых трех свойств.</span><span class="sxs-lookup"><span data-stu-id="24765-121">The workflow runtime supplies values for the first three properties.</span></span> <span data-ttu-id="24765-122">Узел службы рабочего процесса предоставляет значение для **Причина приостановки** свойство.</span><span class="sxs-lookup"><span data-stu-id="24765-122">The workflow service host supplies the value for the **Suspend Reason** property.</span></span> <span data-ttu-id="24765-123">Store экземпляра рабочего процесса SQL, сам предоставляет значения для **последний обновленный компьютер** свойство.</span><span class="sxs-lookup"><span data-stu-id="24765-123">The SQL Workflow Instance Store itself supplies values for the **Last Updated Machine** property.</span></span>  
  
 <span data-ttu-id="24765-124">Возможность хранилища экземпляров рабочих процессов SQL также позволяет указать пользовательские свойства, значения которых требуется сохранять в базе данных сохраняемости и которые будут в дальнейшем использованы в запросах.</span><span class="sxs-lookup"><span data-stu-id="24765-124">The SQL Workflow Instance Store feature also lets you specify the custom properties for which you want to store the values in the persistence database and that you want to use in queries.</span></span> <span data-ttu-id="24765-125">Дополнительные сведения о пользовательских повышениях см. в разделе [расширяемости Store](store-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="24765-125">For more information about custom promotions, see [Store Extensibility](store-extensibility.md).</span></span>  
  
## <a name="views"></a><span data-ttu-id="24765-126">Представления</span><span class="sxs-lookup"><span data-stu-id="24765-126">Views</span></span>  
 <span data-ttu-id="24765-127">Хранилище экземпляров содержит следующие представления.</span><span class="sxs-lookup"><span data-stu-id="24765-127">The instance store contains the following views.</span></span> <span data-ttu-id="24765-128">См. в разделе [схемы базы данных сохраняемости](persistence-database-schema.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="24765-128">See [Persistence Database Schema](persistence-database-schema.md) for further details.</span></span>  
  
### <a name="the-instances-view"></a><span data-ttu-id="24765-129">Представление экземпляров</span><span class="sxs-lookup"><span data-stu-id="24765-129">The Instances View</span></span>  
 <span data-ttu-id="24765-130">Представление экземпляров содержит следующие поля:</span><span class="sxs-lookup"><span data-stu-id="24765-130">The Instances view contains the following fields:</span></span>  
  
1. <span data-ttu-id="24765-131">**Идентификатор**</span><span class="sxs-lookup"><span data-stu-id="24765-131">**Id**</span></span>  
  
2. <span data-ttu-id="24765-132">**PendingTimer**</span><span class="sxs-lookup"><span data-stu-id="24765-132">**PendingTimer**</span></span>  
  
3. <span data-ttu-id="24765-133">**CreationTime**</span><span class="sxs-lookup"><span data-stu-id="24765-133">**CreationTime**</span></span>  
  
4. <span data-ttu-id="24765-134">**LastUpdatedTime**</span><span class="sxs-lookup"><span data-stu-id="24765-134">**LastUpdatedTime**</span></span>  
  
5. <span data-ttu-id="24765-135">**ServiceDeploymentId**</span><span class="sxs-lookup"><span data-stu-id="24765-135">**ServiceDeploymentId**</span></span>  
  
6. <span data-ttu-id="24765-136">**SuspensionExceptionName**</span><span class="sxs-lookup"><span data-stu-id="24765-136">**SuspensionExceptionName**</span></span>  
  
7. <span data-ttu-id="24765-137">**SuspensionReason**</span><span class="sxs-lookup"><span data-stu-id="24765-137">**SuspensionReason**</span></span>  
  
8. <span data-ttu-id="24765-138">**ActiveBookmarks**</span><span class="sxs-lookup"><span data-stu-id="24765-138">**ActiveBookmarks**</span></span>  
  
9. <span data-ttu-id="24765-139">**CurrentMachine**</span><span class="sxs-lookup"><span data-stu-id="24765-139">**CurrentMachine**</span></span>  
  
10. <span data-ttu-id="24765-140">**LastMachine**</span><span class="sxs-lookup"><span data-stu-id="24765-140">**LastMachine**</span></span>  
  
11. <span data-ttu-id="24765-141">**ExecutionStatus**</span><span class="sxs-lookup"><span data-stu-id="24765-141">**ExecutionStatus**</span></span>  
  
12. <span data-ttu-id="24765-142">**IsInitialized**</span><span class="sxs-lookup"><span data-stu-id="24765-142">**IsInitialized**</span></span>  
  
13. <span data-ttu-id="24765-143">**IsSuspended**</span><span class="sxs-lookup"><span data-stu-id="24765-143">**IsSuspended**</span></span>  
  
14. <span data-ttu-id="24765-144">**IsCompleted**</span><span class="sxs-lookup"><span data-stu-id="24765-144">**IsCompleted**</span></span>  
  
15. <span data-ttu-id="24765-145">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="24765-145">**EncodingOption**</span></span>  
  
16. <span data-ttu-id="24765-146">**ReadWritePrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="24765-146">**ReadWritePrimitiveDataProperties**</span></span>  
  
17. <span data-ttu-id="24765-147">**WriteOnlyPrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="24765-147">**WriteOnlyPrimitiveDataProperties**</span></span>  
  
18. <span data-ttu-id="24765-148">**ReadWriteComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="24765-148">**ReadWriteComplexDataProperties**</span></span>  
  
19. <span data-ttu-id="24765-149">**WriteOnlyComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="24765-149">**WriteOnlyComplexDataProperties**</span></span>  
  
### <a name="the-servicedeployments-view"></a><span data-ttu-id="24765-150">Представление ServiceDeployments</span><span class="sxs-lookup"><span data-stu-id="24765-150">The ServiceDeployments view</span></span>  
 <span data-ttu-id="24765-151">Представление ServiceDeployments содержит следующие поля:</span><span class="sxs-lookup"><span data-stu-id="24765-151">The ServiceDeployments view contains the following fields:</span></span>  
  
1. <span data-ttu-id="24765-152">**Имя сайта:**</span><span class="sxs-lookup"><span data-stu-id="24765-152">**SiteName**</span></span>  
  
2. <span data-ttu-id="24765-153">**RelativeServicePath**</span><span class="sxs-lookup"><span data-stu-id="24765-153">**RelativeServicePath**</span></span>  
  
3. <span data-ttu-id="24765-154">**RelativeApplicationPath**</span><span class="sxs-lookup"><span data-stu-id="24765-154">**RelativeApplicationPath**</span></span>  
  
4. <span data-ttu-id="24765-155">**ServiceName**</span><span class="sxs-lookup"><span data-stu-id="24765-155">**ServiceName**</span></span>  
  
5. <span data-ttu-id="24765-156">**ServiceNamespace**</span><span class="sxs-lookup"><span data-stu-id="24765-156">**ServiceNamespace**</span></span>  
  
### <a name="the-instancepromotedproperties-view"></a><span data-ttu-id="24765-157">Представление InstancePromotedProperties</span><span class="sxs-lookup"><span data-stu-id="24765-157">The InstancePromotedProperties view</span></span>  
 <span data-ttu-id="24765-158">Представление InstancePromotedProperties содержит следующие поля.</span><span class="sxs-lookup"><span data-stu-id="24765-158">The InstancePromotedProperties view contains the following fields.</span></span> <span data-ttu-id="24765-159">Дополнительные сведения о свойствах повышенного уровня см. в разделе [расширяемости Store](store-extensibility.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="24765-159">For details on promoted properties, see the [Store Extensibility](store-extensibility.md) topic.</span></span>  
  
1. <span data-ttu-id="24765-160">**InstanceId**</span><span class="sxs-lookup"><span data-stu-id="24765-160">**InstanceId**</span></span>  
  
2. <span data-ttu-id="24765-161">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="24765-161">**EncodingOption**</span></span>  
  
3. <span data-ttu-id="24765-162">**PromotionName**</span><span class="sxs-lookup"><span data-stu-id="24765-162">**PromotionName**</span></span>  
  
4. <span data-ttu-id="24765-163">**Значение #** (ряд полей от **значение1** для **Value64**).</span><span class="sxs-lookup"><span data-stu-id="24765-163">**Value#** (a range of fields from **Value1** to **Value64**).</span></span>
