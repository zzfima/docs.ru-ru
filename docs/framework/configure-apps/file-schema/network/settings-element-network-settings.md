---
title: Элемент <settings> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: 839907d9339d459070fff12dbca22d3c2df5b020
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260623"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="b2548-102">\<Параметры > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="b2548-102">\<settings> Element (Network Settings)</span></span>
<span data-ttu-id="b2548-103">Настраивает основные параметры сети для пространства имен <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b2548-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="b2548-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b2548-104">\<configuration></span></span>  
<span data-ttu-id="b2548-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b2548-105">\<system.net></span></span>  
<span data-ttu-id="b2548-106">\<Параметры ></span><span class="sxs-lookup"><span data-stu-id="b2548-106">\<settings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2548-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2548-107">Syntax</span></span>  
  
```xml  
<settings>  
  <httpListener>...</httpListener>  
  <httpWebRequest>...</httpWebRequest>  
  <ipv6>...</ipv6>  
  <performanceCounters>...</performanceCounters>  
  <servicePointManager>...</servicePointManager>  
  <socket>...</socket>  
  <webProxyScript>...</webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2548-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b2548-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b2548-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b2548-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2548-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b2548-110">Attributes</span></span>  
 <span data-ttu-id="b2548-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b2548-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b2548-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b2548-112">Child Elements</span></span>  
  
|<span data-ttu-id="b2548-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="b2548-113">Element</span></span>|<span data-ttu-id="b2548-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="b2548-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2548-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="b2548-115">httpListener</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|<span data-ttu-id="b2548-116">Настраивает параметры, используемые <xref:System.Net.HttpListener> класса.</span><span class="sxs-lookup"><span data-stu-id="b2548-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="b2548-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="b2548-117">httpWebRequest</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|<span data-ttu-id="b2548-118">Настраивает параметры веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="b2548-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="b2548-119">IPv6</span><span class="sxs-lookup"><span data-stu-id="b2548-119">ipv6</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|<span data-ttu-id="b2548-120">Включает протокол IP версии 6 (IPv6) поддержки.</span><span class="sxs-lookup"><span data-stu-id="b2548-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="b2548-121">\<performanceCounter > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="b2548-121">\<performanceCounter> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|<span data-ttu-id="b2548-122">Включает счетчики производительности сети.</span><span class="sxs-lookup"><span data-stu-id="b2548-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="b2548-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="b2548-123">servicePointManager</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|<span data-ttu-id="b2548-124">Настраивает подключения к сетевым ресурсам.</span><span class="sxs-lookup"><span data-stu-id="b2548-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="b2548-125">сокет</span><span class="sxs-lookup"><span data-stu-id="b2548-125">socket</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|<span data-ttu-id="b2548-126">Указывает, используют ли операции сокета порты завершения.</span><span class="sxs-lookup"><span data-stu-id="b2548-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="b2548-127">\<webProxyScript > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="b2548-127">\<webProxyScript> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|<span data-ttu-id="b2548-128">Настраивает характеристики сценария, используемого для обнаружения веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="b2548-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2548-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b2548-129">Parent Elements</span></span>  
  
|<span data-ttu-id="b2548-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="b2548-130">Element</span></span>|<span data-ttu-id="b2548-131">Описание:</span><span class="sxs-lookup"><span data-stu-id="b2548-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2548-132">System.NET</span><span class="sxs-lookup"><span data-stu-id="b2548-132">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="b2548-133">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="b2548-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2548-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2548-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b2548-135">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="b2548-135">Configuration Files</span></span>  
 <span data-ttu-id="b2548-136">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b2548-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2548-137">См. также</span><span class="sxs-lookup"><span data-stu-id="b2548-137">See also</span></span>
- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="b2548-138">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="b2548-138">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
