---
title: Поддержка запросов
ms.date: 03/30/2017
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
ms.openlocfilehash: e281b5ae7a41bd282f8e7c7eb9db6f99ef5487f3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948941"
---
# <a name="support-for-queries"></a><span data-ttu-id="53a2c-102">Поддержка запросов</span><span class="sxs-lookup"><span data-stu-id="53a2c-102">Support for Queries</span></span>
<span data-ttu-id="53a2c-103">Хранилище экземпляров рабочих процессов SQL записывает набор известных свойств в хранилище.</span><span class="sxs-lookup"><span data-stu-id="53a2c-103">The SQL Workflow Instance Store records a set of well-known properties in the store.</span></span> <span data-ttu-id="53a2c-104">Пользователи могут выполнить запрос экземпляров на основе этих свойств.</span><span class="sxs-lookup"><span data-stu-id="53a2c-104">Users can query for instances based on these properties.</span></span> <span data-ttu-id="53a2c-105">В следующем списке приведены некоторые из этих известных свойств.</span><span class="sxs-lookup"><span data-stu-id="53a2c-105">The following list contains some of these well-known properties:</span></span>  
  
- <span data-ttu-id="53a2c-106">**Имя сайта.**</span><span class="sxs-lookup"><span data-stu-id="53a2c-106">**Site Name.**</span></span> <span data-ttu-id="53a2c-107">Имя веб-узла, содержащего службу.</span><span class="sxs-lookup"><span data-stu-id="53a2c-107">Name of the Web site that contains the service.</span></span>  
  
- <span data-ttu-id="53a2c-108">**Относительный путь приложения.**</span><span class="sxs-lookup"><span data-stu-id="53a2c-108">**Relative Application Path.**</span></span> <span data-ttu-id="53a2c-109">Путь приложения относительно веб-узла.</span><span class="sxs-lookup"><span data-stu-id="53a2c-109">Path of the application relative to the Web site.</span></span>  
  
- <span data-ttu-id="53a2c-110">**Относительный путь службы.**</span><span class="sxs-lookup"><span data-stu-id="53a2c-110">**Relative Service Path.**</span></span> <span data-ttu-id="53a2c-111">Путь службы относительно приложения.</span><span class="sxs-lookup"><span data-stu-id="53a2c-111">Path of the service relative to the application.</span></span>  
  
- <span data-ttu-id="53a2c-112">**Имя службы.**</span><span class="sxs-lookup"><span data-stu-id="53a2c-112">**Service Name.**</span></span> <span data-ttu-id="53a2c-113">Имя службы.</span><span class="sxs-lookup"><span data-stu-id="53a2c-113">Name of the service.</span></span>  
  
- <span data-ttu-id="53a2c-114">**Пространство имен службы.**</span><span class="sxs-lookup"><span data-stu-id="53a2c-114">**Service Namespace.**</span></span> <span data-ttu-id="53a2c-115">Имя пространства имен, которое использует служба.</span><span class="sxs-lookup"><span data-stu-id="53a2c-115">Name of the namespace that the service uses.</span></span>  
  
- <span data-ttu-id="53a2c-116">**Текущий компьютер.**</span><span class="sxs-lookup"><span data-stu-id="53a2c-116">**Current Machine.**</span></span>  
  
