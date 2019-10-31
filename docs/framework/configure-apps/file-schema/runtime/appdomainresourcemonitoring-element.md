---
title: Элемент <appDomainResourceMonitoring>
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 991833500cae4d96e9c28f7e94ca366e9b976a9d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118258"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="84172-102">\<Аппдомаинресаурцемониторинг > элемент</span><span class="sxs-lookup"><span data-stu-id="84172-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="84172-103">Указывает среде собирать статистику для всех доменов приложений в процессе за весь период его существования.</span><span class="sxs-lookup"><span data-stu-id="84172-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
<span data-ttu-id="84172-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="84172-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="84172-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="84172-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="84172-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<аппдомаинресаурцемониторинг >**</span><span class="sxs-lookup"><span data-stu-id="84172-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84172-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84172-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84172-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="84172-108">Attributes and Elements</span></span>  
 <span data-ttu-id="84172-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="84172-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84172-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="84172-110">Attributes</span></span>  
  
|<span data-ttu-id="84172-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="84172-111">Attribute</span></span>|<span data-ttu-id="84172-112">Описание</span><span class="sxs-lookup"><span data-stu-id="84172-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="84172-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="84172-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="84172-114">Указывает, собирает ли среда выполнения статистические данные для отслеживания ресурсов домена приложения.</span><span class="sxs-lookup"><span data-stu-id="84172-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="84172-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="84172-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="84172-116">значения</span><span class="sxs-lookup"><span data-stu-id="84172-116">Value</span></span>|<span data-ttu-id="84172-117">Описание</span><span class="sxs-lookup"><span data-stu-id="84172-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="84172-118">Собираются статистические данные для отслеживания ресурсов домена приложения.</span><span class="sxs-lookup"><span data-stu-id="84172-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="84172-119">Статистика по мониторингу ресурсов домена приложений не собирается.</span><span class="sxs-lookup"><span data-stu-id="84172-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84172-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="84172-120">Child Elements</span></span>  
 <span data-ttu-id="84172-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="84172-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="84172-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="84172-122">Parent Elements</span></span>  
  
|<span data-ttu-id="84172-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="84172-123">Element</span></span>|<span data-ttu-id="84172-124">Описание</span><span class="sxs-lookup"><span data-stu-id="84172-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="84172-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="84172-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="84172-126">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="84172-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84172-127">Заметки</span><span class="sxs-lookup"><span data-stu-id="84172-127">Remarks</span></span>  
 <span data-ttu-id="84172-128">Мониторинг ресурсов домена приложений доступен через класс домена управляемого приложения, интерфейс размещения [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) и трассировку событий для Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="84172-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="84172-129">При включении мониторинга статистика собирается для всех доменов приложений в процессе в течение жизненного цикла процесса.</span><span class="sxs-lookup"><span data-stu-id="84172-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="84172-130">Чтобы включить мониторинг из управляемого кода, используйте свойство <xref:System.AppDomain.MonitoringIsEnabled%2A>.</span><span class="sxs-lookup"><span data-stu-id="84172-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="84172-131">Этот элемент конфигурации доступен только в .NET Framework 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="84172-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84172-132">Пример</span><span class="sxs-lookup"><span data-stu-id="84172-132">Example</span></span>  
 <span data-ttu-id="84172-133">В следующем примере показано, как включить отслеживание ресурсов домена приложения.</span><span class="sxs-lookup"><span data-stu-id="84172-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="84172-134">См. также</span><span class="sxs-lookup"><span data-stu-id="84172-134">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="84172-135">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="84172-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="84172-136">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="84172-136">Configuration File Schema</span></span>](../index.md)
