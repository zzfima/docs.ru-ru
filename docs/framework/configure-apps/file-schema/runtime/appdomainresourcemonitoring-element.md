---
title: '&lt;appDomainResourceMonitoring&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc507d0cf81bf2bc11edfc0b5efb08c462726b88
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727876"
---
# <a name="ltappdomainresourcemonitoringgt-element"></a><span data-ttu-id="748c6-102">&lt;appDomainResourceMonitoring&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="748c6-102">&lt;appDomainResourceMonitoring&gt; Element</span></span>
<span data-ttu-id="748c6-103">Указывает среде собирать статистику для всех доменов приложений в процессе за весь период его существования.</span><span class="sxs-lookup"><span data-stu-id="748c6-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="748c6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="748c6-104">\<configuration></span></span>  
<span data-ttu-id="748c6-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="748c6-105">\<runtime></span></span>  
<span data-ttu-id="748c6-106">\<appDomainResourceMonitoring ></span><span class="sxs-lookup"><span data-stu-id="748c6-106">\<appDomainResourceMonitoring></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="748c6-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="748c6-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="748c6-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="748c6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="748c6-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="748c6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="748c6-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="748c6-110">Attributes</span></span>  
  
|<span data-ttu-id="748c6-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="748c6-111">Attribute</span></span>|<span data-ttu-id="748c6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="748c6-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="748c6-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="748c6-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="748c6-114">Определяет, будет ли среда выполнения собирать статистические данные для отслеживания ресурсов домена приложения.</span><span class="sxs-lookup"><span data-stu-id="748c6-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="748c6-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="748c6-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="748c6-116">Значение</span><span class="sxs-lookup"><span data-stu-id="748c6-116">Value</span></span>|<span data-ttu-id="748c6-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="748c6-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="748c6-118">Сбор статистики для отслеживания ресурсов домена приложения.</span><span class="sxs-lookup"><span data-stu-id="748c6-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="748c6-119">Статистические данные для отслеживания ресурсов домена приложения не собираются.</span><span class="sxs-lookup"><span data-stu-id="748c6-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="748c6-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="748c6-120">Child Elements</span></span>  
 <span data-ttu-id="748c6-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="748c6-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="748c6-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="748c6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="748c6-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="748c6-123">Element</span></span>|<span data-ttu-id="748c6-124">Описание</span><span class="sxs-lookup"><span data-stu-id="748c6-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="748c6-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="748c6-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="748c6-126">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="748c6-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="748c6-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="748c6-127">Remarks</span></span>  
 <span data-ttu-id="748c6-128">Отслеживание ресурсов домена приложения доступен через класс домена управляемого приложения, размещение [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) интерфейс и трассировка событий Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="748c6-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="748c6-129">При включенном наблюдении за, статистические данные собираются для всех доменов приложений в процессе, в течение жизненного цикла процесса.</span><span class="sxs-lookup"><span data-stu-id="748c6-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="748c6-130">Чтобы включить мониторинг из управляемого кода, используйте <xref:System.AppDomain.MonitoringIsEnabled%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="748c6-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="748c6-131">Этот элемент конфигурации доступен только в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="748c6-131">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="748c6-132">Пример</span><span class="sxs-lookup"><span data-stu-id="748c6-132">Example</span></span>  
 <span data-ttu-id="748c6-133">В следующем примере показано, как включить отслеживание ресурсов домена приложения.</span><span class="sxs-lookup"><span data-stu-id="748c6-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="748c6-134">См. также</span><span class="sxs-lookup"><span data-stu-id="748c6-134">See also</span></span>
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="748c6-135">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="748c6-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="748c6-136">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="748c6-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