- <span data-ttu-id="53a2c-117">**Последний компьютер**.</span><span class="sxs-lookup"><span data-stu-id="53a2c-117">**Last Machine**.</span></span> <span data-ttu-id="53a2c-118">Компьютер, на котором экземпляр службы рабочего процесса был запущен последний раз.</span><span class="sxs-lookup"><span data-stu-id="53a2c-118">The computer on which the workflow service instance ran the last time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53a2c-119">Для резидентных сценариев, использующих узел службы рабочего процесса, заполняются только последние четыре свойства.</span><span class="sxs-lookup"><span data-stu-id="53a2c-119">For self-hosted scenarios using Workflow Service Host, only the last four properties are populated.</span></span> <span data-ttu-id="53a2c-120">Для сценариев приложения рабочего процесса заполняется только последнее свойство.</span><span class="sxs-lookup"><span data-stu-id="53a2c-120">For Workflow Application scenarios, only the last property is populated.</span></span>  
  
 <span data-ttu-id="53a2c-121">Среда выполнения рабочего процесса предоставляет значения для первых трех свойств.</span><span class="sxs-lookup"><span data-stu-id="53a2c-121">The workflow runtime supplies values for the first three properties.</span></span> <span data-ttu-id="53a2c-122">Узел службы рабочего процесса предоставляет значение для свойства **Причина приостановки** .</span><span class="sxs-lookup"><span data-stu-id="53a2c-122">The workflow service host supplies the value for the **Suspend Reason** property.</span></span> <span data-ttu-id="53a2c-123">Хранилище экземпляров рабочих процессов SQL предоставляет значения для **последнего обновленного свойства компьютера** .</span><span class="sxs-lookup"><span data-stu-id="53a2c-123">The SQL Workflow Instance Store itself supplies values for the **Last Updated Machine** property.</span></span>  
  
 <span data-ttu-id="53a2c-124">Возможность хранилища экземпляров рабочих процессов SQL также позволяет указать пользовательские свойства, значения которых требуется сохранять в базе данных сохраняемости и которые будут в дальнейшем использованы в запросах.</span><span class="sxs-lookup"><span data-stu-id="53a2c-124">The SQL Workflow Instance Store feature also lets you specify the custom properties for which you want to store the values in the persistence database and that you want to use in queries.</span></span> <span data-ttu-id="53a2c-125">Дополнительные сведения о пользовательских рекламных акциях см. в разделе [Хранение расширяемости](store-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="53a2c-125">For more information about custom promotions, see [Store Extensibility](store-extensibility.md).</span></span>  
  
## <a name="views"></a><span data-ttu-id="53a2c-126">Представления</span><span class="sxs-lookup"><span data-stu-id="53a2c-126">Views</span></span>  
 <span data-ttu-id="53a2c-127">Хранилище экземпляров содержит следующие представления.</span><span class="sxs-lookup"><span data-stu-id="53a2c-127">The instance store contains the following views.</span></span> <span data-ttu-id="53a2c-128">Дополнительные сведения см. в разделе [схема базы данных сохраняемости](persistence-database-schema.md) .</span><span class="sxs-lookup"><span data-stu-id="53a2c-128">See [Persistence Database Schema](persistence-database-schema.md) for further details.</span></span>  
  
### <a name="the-instances-view"></a><span data-ttu-id="53a2c-129">Представление экземпляров</span><span class="sxs-lookup"><span data-stu-id="53a2c-129">The Instances View</span></span>  
 <span data-ttu-id="53a2c-130">Представление экземпляров содержит следующие поля:</span><span class="sxs-lookup"><span data-stu-id="53a2c-130">The Instances view contains the following fields:</span></span>  
  
1. <span data-ttu-id="53a2c-131">**Идентификатор**</span><span class="sxs-lookup"><span data-stu-id="53a2c-131">**Id**</span></span>  
  
2. <span data-ttu-id="53a2c-132">**пендингтимер**</span><span class="sxs-lookup"><span data-stu-id="53a2c-132">**PendingTimer**</span></span>  
  
3. <span data-ttu-id="53a2c-133">**CreationTime**</span><span class="sxs-lookup"><span data-stu-id="53a2c-133">**CreationTime**</span></span>  
  
4. <span data-ttu-id="53a2c-134">**LastUpdatedTime**</span><span class="sxs-lookup"><span data-stu-id="53a2c-134">**LastUpdatedTime**</span></span>  
  
5. <span data-ttu-id="53a2c-135">**сервицедеплойментид**</span><span class="sxs-lookup"><span data-stu-id="53a2c-135">**ServiceDeploymentId**</span></span>  
  
6. <span data-ttu-id="53a2c-136">**суспенсионексцептионнаме**</span><span class="sxs-lookup"><span data-stu-id="53a2c-136">**SuspensionExceptionName**</span></span>  
  
7. <span data-ttu-id="53a2c-137">**суспенсионреасон**</span><span class="sxs-lookup"><span data-stu-id="53a2c-137">**SuspensionReason**</span></span>  
  
8. <span data-ttu-id="53a2c-138">**активебукмаркс**</span><span class="sxs-lookup"><span data-stu-id="53a2c-138">**ActiveBookmarks**</span></span>  
  
9. <span data-ttu-id="53a2c-139">**куррентмачине**</span><span class="sxs-lookup"><span data-stu-id="53a2c-139">**CurrentMachine**</span></span>  
  
10. <span data-ttu-id="53a2c-140">**ластмачине**</span><span class="sxs-lookup"><span data-stu-id="53a2c-140">**LastMachine**</span></span>  
  
11. <span data-ttu-id="53a2c-141">**ексекутионстатус**</span><span class="sxs-lookup"><span data-stu-id="53a2c-141">**ExecutionStatus**</span></span>  
  
12. <span data-ttu-id="53a2c-142">**IsInitialized**</span><span class="sxs-lookup"><span data-stu-id="53a2c-142">**IsInitialized**</span></span>  
  
13. <span data-ttu-id="53a2c-143">**Приостановка**</span><span class="sxs-lookup"><span data-stu-id="53a2c-143">**IsSuspended**</span></span>  
  
14. <span data-ttu-id="53a2c-144">**Соответствующие IsCompleted**</span><span class="sxs-lookup"><span data-stu-id="53a2c-144">**IsCompleted**</span></span>  
  
15. <span data-ttu-id="53a2c-145">**енкодингоптион**</span><span class="sxs-lookup"><span data-stu-id="53a2c-145">**EncodingOption**</span></span>  
  
16. <span data-ttu-id="53a2c-146">**реадвритепримитиведатапропертиес**</span><span class="sxs-lookup"><span data-stu-id="53a2c-146">**ReadWritePrimitiveDataProperties**</span></span>  
  
17. <span data-ttu-id="53a2c-147">**вритеонлипримитиведатапропертиес**</span><span class="sxs-lookup"><span data-stu-id="53a2c-147">**WriteOnlyPrimitiveDataProperties**</span></span>  
  
18. <span data-ttu-id="53a2c-148">**реадвритекомплексдатапропертиес**</span><span class="sxs-lookup"><span data-stu-id="53a2c-148">**ReadWriteComplexDataProperties**</span></span>  
  
19. <span data-ttu-id="53a2c-149">**вритеонликомплексдатапропертиес**</span><span class="sxs-lookup"><span data-stu-id="53a2c-149">**WriteOnlyComplexDataProperties**</span></span>  
  
### <a name="the-servicedeployments-view"></a><span data-ttu-id="53a2c-150">Представление ServiceDeployments</span><span class="sxs-lookup"><span data-stu-id="53a2c-150">The ServiceDeployments view</span></span>  
 <span data-ttu-id="53a2c-151">Представление ServiceDeployments содержит следующие поля:</span><span class="sxs-lookup"><span data-stu-id="53a2c-151">The ServiceDeployments view contains the following fields:</span></span>  
  
1. <span data-ttu-id="53a2c-152">**Значением**</span><span class="sxs-lookup"><span data-stu-id="53a2c-152">**SiteName**</span></span>  
  
2. <span data-ttu-id="53a2c-153">**релативесервицепас**</span><span class="sxs-lookup"><span data-stu-id="53a2c-153">**RelativeServicePath**</span></span>  
  
3. <span data-ttu-id="53a2c-154">**релативеаппликатионпас**</span><span class="sxs-lookup"><span data-stu-id="53a2c-154">**RelativeApplicationPath**</span></span>  
  
4. <span data-ttu-id="53a2c-155">**Служба**</span><span class="sxs-lookup"><span data-stu-id="53a2c-155">**ServiceName**</span></span>  
  
5. <span data-ttu-id="53a2c-156">**сервиценамеспаце**</span><span class="sxs-lookup"><span data-stu-id="53a2c-156">**ServiceNamespace**</span></span>  
  
### <a name="the-instancepromotedproperties-view"></a><span data-ttu-id="53a2c-157">Представление InstancePromotedProperties</span><span class="sxs-lookup"><span data-stu-id="53a2c-157">The InstancePromotedProperties view</span></span>  
 <span data-ttu-id="53a2c-158">Представление InstancePromotedProperties содержит следующие поля.</span><span class="sxs-lookup"><span data-stu-id="53a2c-158">The InstancePromotedProperties view contains the following fields.</span></span> <span data-ttu-id="53a2c-159">Дополнительные сведения о повышенных свойствах см. в статье о [расширении хранилища](store-extensibility.md) .</span><span class="sxs-lookup"><span data-stu-id="53a2c-159">For details on promoted properties, see the [Store Extensibility](store-extensibility.md) topic.</span></span>  
  
1. <span data-ttu-id="53a2c-160">**InstanceId**</span><span class="sxs-lookup"><span data-stu-id="53a2c-160">**InstanceId**</span></span>  
  
2. <span data-ttu-id="53a2c-161">**енкодингоптион**</span><span class="sxs-lookup"><span data-stu-id="53a2c-161">**EncodingOption**</span></span>  
  
3. <span data-ttu-id="53a2c-162">**промотионнаме**</span><span class="sxs-lookup"><span data-stu-id="53a2c-162">**PromotionName**</span></span>  
  
4. <span data-ttu-id="53a2c-163">**Значение #** (диапазон полей от **Значение1** до **Value64**).</span><span class="sxs-lookup"><span data-stu-id="53a2c-163">**Value#** (a range of fields from **Value1** to **Value64**).</span></span>
