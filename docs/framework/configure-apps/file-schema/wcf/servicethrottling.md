---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: 77ed5e91f09d9e658deeb7996baaca445b4e0c90
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937111"
---
# <a name="servicethrottling"></a><span data-ttu-id="1fbcc-101">\<Сервицесроттлинг ></span><span class="sxs-lookup"><span data-stu-id="1fbcc-101">\<serviceThrottling></span></span>
<span data-ttu-id="1fbcc-102">Задает механизм настройки службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1fbcc-102">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="1fbcc-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1fbcc-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1fbcc-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="1fbcc-104">\<behaviors></span></span>  
<span data-ttu-id="1fbcc-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1fbcc-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="1fbcc-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="1fbcc-106">\<behavior></span></span>  
<span data-ttu-id="1fbcc-107">\<Сервицесроттлинг ></span><span class="sxs-lookup"><span data-stu-id="1fbcc-107">\<serviceThrottling></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fbcc-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1fbcc-108">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fbcc-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1fbcc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1fbcc-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1fbcc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fbcc-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1fbcc-111">Attributes</span></span>  
  
|<span data-ttu-id="1fbcc-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1fbcc-112">Attribute</span></span>|<span data-ttu-id="1fbcc-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1fbcc-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1fbcc-114">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="1fbcc-114">maxConcurrentCalls</span></span>|<span data-ttu-id="1fbcc-115">Положительное целое число, ограничивающее количество сообщений, обрабатываемых в текущий момент в <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="1fbcc-115">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="1fbcc-116">Вызовы, превышающие этот предел, ставятся в очередь.</span><span class="sxs-lookup"><span data-stu-id="1fbcc-116">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="1fbcc-117">Установка этого значения на 0 эквивалентна его установке на Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="1fbcc-117">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="1fbcc-118">Значение по умолчанию: 16 \* количество процессоров.</span><span class="sxs-lookup"><span data-stu-id="1fbcc-118">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="1fbcc-119">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="1fbcc-119">maxConcurrentInstances</span></span>|<span data-ttu-id="1fbcc-120">Положительное целое число, ограничивающее количество объектов <xref:System.ServiceModel.InstanceContext>, одновременно выполняющихся в <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="1fbcc-120">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="1fbcc-121">Запросы на создание дополнительных экземпляров ставятся в очередь и выполняются, когда происходит отступление от предельной величины.</span><span class="sxs-lookup"><span data-stu-id="1fbcc-121">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="1fbcc-122">Значение по умолчанию: сумма maxConcurrentSessions и MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="1fbcc-122">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="1fbcc-123">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="1fbcc-123">maxConcurrentSessions</span></span>|<span data-ttu-id="1fbcc-124">Положительное целое число, ограничивающее количество сеансов, которое может принять объект <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="1fbcc-124">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="1fbcc-125">Служба принимает соединения сверх предела, но только каналы, количество которых меньше предельного значения, являются активными (сообщения считываются из канала).</span><span class="sxs-lookup"><span data-stu-id="1fbcc-125">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="1fbcc-126">Установка этого значения на 0 эквивалентна его установке на Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="1fbcc-126">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="1fbcc-127">Значение по умолчанию: 100 \* количество процессоров.</span><span class="sxs-lookup"><span data-stu-id="1fbcc-127">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1fbcc-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1fbcc-128">Child Elements</span></span>  
 <span data-ttu-id="1fbcc-129">Нет.</span><span class="sxs-lookup"><span data-stu-id="1fbcc-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1fbcc-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1fbcc-130">Parent Elements</span></span>  
  
|<span data-ttu-id="1fbcc-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="1fbcc-131">Element</span></span>|<span data-ttu-id="1fbcc-132">Описание</span><span class="sxs-lookup"><span data-stu-id="1fbcc-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fbcc-133">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="1fbcc-133">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="1fbcc-134">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="1fbcc-134">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fbcc-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="1fbcc-135">Remarks</span></span>  
 <span data-ttu-id="1fbcc-136">Элементы регулирования ограничивают число одновременных вызовов, экземпляров или сеансов, чтобы предотвратить чрезмерное потребление ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1fbcc-136">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="1fbcc-137">Каждый раз при достижении значений атрибутов происходит запись трассировки.</span><span class="sxs-lookup"><span data-stu-id="1fbcc-137">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="1fbcc-138">Первая трассировка записывается как предупреждение.</span><span class="sxs-lookup"><span data-stu-id="1fbcc-138">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fbcc-139">Пример</span><span class="sxs-lookup"><span data-stu-id="1fbcc-139">Example</span></span>  
 <span data-ttu-id="1fbcc-140">В следующем примере конфигурации служба допускает максимум 2 одновременно выполняющихся вызова, а максимальное количество одновременно присутствующих экземпляров равно 10.</span><span class="sxs-lookup"><span data-stu-id="1fbcc-140">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="1fbcc-141">Подробный пример выполнения этого примера см. в разделе [регулирование](../../../wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="1fbcc-141">For a detailed example of running this example, see [Throttling](../../../wcf/samples/throttling.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1fbcc-142">См. также</span><span class="sxs-lookup"><span data-stu-id="1fbcc-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [<span data-ttu-id="1fbcc-143">Использование ServiceThrottlingBehavior для управления производительностью службы WCF</span><span class="sxs-lookup"><span data-stu-id="1fbcc-143">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
