---
title: Элемент <system.Net> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 810e942394c75c192e4423afe4c674ef3a2b9900
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697508"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="aaac2-102">Элемент \<system.Net> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="aaac2-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="aaac2-103">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="aaac2-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[<span data-ttu-id="aaac2-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="aaac2-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="aaac2-105">&nbsp;&nbsp; **\<System. net >**</span><span class="sxs-lookup"><span data-stu-id="aaac2-105">&nbsp;&nbsp;**\<system.net>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaac2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aaac2-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aaac2-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aaac2-107">Attributes and Elements</span></span>  
 <span data-ttu-id="aaac2-108">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aaac2-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aaac2-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aaac2-109">Attributes</span></span>  
 <span data-ttu-id="aaac2-110">Нет</span><span class="sxs-lookup"><span data-stu-id="aaac2-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aaac2-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aaac2-111">Child Elements</span></span>  
  
|<span data-ttu-id="aaac2-112">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="aaac2-112">**Element**</span></span>|<span data-ttu-id="aaac2-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="aaac2-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="aaac2-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="aaac2-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="aaac2-115">Указывает модули, используемые для проверки подлинности интернет запросов.</span><span class="sxs-lookup"><span data-stu-id="aaac2-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="aaac2-116">Элемент connectionManagement</span><span class="sxs-lookup"><span data-stu-id="aaac2-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="aaac2-117">Указывает максимальное число подключений к узлу в Интернете.</span><span class="sxs-lookup"><span data-stu-id="aaac2-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="aaac2-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="aaac2-118">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="aaac2-119">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="aaac2-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="aaac2-120">маилсеттингс</span><span class="sxs-lookup"><span data-stu-id="aaac2-120">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="aaac2-121">Настраивает параметры отправки почты по протоколу SMTP.</span><span class="sxs-lookup"><span data-stu-id="aaac2-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="aaac2-122">Элемент requestcaching</span><span class="sxs-lookup"><span data-stu-id="aaac2-122">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="aaac2-123">Управляет механизмом кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="aaac2-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="aaac2-124">Параметры</span><span class="sxs-lookup"><span data-stu-id="aaac2-124">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="aaac2-125">Настраивает основные сетевые параметры для классов в <xref:System.Net> и связанных с ними дочерних пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="aaac2-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="aaac2-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="aaac2-126">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="aaac2-127">Указывает модули, используемые для запроса информации от узлов Интернета.</span><span class="sxs-lookup"><span data-stu-id="aaac2-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aaac2-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aaac2-128">Parent Elements</span></span>  
  
|<span data-ttu-id="aaac2-129">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="aaac2-129">**Element**</span></span>|<span data-ttu-id="aaac2-130">**Описание**</span><span class="sxs-lookup"><span data-stu-id="aaac2-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="aaac2-131">Настройка</span><span class="sxs-lookup"><span data-stu-id="aaac2-131">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="aaac2-132">Содержит параметры для всех пространств имен.</span><span class="sxs-lookup"><span data-stu-id="aaac2-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aaac2-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="aaac2-133">Remarks</span></span>  
 <span data-ttu-id="aaac2-134">Элемент [\<System. net >](system-net-element-network-settings.md) содержит параметры для классов в <xref:System.Net> и связанных дочерних пространств имен.</span><span class="sxs-lookup"><span data-stu-id="aaac2-134">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="aaac2-135">Параметры настройки модулей проверки подлинности, управления подключениями, параметров почты, прокси-сервера и модулей запросов Интернета для получения данных от узлов Интернета.</span><span class="sxs-lookup"><span data-stu-id="aaac2-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaac2-136">Пример</span><span class="sxs-lookup"><span data-stu-id="aaac2-136">Example</span></span>  
 <span data-ttu-id="aaac2-137">В следующем примере показана типичная конфигурация, используемая классами <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="aaac2-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="aaac2-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="aaac2-138">See also</span></span>

- [<span data-ttu-id="aaac2-139">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="aaac2-139">Network Settings Schema</span></span>](index.md)
