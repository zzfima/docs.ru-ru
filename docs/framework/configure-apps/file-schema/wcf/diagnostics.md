---
title: <diagnostics>
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: 3fc7828d399555f7c459f6dd067ce9a24b8998b6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108034"
---
# <a name="diagnostics"></a><span data-ttu-id="d0e5c-101">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="d0e5c-101">\<diagnostics></span></span>
<span data-ttu-id="d0e5c-102">Элемент `diagnostics` определяет параметры, которые могут быть использованы администратором для проверки и контроля времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-102">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
 <span data-ttu-id="d0e5c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d0e5c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d0e5c-104">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="d0e5c-104">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0e5c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0e5c-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics etwProviderId="String"
               performanceCounters="Off/ServiceOnly/All/Default"
               wmiProviderEnabled="Boolean">
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
    <messageLogging logEntireMessage="Boolean"
                    logMalformedMessages="Boolean"
                    logMessagesAtServiceLevel="Boolean"
                    logMessagesAtTransportLevel="Boolean"
                    maxMessagesToLog="Integer"
                    maxSizeOfMessageToLog="Integer">
      <filters>
        <clear />
      </filters>
    </messageLogging>
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0e5c-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d0e5c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d0e5c-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0e5c-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d0e5c-108">Attributes</span></span>  
  
|<span data-ttu-id="d0e5c-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d0e5c-109">Attribute</span></span>|<span data-ttu-id="d0e5c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d0e5c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d0e5c-111">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="d0e5c-111">etwProviderId</span></span>|<span data-ttu-id="d0e5c-112">Строка, которая задает идентификатор для поставщика отслеживания событий, который записывает события в сеансы ETW.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-112">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="d0e5c-113">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="d0e5c-113">performanceCounters</span></span>|<span data-ttu-id="d0e5c-114">Указывает, включены ли счетчики производительности для сборки.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-114">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="d0e5c-115">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="d0e5c-115">Valid values are</span></span><br /><br /> <span data-ttu-id="d0e5c-116">-Off: Счетчики производительности отключены.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-116">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="d0e5c-117">-ServiceOnly Включены только счетчики производительности, относящиеся к данной службе.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-117">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="d0e5c-118">— Все: Счетчики производительности можно просматривать во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-118">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="d0e5c-119">-Значение по умолчанию: Создается единичный экземпляр счетчика производительности _WCF_Admin.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-119">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="d0e5c-120">Данный экземпляр используется, чтобы включить коллекцию данных SQM для использования инфраструктурой.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-120">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="d0e5c-121">Значения счетчика для данного экземпляра не обновляются и, соответственно, остаются нулевыми.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-121">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="d0e5c-122">Если для WCF не задана конфигурация, это значение используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-122">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="d0e5c-123">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="d0e5c-123">wmiProviderEnabled</span></span>|<span data-ttu-id="d0e5c-124">Логическое значение, определяющее, включен ли поставщик WMI для сборки.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-124">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="d0e5c-125">Данный поставщик WMI требуется пользователю, чтобы на время выполнения получить доступ к функциональным возможностям проверки и контроля Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d0e5c-125">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="d0e5c-126">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-126">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0e5c-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d0e5c-127">Child Elements</span></span>  
  
|<span data-ttu-id="d0e5c-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="d0e5c-128">Element</span></span>|<span data-ttu-id="d0e5c-129">Описание</span><span class="sxs-lookup"><span data-stu-id="d0e5c-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0e5c-130">\<endToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="d0e5c-130">\<endToEndTracing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endtoendtracing.md)|<span data-ttu-id="d0e5c-131">Элемент конфигурации, который позволяет включать и отключать различные аспекты сквозной отслеживания во время выполнения приложения службы.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-131">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[<span data-ttu-id="d0e5c-132">\<messageLogging ></span><span class="sxs-lookup"><span data-stu-id="d0e5c-132">\<messageLogging></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)|<span data-ttu-id="d0e5c-133">Описывает параметры ведения журнала сообщений WCF.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-133">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d0e5c-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d0e5c-134">Parent Elements</span></span>  
  
|<span data-ttu-id="d0e5c-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="d0e5c-135">Element</span></span>|<span data-ttu-id="d0e5c-136">Описание</span><span class="sxs-lookup"><span data-stu-id="d0e5c-136">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d0e5c-137">serviceModel</span><span class="sxs-lookup"><span data-stu-id="d0e5c-137">serviceModel</span></span>|<span data-ttu-id="d0e5c-138">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-138">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0e5c-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="d0e5c-139">Remarks</span></span>  
 <span data-ttu-id="d0e5c-140">В разделе `diagnostics` определяются параметры диагностики для всех служб, содержащихся в сборке.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-140">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="d0e5c-141">Отдельные параметры диагностики можно определить на уровне службы, только если сборка содержит одну службу.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-141">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="d0e5c-142">Атрибуты заданы в соответствии с требованиями раздела.</span><span class="sxs-lookup"><span data-stu-id="d0e5c-142">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0e5c-143">Пример</span><span class="sxs-lookup"><span data-stu-id="d0e5c-143">Example</span></span>  
  
```xml  
<diagnostics wmiProviderEnabled="false"
             performanceCounters="all">
  <messageLogging logEntireMessage="true"
                  logMalformedMessages="true"
                  logMessagesAtServiceLevel="true"
                  logMessagesAtTransportLevel="true"
                  maxMessagesToLog="42"
                  maxSizeOfMessageToLog="42">
    <filters>
      <clear />
    </filters>
  </messageLogging>
</diagnostics>
```  
  
## <a name="see-also"></a><span data-ttu-id="d0e5c-144">См. также</span><span class="sxs-lookup"><span data-stu-id="d0e5c-144">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
