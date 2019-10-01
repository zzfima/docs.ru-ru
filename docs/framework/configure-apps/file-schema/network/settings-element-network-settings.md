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
ms.openlocfilehash: ba08f630dc602c950da309bf29482d85b41af7ef
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697682"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="f0e79-102">Элемент > @no__t 0settings (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="f0e79-102">\<settings> Element (Network Settings)</span></span>
<span data-ttu-id="f0e79-103">Настраивает основные параметры сети для пространства имен <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f0e79-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
[<span data-ttu-id="f0e79-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f0e79-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f0e79-105">&nbsp; @ no__t-1[ **@no__t -4system. NET >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f0e79-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="f0e79-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<settings >**</span><span class="sxs-lookup"><span data-stu-id="f0e79-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<settings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0e79-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0e79-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0e79-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f0e79-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f0e79-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f0e79-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0e79-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f0e79-110">Attributes</span></span>  
 <span data-ttu-id="f0e79-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="f0e79-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f0e79-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f0e79-112">Child Elements</span></span>  
  
|<span data-ttu-id="f0e79-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="f0e79-113">Element</span></span>|<span data-ttu-id="f0e79-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f0e79-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0e79-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="f0e79-115">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="f0e79-116">Настраивает параметры, используемые классом <xref:System.Net.HttpListener>.</span><span class="sxs-lookup"><span data-stu-id="f0e79-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="f0e79-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="f0e79-117">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="f0e79-118">Настраивает параметры веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="f0e79-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="f0e79-119">Протокол</span><span class="sxs-lookup"><span data-stu-id="f0e79-119">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="f0e79-120">Включает поддержку протокола IP версии 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="f0e79-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="f0e79-121">Элемент > @no__t 1performanceCounter (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="f0e79-121">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="f0e79-122">Включает счетчики производительности сети.</span><span class="sxs-lookup"><span data-stu-id="f0e79-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="f0e79-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="f0e79-123">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="f0e79-124">Настраивает подключения к сетевым ресурсам.</span><span class="sxs-lookup"><span data-stu-id="f0e79-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="f0e79-125">фиксатор</span><span class="sxs-lookup"><span data-stu-id="f0e79-125">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="f0e79-126">Указывает, используют ли операции сокета порты завершения.</span><span class="sxs-lookup"><span data-stu-id="f0e79-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="f0e79-127">Элемент > @no__t 1webProxyScript (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="f0e79-127">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="f0e79-128">Настраивает характеристики сценария, используемого для обнаружения веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="f0e79-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f0e79-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f0e79-129">Parent Elements</span></span>  
  
|<span data-ttu-id="f0e79-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="f0e79-130">Element</span></span>|<span data-ttu-id="f0e79-131">Описание</span><span class="sxs-lookup"><span data-stu-id="f0e79-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0e79-132">system.net</span><span class="sxs-lookup"><span data-stu-id="f0e79-132">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="f0e79-133">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="f0e79-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0e79-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0e79-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f0e79-135">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="f0e79-135">Configuration Files</span></span>  
 <span data-ttu-id="f0e79-136">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f0e79-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0e79-137">См. также</span><span class="sxs-lookup"><span data-stu-id="f0e79-137">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="f0e79-138">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="f0e79-138">Network Settings Schema</span></span>](index.md)
