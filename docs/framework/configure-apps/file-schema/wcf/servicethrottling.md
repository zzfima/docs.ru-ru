---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: 87952a92bab1ef7147100332bcef87b6f0534817
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270403"
---
# <a name="servicethrottling"></a><span data-ttu-id="225dd-101">\<serviceThrottling ></span><span class="sxs-lookup"><span data-stu-id="225dd-101">\<serviceThrottling></span></span>
<span data-ttu-id="225dd-102">Задает механизм настройки службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="225dd-102">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="225dd-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="225dd-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="225dd-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="225dd-104">\<behaviors></span></span>  
<span data-ttu-id="225dd-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="225dd-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="225dd-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="225dd-106">\<behavior></span></span>  
<span data-ttu-id="225dd-107">\<serviceThrottling ></span><span class="sxs-lookup"><span data-stu-id="225dd-107">\<serviceThrottling></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="225dd-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="225dd-108">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="225dd-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="225dd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="225dd-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="225dd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="225dd-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="225dd-111">Attributes</span></span>  
  
|<span data-ttu-id="225dd-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="225dd-112">Attribute</span></span>|<span data-ttu-id="225dd-113">Описание</span><span class="sxs-lookup"><span data-stu-id="225dd-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="225dd-114">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="225dd-114">maxConcurrentCalls</span></span>|<span data-ttu-id="225dd-115">Положительное целое число, ограничивающее количество сообщений, обрабатываемых в текущий момент в <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="225dd-115">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="225dd-116">Вызовы, превышающие этот предел, ставятся в очередь.</span><span class="sxs-lookup"><span data-stu-id="225dd-116">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="225dd-117">Установка этого значения на 0 эквивалентна его установке на Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="225dd-117">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="225dd-118">Значение по умолчанию: 16 \* количество процессоров.</span><span class="sxs-lookup"><span data-stu-id="225dd-118">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="225dd-119">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="225dd-119">maxConcurrentInstances</span></span>|<span data-ttu-id="225dd-120">Положительное целое число, ограничивающее количество объектов <xref:System.ServiceModel.InstanceContext>, одновременно выполняющихся в <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="225dd-120">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="225dd-121">Запросы на создание дополнительных экземпляров ставятся в очередь и выполняются, когда происходит отступление от предельной величины.</span><span class="sxs-lookup"><span data-stu-id="225dd-121">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="225dd-122">Значение по умолчанию: сумма maxConcurrentSessions и MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="225dd-122">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="225dd-123">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="225dd-123">maxConcurrentSessions</span></span>|<span data-ttu-id="225dd-124">Положительное целое число, ограничивающее количество сеансов, которое может принять объект <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="225dd-124">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="225dd-125">Служба принимает соединения сверх предела, но только каналы, количество которых меньше предельного значения, являются активными (сообщения считываются из канала).</span><span class="sxs-lookup"><span data-stu-id="225dd-125">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="225dd-126">Установка этого значения на 0 эквивалентна его установке на Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="225dd-126">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="225dd-127">Значение по умолчанию: 100 \* количество процессоров.</span><span class="sxs-lookup"><span data-stu-id="225dd-127">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="225dd-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="225dd-128">Child Elements</span></span>  
 <span data-ttu-id="225dd-129">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="225dd-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="225dd-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="225dd-130">Parent Elements</span></span>  
  
|<span data-ttu-id="225dd-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="225dd-131">Element</span></span>|<span data-ttu-id="225dd-132">Описание:</span><span class="sxs-lookup"><span data-stu-id="225dd-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="225dd-133">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="225dd-133">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="225dd-134">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="225dd-134">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="225dd-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="225dd-135">Remarks</span></span>  
 <span data-ttu-id="225dd-136">Элементы регулирования ограничивают число одновременных вызовов, экземпляров или сеансов, чтобы предотвратить чрезмерное потребление ресурсов.</span><span class="sxs-lookup"><span data-stu-id="225dd-136">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="225dd-137">Каждый раз при достижении значений атрибутов происходит запись трассировки.</span><span class="sxs-lookup"><span data-stu-id="225dd-137">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="225dd-138">Первая трассировка записывается как предупреждение.</span><span class="sxs-lookup"><span data-stu-id="225dd-138">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="225dd-139">Пример</span><span class="sxs-lookup"><span data-stu-id="225dd-139">Example</span></span>  
 <span data-ttu-id="225dd-140">В следующем примере конфигурации служба допускает максимум 2 одновременно выполняющихся вызова, а максимальное количество одновременно присутствующих экземпляров равно 10.</span><span class="sxs-lookup"><span data-stu-id="225dd-140">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="225dd-141">Подробный пример рассмотрение этого примера, см. в разделе [регулирование](../../../../../docs/framework/wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="225dd-141">For a detailed example of running this example, see [Throttling](../../../../../docs/framework/wcf/samples/throttling.md).</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDebug includeExceptionDetailInFaults="False" />
      <serviceMetadata httpGetEnabled="True" />
      <!-- Specify throttling behavior -->
      <serviceThrottling maxConcurrentCalls="2"
                         maxConcurrentInstances="10" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="225dd-142">См. также</span><span class="sxs-lookup"><span data-stu-id="225dd-142">See also</span></span>
- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [<span data-ttu-id="225dd-143">Использование ServiceThrottlingBehavior для управления производительностью службы WCF</span><span class="sxs-lookup"><span data-stu-id="225dd-143">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../../../docs/framework/wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
