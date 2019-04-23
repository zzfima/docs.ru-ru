---
title: Элемент <performanceCounter> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
ms.openlocfilehash: 30c5cd07c92a8fc3c340cab0ff9ae74e940c0c12
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210936"
---
# <a name="performancecounter-element-network-settings"></a><span data-ttu-id="f551c-102">\<performanceCounter > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="f551c-102">\<performanceCounter> Element (Network Settings)</span></span>
<span data-ttu-id="f551c-103">Включает или отключает счетчики производительности сети.</span><span class="sxs-lookup"><span data-stu-id="f551c-103">Enables or disables networking performance counters.</span></span>  
  
 <span data-ttu-id="f551c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f551c-104">\<configuration></span></span>  
<span data-ttu-id="f551c-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="f551c-105">\<system.net></span></span>  
<span data-ttu-id="f551c-106">\<Параметры ></span><span class="sxs-lookup"><span data-stu-id="f551c-106">\<settings></span></span>  
<span data-ttu-id="f551c-107">\<performanceCounters ></span><span class="sxs-lookup"><span data-stu-id="f551c-107">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f551c-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f551c-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f551c-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f551c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f551c-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f551c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f551c-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f551c-111">Attributes</span></span>  
  
|<span data-ttu-id="f551c-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f551c-112">Attribute</span></span>|<span data-ttu-id="f551c-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f551c-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="f551c-114">Указывает, включены ли счетчики производительности сети.</span><span class="sxs-lookup"><span data-stu-id="f551c-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="f551c-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="f551c-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f551c-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f551c-116">Child Elements</span></span>  
 <span data-ttu-id="f551c-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f551c-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f551c-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f551c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f551c-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="f551c-119">Element</span></span>|<span data-ttu-id="f551c-120">Описание</span><span class="sxs-lookup"><span data-stu-id="f551c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f551c-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="f551c-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="f551c-122">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="f551c-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f551c-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="f551c-123">Remarks</span></span>  
 <span data-ttu-id="f551c-124">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f551c-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="f551c-125">Счетчики производительности сети необходимо включить для использования в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f551c-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="f551c-126">Все счетчики производительности сети включаются и отключаются с помощью одного параметра в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f551c-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="f551c-127">Включить или отключить отдельные счетчики производительности сети невозможно.</span><span class="sxs-lookup"><span data-stu-id="f551c-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="f551c-128">Дополнительные сведения о конкретных счетчики производительности сети, см. в разделе [счетчики производительности сети](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking).</span><span class="sxs-lookup"><span data-stu-id="f551c-128">For more information on the specific networking performance counters, see [Networking Performance Counters](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking).</span></span>  
  
 <span data-ttu-id="f551c-129">Значение по умолчанию — что сетевой производительности счетчики отключены.</span><span class="sxs-lookup"><span data-stu-id="f551c-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="f551c-130"><xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> Свойство может использоваться для получения текущего значения **включена** атрибут из применимые файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f551c-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f551c-131">Пример</span><span class="sxs-lookup"><span data-stu-id="f551c-131">Example</span></span>  
 <span data-ttu-id="f551c-132">В следующем примере показано, как настроить <xref:System.Net> и соответствующие пространства имен, чтобы включить счетчики производительности сети.</span><span class="sxs-lookup"><span data-stu-id="f551c-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f551c-133">См. также</span><span class="sxs-lookup"><span data-stu-id="f551c-133">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f551c-134">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="f551c-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="f551c-135">Счетчики производительности сети</span><span class="sxs-lookup"><span data-stu-id="f551c-135">Networking Performance Counters</span></span>](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking)
