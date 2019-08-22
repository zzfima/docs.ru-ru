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
ms.openlocfilehash: 12797e2f06d03aacd81700eae57d5776c1a6f354
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663999"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="e673f-102">\<Элемент параметров > (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="e673f-102">\<settings> Element (Network Settings)</span></span>
<span data-ttu-id="e673f-103">Настраивает основные параметры сети для пространства имен <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e673f-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="e673f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e673f-104">\<configuration></span></span>  
<span data-ttu-id="e673f-105">\<> System. NET</span><span class="sxs-lookup"><span data-stu-id="e673f-105">\<system.net></span></span>  
<span data-ttu-id="e673f-106">\<> параметров</span><span class="sxs-lookup"><span data-stu-id="e673f-106">\<settings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e673f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e673f-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e673f-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e673f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e673f-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e673f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e673f-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e673f-110">Attributes</span></span>  
 <span data-ttu-id="e673f-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="e673f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e673f-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e673f-112">Child Elements</span></span>  
  
|<span data-ttu-id="e673f-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="e673f-113">Element</span></span>|<span data-ttu-id="e673f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e673f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e673f-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="e673f-115">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="e673f-116">Настраивает параметры, используемые <xref:System.Net.HttpListener> классом.</span><span class="sxs-lookup"><span data-stu-id="e673f-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="e673f-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="e673f-117">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="e673f-118">Настраивает параметры веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="e673f-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="e673f-119">Протокол</span><span class="sxs-lookup"><span data-stu-id="e673f-119">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="e673f-120">Включает поддержку протокола IP версии 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="e673f-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="e673f-121">\<Элемент performanceCounter > (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="e673f-121">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="e673f-122">Включает счетчики производительности сети.</span><span class="sxs-lookup"><span data-stu-id="e673f-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="e673f-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="e673f-123">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="e673f-124">Настраивает подключения к сетевым ресурсам.</span><span class="sxs-lookup"><span data-stu-id="e673f-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="e673f-125">фиксатор</span><span class="sxs-lookup"><span data-stu-id="e673f-125">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="e673f-126">Указывает, используют ли операции сокета порты завершения.</span><span class="sxs-lookup"><span data-stu-id="e673f-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="e673f-127">\<Элемент > Вебпроксискрипт (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="e673f-127">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="e673f-128">Настраивает характеристики сценария, используемого для обнаружения веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="e673f-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e673f-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e673f-129">Parent Elements</span></span>  
  
|<span data-ttu-id="e673f-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="e673f-130">Element</span></span>|<span data-ttu-id="e673f-131">Описание</span><span class="sxs-lookup"><span data-stu-id="e673f-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e673f-132">system.net</span><span class="sxs-lookup"><span data-stu-id="e673f-132">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="e673f-133">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="e673f-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e673f-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="e673f-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e673f-135">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="e673f-135">Configuration Files</span></span>  
 <span data-ttu-id="e673f-136">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e673f-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e673f-137">См. также</span><span class="sxs-lookup"><span data-stu-id="e673f-137">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="e673f-138">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="e673f-138">Network Settings Schema</span></span>](index.md)
