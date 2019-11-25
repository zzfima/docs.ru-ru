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
ms.openlocfilehash: d510c445c585a36005ed415b14188efc4be03984
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089108"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="b57f3-102">Элемент > параметров \<(параметры сети)</span><span class="sxs-lookup"><span data-stu-id="b57f3-102">\<settings> Element (Network Settings)</span></span>
<span data-ttu-id="b57f3-103">Настраивает основные параметры сети для пространства имен <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b57f3-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  

<span data-ttu-id="b57f3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b57f3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b57f3-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b57f3-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="b57f3-106">&nbsp;&nbsp;&nbsp;&nbsp;**Параметры**\<</span><span class="sxs-lookup"><span data-stu-id="b57f3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<settings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b57f3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b57f3-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b57f3-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b57f3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b57f3-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b57f3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b57f3-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b57f3-110">Attributes</span></span>  
 <span data-ttu-id="b57f3-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b57f3-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b57f3-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b57f3-112">Child Elements</span></span>  
  
|<span data-ttu-id="b57f3-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="b57f3-113">Element</span></span>|<span data-ttu-id="b57f3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b57f3-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b57f3-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="b57f3-115">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="b57f3-116">Настраивает параметры, используемые классом <xref:System.Net.HttpListener>.</span><span class="sxs-lookup"><span data-stu-id="b57f3-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="b57f3-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="b57f3-117">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="b57f3-118">Настраивает параметры веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="b57f3-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="b57f3-119">Протокол</span><span class="sxs-lookup"><span data-stu-id="b57f3-119">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="b57f3-120">Включает поддержку протокола IP версии 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="b57f3-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="b57f3-121">\<элемента > performanceCounter (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="b57f3-121">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="b57f3-122">Включает счетчики производительности сети.</span><span class="sxs-lookup"><span data-stu-id="b57f3-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="b57f3-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="b57f3-123">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="b57f3-124">Настраивает подключения к сетевым ресурсам.</span><span class="sxs-lookup"><span data-stu-id="b57f3-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="b57f3-125">фиксатор</span><span class="sxs-lookup"><span data-stu-id="b57f3-125">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="b57f3-126">Указывает, используют ли операции сокета порты завершения.</span><span class="sxs-lookup"><span data-stu-id="b57f3-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="b57f3-127">Элемент \<Вебпроксискрипт > (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="b57f3-127">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="b57f3-128">Настраивает характеристики сценария, используемого для обнаружения веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="b57f3-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b57f3-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b57f3-129">Parent Elements</span></span>  
  
|<span data-ttu-id="b57f3-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="b57f3-130">Element</span></span>|<span data-ttu-id="b57f3-131">Описание</span><span class="sxs-lookup"><span data-stu-id="b57f3-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b57f3-132">system.net</span><span class="sxs-lookup"><span data-stu-id="b57f3-132">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="b57f3-133">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="b57f3-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b57f3-134">Заметки</span><span class="sxs-lookup"><span data-stu-id="b57f3-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b57f3-135">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="b57f3-135">Configuration Files</span></span>  
 <span data-ttu-id="b57f3-136">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b57f3-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b57f3-137">См. также</span><span class="sxs-lookup"><span data-stu-id="b57f3-137">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="b57f3-138">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="b57f3-138">Network Settings Schema</span></span>](index.md)
