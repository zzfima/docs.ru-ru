---
title: '&lt;serviceThrottling&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aea9702b5376e584c9598be1a6270dbe0cc4c717
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicethrottlinggt"></a><span data-ttu-id="1d11c-102">&lt;serviceThrottling&gt;</span><span class="sxs-lookup"><span data-stu-id="1d11c-102">&lt;serviceThrottling&gt;</span></span>
<span data-ttu-id="1d11c-103">Задает механизм настройки службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1d11c-103">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="1d11c-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1d11c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1d11c-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="1d11c-105">\<behaviors></span></span>  
<span data-ttu-id="1d11c-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1d11c-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="1d11c-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="1d11c-107">\<behavior></span></span>  
<span data-ttu-id="1d11c-108">\<serviceThrottling ></span><span class="sxs-lookup"><span data-stu-id="1d11c-108">\<serviceThrottling></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d11c-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d11c-109">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"  
    maxConcurrentInstances="Integer"  
    maxConcurrentSessions="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d11c-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1d11c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1d11c-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1d11c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d11c-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1d11c-112">Attributes</span></span>  
  
|<span data-ttu-id="1d11c-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1d11c-113">Attribute</span></span>|<span data-ttu-id="1d11c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1d11c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1d11c-115">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="1d11c-115">maxConcurrentCalls</span></span>|<span data-ttu-id="1d11c-116">Положительное целое число, ограничивающее количество сообщений, обрабатываемых в текущий момент в <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="1d11c-116">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="1d11c-117">Вызовы, превышающие этот предел, ставятся в очередь.</span><span class="sxs-lookup"><span data-stu-id="1d11c-117">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="1d11c-118">Установка этого значения на 0 эквивалентна его установке на Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="1d11c-118">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="1d11c-119">Значение по умолчанию: 16 * количество процессоров.</span><span class="sxs-lookup"><span data-stu-id="1d11c-119">The default is 16 * processor count.</span></span>|  
|<span data-ttu-id="1d11c-120">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="1d11c-120">maxConcurrentInstances</span></span>|<span data-ttu-id="1d11c-121">Положительное целое число, ограничивающее количество объектов <xref:System.ServiceModel.InstanceContext>, одновременно выполняющихся в <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="1d11c-121">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="1d11c-122">Запросы на создание дополнительных экземпляров ставятся в очередь и выполняются, когда происходит отступление от предельной величины.</span><span class="sxs-lookup"><span data-stu-id="1d11c-122">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="1d11c-123">Значение по умолчанию: сумма maxConcurrentSessions и MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="1d11c-123">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="1d11c-124">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="1d11c-124">maxConcurrentSessions</span></span>|<span data-ttu-id="1d11c-125">Положительное целое число, ограничивающее количество сеансов, которое может принять объект <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="1d11c-125">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="1d11c-126">Служба принимает соединения сверх предела, но только каналы, количество которых меньше предельного значения, являются активными (сообщения считываются из канала).</span><span class="sxs-lookup"><span data-stu-id="1d11c-126">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="1d11c-127">Установка этого значения на 0 эквивалентна его установке на Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="1d11c-127">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="1d11c-128">Значение по умолчанию: 100 * количество процессоров.</span><span class="sxs-lookup"><span data-stu-id="1d11c-128">The default is 100 * processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1d11c-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1d11c-129">Child Elements</span></span>  
 <span data-ttu-id="1d11c-130">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1d11c-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1d11c-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1d11c-131">Parent Elements</span></span>  
  
|<span data-ttu-id="1d11c-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="1d11c-132">Element</span></span>|<span data-ttu-id="1d11c-133">Описание</span><span class="sxs-lookup"><span data-stu-id="1d11c-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d11c-134">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="1d11c-134">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="1d11c-135">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="1d11c-135">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d11c-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="1d11c-136">Remarks</span></span>  
 <span data-ttu-id="1d11c-137">Элементы регулирования ограничивают число одновременных вызовов, экземпляров или сеансов, чтобы предотвратить чрезмерное потребление ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1d11c-137">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="1d11c-138">Каждый раз при достижении значений атрибутов происходит запись трассировки.</span><span class="sxs-lookup"><span data-stu-id="1d11c-138">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="1d11c-139">Первая трассировка записывается как предупреждение.</span><span class="sxs-lookup"><span data-stu-id="1d11c-139">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d11c-140">Пример</span><span class="sxs-lookup"><span data-stu-id="1d11c-140">Example</span></span>  
 <span data-ttu-id="1d11c-141">В следующем примере конфигурации служба допускает максимум 2 одновременно выполняющихся вызова, а максимальное количество одновременно присутствующих экземпляров равно 10.</span><span class="sxs-lookup"><span data-stu-id="1d11c-141">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="1d11c-142">Подробный пример выполнения данного примера см. в разделе [регулирование](../../../../../docs/framework/wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="1d11c-142">For a detailed example of running this example, see [Throttling](../../../../../docs/framework/wcf/samples/throttling.md).</span></span>  
  
```xml  
<behaviors>   
  <serviceBehaviors>   
    <behavior name="CalculatorServiceBehavior">   
      <serviceDebug includeExceptionDetailInFaults="False" />   
      <serviceMetadata httpGetEnabled="True"/>   
      <!-- Specify throttling behavior -->  
      <serviceThrottling maxConcurrentCalls="2"   
           maxConcurrentInstances="10"/>   
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1d11c-143">См. также</span><span class="sxs-lookup"><span data-stu-id="1d11c-143">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>  
 <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>  
 [<span data-ttu-id="1d11c-144">Использование ServiceThrottlingBehavior для управления производительностью службы WCF</span><span class="sxs-lookup"><span data-stu-id="1d11c-144">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../../../docs/framework/wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
