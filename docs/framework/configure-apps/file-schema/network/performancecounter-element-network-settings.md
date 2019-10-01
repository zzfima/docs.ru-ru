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
ms.openlocfilehash: 3fe6b19d0055aafad859b55960800d9786d7fa08
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698002"
---
# <a name="performancecounter-element-network-settings"></a><span data-ttu-id="273ce-102">Элемент > @no__t 0performanceCounter (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="273ce-102">\<performanceCounter> Element (Network Settings)</span></span>
<span data-ttu-id="273ce-103">Включает или отключает счетчики производительности сети.</span><span class="sxs-lookup"><span data-stu-id="273ce-103">Enables or disables networking performance counters.</span></span>  
  
[<span data-ttu-id="273ce-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="273ce-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="273ce-105">&nbsp; @ no__t-1[ **@no__t -4system. NET >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="273ce-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="273ce-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<settings >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="273ce-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="273ce-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<performanceCounters >**</span><span class="sxs-lookup"><span data-stu-id="273ce-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="273ce-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="273ce-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="273ce-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="273ce-109">Attributes and Elements</span></span>  
 <span data-ttu-id="273ce-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="273ce-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="273ce-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="273ce-111">Attributes</span></span>  
  
|<span data-ttu-id="273ce-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="273ce-112">Attribute</span></span>|<span data-ttu-id="273ce-113">Описание</span><span class="sxs-lookup"><span data-stu-id="273ce-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="273ce-114">Указывает, включены ли счетчики производительности сети.</span><span class="sxs-lookup"><span data-stu-id="273ce-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="273ce-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="273ce-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="273ce-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="273ce-116">Child Elements</span></span>  
 <span data-ttu-id="273ce-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="273ce-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="273ce-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="273ce-118">Parent Elements</span></span>  
  
|<span data-ttu-id="273ce-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="273ce-119">Element</span></span>|<span data-ttu-id="273ce-120">Описание</span><span class="sxs-lookup"><span data-stu-id="273ce-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="273ce-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="273ce-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="273ce-122">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="273ce-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="273ce-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="273ce-123">Remarks</span></span>  
 <span data-ttu-id="273ce-124">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="273ce-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="273ce-125">Счетчики производительности сети необходимо включить для использования в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="273ce-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="273ce-126">Все счетчики производительности сети включаются и отключаются с помощью одного параметра в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="273ce-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="273ce-127">Включить или отключить отдельные счетчики производительности сети невозможно.</span><span class="sxs-lookup"><span data-stu-id="273ce-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="273ce-128">Дополнительные сведения о конкретных счетчиках производительности сети см. в разделе [Сетевые счетчики производительности](../../../debug-trace-profile/performance-counters.md#networking).</span><span class="sxs-lookup"><span data-stu-id="273ce-128">For more information on the specific networking performance counters, see [Networking Performance Counters](../../../debug-trace-profile/performance-counters.md#networking).</span></span>  
  
 <span data-ttu-id="273ce-129">Значение по умолчанию — сетевые счетчики производительности отключены.</span><span class="sxs-lookup"><span data-stu-id="273ce-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="273ce-130">Свойство <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> можно использовать для получения текущего значения атрибута **Enabled** из применимых файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="273ce-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="273ce-131">Пример</span><span class="sxs-lookup"><span data-stu-id="273ce-131">Example</span></span>  
 <span data-ttu-id="273ce-132">В следующем примере показано, как настроить <xref:System.Net> и связанные пространства имен для включения сетевых счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="273ce-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="273ce-133">См. также</span><span class="sxs-lookup"><span data-stu-id="273ce-133">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="273ce-134">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="273ce-134">Network Settings Schema</span></span>](index.md)
- [<span data-ttu-id="273ce-135">Счетчики производительности сети</span><span class="sxs-lookup"><span data-stu-id="273ce-135">Networking Performance Counters</span></span>](../../../debug-trace-profile/performance-counters.md#networking)
