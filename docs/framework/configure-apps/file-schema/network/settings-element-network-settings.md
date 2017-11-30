---
title: "&lt;Параметры&gt; элемент (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
caps.latest.revision: "21"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 07f356c0425b071ac320e702a9ba7cd6b9537341
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltsettingsgt-element-network-settings"></a><span data-ttu-id="5c7b5-102">&lt;Параметры&gt; элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="5c7b5-102">&lt;settings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="5c7b5-103">Настраивает основные параметры сети для пространства имен <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c7b5-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="5c7b5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5c7b5-104">\<configuration></span></span>  
<span data-ttu-id="5c7b5-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="5c7b5-105">\<system.net></span></span>  
<span data-ttu-id="5c7b5-106">\<Параметры ></span><span class="sxs-lookup"><span data-stu-id="5c7b5-106">\<settings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c7b5-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c7b5-107">Syntax</span></span>  
  
```xml  
<settings>  
  <httpListener> … </httpListener>  
  <httpWebRequest> … </httpWebRequest>  
  <ipv6> … </ipv6>  
  <performanceCounters> … </performanceCounters>  
  <servicePointManager> … </servicePointManager>  
  <socket> … </socket>  
  <webProxyScript> … </webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c7b5-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5c7b5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5c7b5-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5c7b5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c7b5-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5c7b5-110">Attributes</span></span>  
 <span data-ttu-id="5c7b5-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5c7b5-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5c7b5-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5c7b5-112">Child Elements</span></span>  
  
|<span data-ttu-id="5c7b5-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="5c7b5-113">Element</span></span>|<span data-ttu-id="5c7b5-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5c7b5-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c7b5-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="5c7b5-115">httpListener</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|<span data-ttu-id="5c7b5-116">Настраивает параметры, используемые <xref:System.Net.HttpListener> класса.</span><span class="sxs-lookup"><span data-stu-id="5c7b5-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="5c7b5-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="5c7b5-117">httpWebRequest</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|<span data-ttu-id="5c7b5-118">Настраивает параметры веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="5c7b5-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="5c7b5-119">IPv6</span><span class="sxs-lookup"><span data-stu-id="5c7b5-119">ipv6</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|<span data-ttu-id="5c7b5-120">Протокол IP версии 6 (IPv6) позволяет поддерживать.</span><span class="sxs-lookup"><span data-stu-id="5c7b5-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="5c7b5-121">\<performanceCounter > Element (Network Settings)</span><span class="sxs-lookup"><span data-stu-id="5c7b5-121">\<performanceCounter> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|<span data-ttu-id="5c7b5-122">Включает счетчики производительности сети.</span><span class="sxs-lookup"><span data-stu-id="5c7b5-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="5c7b5-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="5c7b5-123">servicePointManager</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|<span data-ttu-id="5c7b5-124">Настраивает подключения к сетевым ресурсам.</span><span class="sxs-lookup"><span data-stu-id="5c7b5-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="5c7b5-125">сокет</span><span class="sxs-lookup"><span data-stu-id="5c7b5-125">socket</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|<span data-ttu-id="5c7b5-126">Указывает, используют ли операции сокета порты завершения.</span><span class="sxs-lookup"><span data-stu-id="5c7b5-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="5c7b5-127">\<webProxyScript > Element (Network Settings)</span><span class="sxs-lookup"><span data-stu-id="5c7b5-127">\<webProxyScript> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|<span data-ttu-id="5c7b5-128">Настраивает характеристики сценария для обнаружения веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="5c7b5-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5c7b5-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5c7b5-129">Parent Elements</span></span>  
  
|<span data-ttu-id="5c7b5-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="5c7b5-130">Element</span></span>|<span data-ttu-id="5c7b5-131">Описание</span><span class="sxs-lookup"><span data-stu-id="5c7b5-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c7b5-132">System.NET</span><span class="sxs-lookup"><span data-stu-id="5c7b5-132">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="5c7b5-133">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="5c7b5-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c7b5-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c7b5-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5c7b5-135">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="5c7b5-135">Configuration Files</span></span>  
 <span data-ttu-id="5c7b5-136">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5c7b5-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c7b5-137">См. также</span><span class="sxs-lookup"><span data-stu-id="5c7b5-137">See Also</span></span>  
 <xref:System.Net?displayProperty=nameWithType>  
 [<span data-ttu-id="5c7b5-138">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="5c7b5-138">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
