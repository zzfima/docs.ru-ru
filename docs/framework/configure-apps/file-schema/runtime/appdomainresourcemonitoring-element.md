---
title: Элемент <appDomainResourceMonitoring>
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 3c6092b6c34bb13c0ad0e66df2d3b7e65ac3de7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154380"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="46455-102">\<appDomainResourceMonitoring> Элемент</span><span class="sxs-lookup"><span data-stu-id="46455-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="46455-103">Указывает среде собирать статистику для всех доменов приложений в процессе за весь период его существования.</span><span class="sxs-lookup"><span data-stu-id="46455-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
<span data-ttu-id="46455-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="46455-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="46455-105">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="46455-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="46455-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**</span><span class="sxs-lookup"><span data-stu-id="46455-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46455-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46455-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46455-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="46455-108">Attributes and Elements</span></span>  
 <span data-ttu-id="46455-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="46455-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46455-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="46455-110">Attributes</span></span>  
  
|<span data-ttu-id="46455-111">attribute</span><span class="sxs-lookup"><span data-stu-id="46455-111">Attribute</span></span>|<span data-ttu-id="46455-112">Описание</span><span class="sxs-lookup"><span data-stu-id="46455-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="46455-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="46455-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="46455-114">Уточняется, собирает ли время выполнения статистику для мониторинга ресурсов доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="46455-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="46455-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="46455-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="46455-116">Значение</span><span class="sxs-lookup"><span data-stu-id="46455-116">Value</span></span>|<span data-ttu-id="46455-117">Описание</span><span class="sxs-lookup"><span data-stu-id="46455-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="46455-118">Собрана статистика мониторинга ресурсов доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="46455-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="46455-119">Статистика мониторинга ресурсов доменов приложений не собирается.</span><span class="sxs-lookup"><span data-stu-id="46455-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46455-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="46455-120">Child Elements</span></span>  
 <span data-ttu-id="46455-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="46455-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="46455-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="46455-122">Parent Elements</span></span>  
  
|<span data-ttu-id="46455-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="46455-123">Element</span></span>|<span data-ttu-id="46455-124">Описание</span><span class="sxs-lookup"><span data-stu-id="46455-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="46455-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="46455-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="46455-126">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="46455-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46455-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="46455-127">Remarks</span></span>  
 <span data-ttu-id="46455-128">Мониторинг ресурсов доменов приложений доступен через управляемый класс доменов приложений, интерфейс [хостинга ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) и отслеживание событий для Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="46455-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="46455-129">При включении мониторинга собираются статистические данные по всем областям приложений в процессе процесса.</span><span class="sxs-lookup"><span data-stu-id="46455-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="46455-130">Для обеспечения мониторинга из <xref:System.AppDomain.MonitoringIsEnabled%2A> управляемого кода используйте свойство.</span><span class="sxs-lookup"><span data-stu-id="46455-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="46455-131">Этот элемент конфигурации доступен только в системе .NET 4 и позже.</span><span class="sxs-lookup"><span data-stu-id="46455-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46455-132">Пример</span><span class="sxs-lookup"><span data-stu-id="46455-132">Example</span></span>  
 <span data-ttu-id="46455-133">В следующем примере показано, как включить мониторинг ресурсов домена приложений.</span><span class="sxs-lookup"><span data-stu-id="46455-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="46455-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="46455-134">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="46455-135">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="46455-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="46455-136">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="46455-136">Configuration File Schema</span></span>](../index.md)
