---
title: Элемент <appDomainResourceMonitoring>
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1395ee64d94e33693344b678c7a949665f994079
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252826"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="8af30-102">\<Элемент > Аппдомаинресаурцемониторинг</span><span class="sxs-lookup"><span data-stu-id="8af30-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="8af30-103">Указывает среде собирать статистику для всех доменов приложений в процессе за весь период его существования.</span><span class="sxs-lookup"><span data-stu-id="8af30-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
<span data-ttu-id="8af30-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8af30-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8af30-105">&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="8af30-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="8af30-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Аппдомаинресаурцемониторинг >**</span><span class="sxs-lookup"><span data-stu-id="8af30-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af30-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8af30-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8af30-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8af30-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8af30-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8af30-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8af30-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8af30-110">Attributes</span></span>  
  
|<span data-ttu-id="8af30-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8af30-111">Attribute</span></span>|<span data-ttu-id="8af30-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8af30-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="8af30-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="8af30-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="8af30-114">Указывает, собирает ли среда выполнения статистические данные для отслеживания ресурсов домена приложения.</span><span class="sxs-lookup"><span data-stu-id="8af30-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="8af30-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="8af30-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="8af30-116">Значение</span><span class="sxs-lookup"><span data-stu-id="8af30-116">Value</span></span>|<span data-ttu-id="8af30-117">Описание</span><span class="sxs-lookup"><span data-stu-id="8af30-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="8af30-118">Собираются статистические данные для отслеживания ресурсов домена приложения.</span><span class="sxs-lookup"><span data-stu-id="8af30-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="8af30-119">Статистика по мониторингу ресурсов домена приложений не собирается.</span><span class="sxs-lookup"><span data-stu-id="8af30-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8af30-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8af30-120">Child Elements</span></span>  
 <span data-ttu-id="8af30-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="8af30-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8af30-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8af30-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8af30-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="8af30-123">Element</span></span>|<span data-ttu-id="8af30-124">Описание</span><span class="sxs-lookup"><span data-stu-id="8af30-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8af30-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8af30-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8af30-126">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="8af30-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8af30-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="8af30-127">Remarks</span></span>  
 <span data-ttu-id="8af30-128">Мониторинг ресурсов домена приложений доступен через класс домена управляемого приложения, интерфейс размещения [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) и трассировку событий для Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="8af30-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="8af30-129">При включении мониторинга статистика собирается для всех доменов приложений в процессе в течение жизненного цикла процесса.</span><span class="sxs-lookup"><span data-stu-id="8af30-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="8af30-130">Чтобы включить мониторинг из управляемого кода, используйте <xref:System.AppDomain.MonitoringIsEnabled%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="8af30-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="8af30-131">Этот элемент конфигурации доступен только в .NET Framework 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="8af30-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8af30-132">Пример</span><span class="sxs-lookup"><span data-stu-id="8af30-132">Example</span></span>  
 <span data-ttu-id="8af30-133">В следующем примере показано, как включить отслеживание ресурсов домена приложения.</span><span class="sxs-lookup"><span data-stu-id="8af30-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8af30-134">См. также</span><span class="sxs-lookup"><span data-stu-id="8af30-134">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8af30-135">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="8af30-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8af30-136">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="8af30-136">Configuration File Schema</span></span>](../index.md)
