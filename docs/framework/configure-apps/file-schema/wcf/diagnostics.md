---
title: '&lt;Диагностика&gt;'
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: 3ee611d3903ba36748837d2743cd03d54670befd
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149349"
---
# <a name="ltdiagnosticsgt"></a><span data-ttu-id="b14a1-102">&lt;Диагностика&gt;</span><span class="sxs-lookup"><span data-stu-id="b14a1-102">&lt;diagnostics&gt;</span></span>
<span data-ttu-id="b14a1-103">Элемент `diagnostics` определяет параметры, которые могут быть использованы администратором для проверки и контроля времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="b14a1-103">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
 <span data-ttu-id="b14a1-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b14a1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b14a1-105">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="b14a1-105">\<diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b14a1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b14a1-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b14a1-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b14a1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b14a1-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b14a1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b14a1-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b14a1-109">Attributes</span></span>  
  
|<span data-ttu-id="b14a1-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b14a1-110">Attribute</span></span>|<span data-ttu-id="b14a1-111">Описание</span><span class="sxs-lookup"><span data-stu-id="b14a1-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b14a1-112">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="b14a1-112">etwProviderId</span></span>|<span data-ttu-id="b14a1-113">Строка, которая задает идентификатор для поставщика отслеживания событий, который записывает события в сеансы ETW.</span><span class="sxs-lookup"><span data-stu-id="b14a1-113">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="b14a1-114">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="b14a1-114">performanceCounters</span></span>|<span data-ttu-id="b14a1-115">Указывает, включены ли счетчики производительности для сборки.</span><span class="sxs-lookup"><span data-stu-id="b14a1-115">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="b14a1-116">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="b14a1-116">Valid values are</span></span><br /><br /> <span data-ttu-id="b14a1-117">-Off: Счетчики производительности отключены.</span><span class="sxs-lookup"><span data-stu-id="b14a1-117">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="b14a1-118">-ServiceOnly Включены только счетчики производительности, относящиеся к данной службе.</span><span class="sxs-lookup"><span data-stu-id="b14a1-118">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="b14a1-119">— Все: Счетчики производительности можно просматривать во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b14a1-119">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="b14a1-120">-Значение по умолчанию: Создается единичный экземпляр счетчика производительности _WCF_Admin.</span><span class="sxs-lookup"><span data-stu-id="b14a1-120">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="b14a1-121">Данный экземпляр используется, чтобы включить коллекцию данных SQM для использования инфраструктурой.</span><span class="sxs-lookup"><span data-stu-id="b14a1-121">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="b14a1-122">Значения счетчика для данного экземпляра не обновляются и, соответственно, остаются нулевыми.</span><span class="sxs-lookup"><span data-stu-id="b14a1-122">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="b14a1-123">Если для WCF не задана конфигурация, это значение используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b14a1-123">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="b14a1-124">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="b14a1-124">wmiProviderEnabled</span></span>|<span data-ttu-id="b14a1-125">Логическое значение, определяющее, включен ли поставщик WMI для сборки.</span><span class="sxs-lookup"><span data-stu-id="b14a1-125">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="b14a1-126">Данный поставщик WMI требуется пользователю, чтобы на время выполнения получить доступ к функциональным возможностям проверки и контроля Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="b14a1-126">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="b14a1-127">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="b14a1-127">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b14a1-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b14a1-128">Child Elements</span></span>  
  
|<span data-ttu-id="b14a1-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="b14a1-129">Element</span></span>|<span data-ttu-id="b14a1-130">Описание</span><span class="sxs-lookup"><span data-stu-id="b14a1-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b14a1-131">\<endToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="b14a1-131">\<endToEndTracing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endtoendtracing.md)|<span data-ttu-id="b14a1-132">Элемент конфигурации, который позволяет включать и отключать различные аспекты сквозной отслеживания во время выполнения приложения службы.</span><span class="sxs-lookup"><span data-stu-id="b14a1-132">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[<span data-ttu-id="b14a1-133">\<messageLogging ></span><span class="sxs-lookup"><span data-stu-id="b14a1-133">\<messageLogging></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)|<span data-ttu-id="b14a1-134">Описывает параметры ведения журнала сообщений WCF.</span><span class="sxs-lookup"><span data-stu-id="b14a1-134">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b14a1-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b14a1-135">Parent Elements</span></span>  
  
|<span data-ttu-id="b14a1-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="b14a1-136">Element</span></span>|<span data-ttu-id="b14a1-137">Описание</span><span class="sxs-lookup"><span data-stu-id="b14a1-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b14a1-138">serviceModel</span><span class="sxs-lookup"><span data-stu-id="b14a1-138">serviceModel</span></span>|<span data-ttu-id="b14a1-139">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="b14a1-139">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b14a1-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="b14a1-140">Remarks</span></span>  
 <span data-ttu-id="b14a1-141">В разделе `diagnostics` определяются параметры диагностики для всех служб, содержащихся в сборке.</span><span class="sxs-lookup"><span data-stu-id="b14a1-141">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="b14a1-142">Отдельные параметры диагностики можно определить на уровне службы, только если сборка содержит одну службу.</span><span class="sxs-lookup"><span data-stu-id="b14a1-142">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="b14a1-143">Атрибуты заданы в соответствии с требованиями раздела.</span><span class="sxs-lookup"><span data-stu-id="b14a1-143">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b14a1-144">Пример</span><span class="sxs-lookup"><span data-stu-id="b14a1-144">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b14a1-145">См. также</span><span class="sxs-lookup"><span data-stu-id="b14a1-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>
