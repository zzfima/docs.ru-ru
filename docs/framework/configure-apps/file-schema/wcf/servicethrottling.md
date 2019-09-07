---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: ad87a5876381a7224341babdb076c85edcd1dd87
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399565"
---
# <a name="servicethrottling"></a><span data-ttu-id="4d6ce-101">\<Сервицесроттлинг ></span><span class="sxs-lookup"><span data-stu-id="4d6ce-101">\<serviceThrottling></span></span>
<span data-ttu-id="4d6ce-102">Задает механизм настройки службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4d6ce-102">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
<span data-ttu-id="4d6ce-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4d6ce-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4d6ce-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4d6ce-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4d6ce-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4d6ce-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="4d6ce-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4d6ce-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="4d6ce-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4d6ce-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="4d6ce-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Сервицесроттлинг >**</span><span class="sxs-lookup"><span data-stu-id="4d6ce-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceThrottling>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d6ce-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d6ce-109">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d6ce-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4d6ce-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4d6ce-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4d6ce-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d6ce-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4d6ce-112">Attributes</span></span>  
  
|<span data-ttu-id="4d6ce-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4d6ce-113">Attribute</span></span>|<span data-ttu-id="4d6ce-114">Описание</span><span class="sxs-lookup"><span data-stu-id="4d6ce-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d6ce-115">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="4d6ce-115">maxConcurrentCalls</span></span>|<span data-ttu-id="4d6ce-116">Положительное целое число, ограничивающее количество сообщений, обрабатываемых в текущий момент в <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="4d6ce-116">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="4d6ce-117">Вызовы, превышающие этот предел, ставятся в очередь.</span><span class="sxs-lookup"><span data-stu-id="4d6ce-117">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="4d6ce-118">Установка этого значения на 0 эквивалентна его установке на Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="4d6ce-118">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="4d6ce-119">Значение по умолчанию: 16 \* количество процессоров.</span><span class="sxs-lookup"><span data-stu-id="4d6ce-119">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="4d6ce-120">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="4d6ce-120">maxConcurrentInstances</span></span>|<span data-ttu-id="4d6ce-121">Положительное целое число, ограничивающее количество объектов <xref:System.ServiceModel.InstanceContext>, одновременно выполняющихся в <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="4d6ce-121">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="4d6ce-122">Запросы на создание дополнительных экземпляров ставятся в очередь и выполняются, когда происходит отступление от предельной величины.</span><span class="sxs-lookup"><span data-stu-id="4d6ce-122">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="4d6ce-123">Значение по умолчанию: сумма maxConcurrentSessions и MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="4d6ce-123">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="4d6ce-124">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="4d6ce-124">maxConcurrentSessions</span></span>|<span data-ttu-id="4d6ce-125">Положительное целое число, ограничивающее количество сеансов, которое может принять объект <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="4d6ce-125">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="4d6ce-126">Служба принимает соединения сверх предела, но только каналы, количество которых меньше предельного значения, являются активными (сообщения считываются из канала).</span><span class="sxs-lookup"><span data-stu-id="4d6ce-126">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="4d6ce-127">Установка этого значения на 0 эквивалентна его установке на Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="4d6ce-127">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="4d6ce-128">Значение по умолчанию: 100 \* количество процессоров.</span><span class="sxs-lookup"><span data-stu-id="4d6ce-128">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d6ce-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4d6ce-129">Child Elements</span></span>  
 <span data-ttu-id="4d6ce-130">Нет.</span><span class="sxs-lookup"><span data-stu-id="4d6ce-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d6ce-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4d6ce-131">Parent Elements</span></span>  
  
|<span data-ttu-id="4d6ce-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="4d6ce-132">Element</span></span>|<span data-ttu-id="4d6ce-133">Описание</span><span class="sxs-lookup"><span data-stu-id="4d6ce-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d6ce-134">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="4d6ce-134">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="4d6ce-135">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="4d6ce-135">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d6ce-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="4d6ce-136">Remarks</span></span>  
 <span data-ttu-id="4d6ce-137">Элементы регулирования ограничивают число одновременных вызовов, экземпляров или сеансов, чтобы предотвратить чрезмерное потребление ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4d6ce-137">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="4d6ce-138">Каждый раз при достижении значений атрибутов происходит запись трассировки.</span><span class="sxs-lookup"><span data-stu-id="4d6ce-138">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="4d6ce-139">Первая трассировка записывается как предупреждение.</span><span class="sxs-lookup"><span data-stu-id="4d6ce-139">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d6ce-140">Пример</span><span class="sxs-lookup"><span data-stu-id="4d6ce-140">Example</span></span>  
 <span data-ttu-id="4d6ce-141">В следующем примере конфигурации служба допускает максимум 2 одновременно выполняющихся вызова, а максимальное количество одновременно присутствующих экземпляров равно 10.</span><span class="sxs-lookup"><span data-stu-id="4d6ce-141">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="4d6ce-142">Подробный пример выполнения этого примера см. в разделе [регулирование](../../../wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="4d6ce-142">For a detailed example of running this example, see [Throttling](../../../wcf/samples/throttling.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4d6ce-143">См. также</span><span class="sxs-lookup"><span data-stu-id="4d6ce-143">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [<span data-ttu-id="4d6ce-144">Использование ServiceThrottlingBehavior для управления производительностью службы WCF</span><span class="sxs-lookup"><span data-stu-id="4d6ce-144">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
