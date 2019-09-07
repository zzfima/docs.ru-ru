---
title: <diagnostics>
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: 2749bc6c66d491a8a160d98b508fb43aa027b806
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398043"
---
# <a name="diagnostics"></a><span data-ttu-id="27327-101">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="27327-101">\<diagnostics></span></span>
<span data-ttu-id="27327-102">Элемент `diagnostics` определяет параметры, которые могут быть использованы администратором для проверки и контроля времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="27327-102">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
<span data-ttu-id="27327-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="27327-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="27327-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="27327-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="27327-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<Диагностика >**</span><span class="sxs-lookup"><span data-stu-id="27327-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27327-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27327-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27327-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="27327-107">Attributes and Elements</span></span>  
 <span data-ttu-id="27327-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="27327-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27327-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="27327-109">Attributes</span></span>  
  
|<span data-ttu-id="27327-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="27327-110">Attribute</span></span>|<span data-ttu-id="27327-111">Описание</span><span class="sxs-lookup"><span data-stu-id="27327-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="27327-112">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="27327-112">etwProviderId</span></span>|<span data-ttu-id="27327-113">Строка, которая задает идентификатор для поставщика отслеживания событий, который записывает события в сеансы ETW.</span><span class="sxs-lookup"><span data-stu-id="27327-113">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="27327-114">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="27327-114">performanceCounters</span></span>|<span data-ttu-id="27327-115">Указывает, включены ли счетчики производительности для сборки.</span><span class="sxs-lookup"><span data-stu-id="27327-115">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="27327-116">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="27327-116">Valid values are</span></span><br /><br /> <span data-ttu-id="27327-117">Автоном Счетчики производительности отключены.</span><span class="sxs-lookup"><span data-stu-id="27327-117">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="27327-118">-Сервицеонли: Включены только счетчики производительности, относящиеся к данной службе.</span><span class="sxs-lookup"><span data-stu-id="27327-118">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="27327-119">Каждого Счетчики производительности можно просматривать во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="27327-119">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="27327-120">Параметры Создается единичный экземпляр счетчика производительности _WCF_Admin.</span><span class="sxs-lookup"><span data-stu-id="27327-120">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="27327-121">Данный экземпляр используется, чтобы включить коллекцию данных SQM для использования инфраструктурой.</span><span class="sxs-lookup"><span data-stu-id="27327-121">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="27327-122">Значения счетчика для данного экземпляра не обновляются и, соответственно, остаются нулевыми.</span><span class="sxs-lookup"><span data-stu-id="27327-122">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="27327-123">Если для WCF не задана конфигурация, это значение используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="27327-123">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="27327-124">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="27327-124">wmiProviderEnabled</span></span>|<span data-ttu-id="27327-125">Логическое значение, определяющее, включен ли поставщик WMI для сборки.</span><span class="sxs-lookup"><span data-stu-id="27327-125">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="27327-126">Данный поставщик WMI требуется пользователю, чтобы на время выполнения получить доступ к функциональным возможностям проверки и контроля Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="27327-126">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="27327-127">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="27327-127">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27327-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="27327-128">Child Elements</span></span>  
  
|<span data-ttu-id="27327-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="27327-129">Element</span></span>|<span data-ttu-id="27327-130">Описание</span><span class="sxs-lookup"><span data-stu-id="27327-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27327-131">\<ЕндтоендтраЦинг ></span><span class="sxs-lookup"><span data-stu-id="27327-131">\<endToEndTracing></span></span>](endtoendtracing.md)|<span data-ttu-id="27327-132">Элемент конфигурации, который позволяет включать и отключать различные аспекты сквозной отслеживания во время выполнения приложения службы.</span><span class="sxs-lookup"><span data-stu-id="27327-132">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[<span data-ttu-id="27327-133">\<Мессажелоггинг ></span><span class="sxs-lookup"><span data-stu-id="27327-133">\<messageLogging></span></span>](messagelogging.md)|<span data-ttu-id="27327-134">Описывает параметры ведения журнала сообщений WCF.</span><span class="sxs-lookup"><span data-stu-id="27327-134">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="27327-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="27327-135">Parent Elements</span></span>  
  
|<span data-ttu-id="27327-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="27327-136">Element</span></span>|<span data-ttu-id="27327-137">Описание</span><span class="sxs-lookup"><span data-stu-id="27327-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27327-138">serviceModel</span><span class="sxs-lookup"><span data-stu-id="27327-138">serviceModel</span></span>|<span data-ttu-id="27327-139">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="27327-139">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27327-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="27327-140">Remarks</span></span>  
 <span data-ttu-id="27327-141">В разделе `diagnostics` определяются параметры диагностики для всех служб, содержащихся в сборке.</span><span class="sxs-lookup"><span data-stu-id="27327-141">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="27327-142">Отдельные параметры диагностики можно определить на уровне службы, только если сборка содержит одну службу.</span><span class="sxs-lookup"><span data-stu-id="27327-142">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="27327-143">Атрибуты заданы в соответствии с требованиями раздела.</span><span class="sxs-lookup"><span data-stu-id="27327-143">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27327-144">Пример</span><span class="sxs-lookup"><span data-stu-id="27327-144">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="27327-145">См. также</span><span class="sxs-lookup"><span data-stu-id="27327-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
