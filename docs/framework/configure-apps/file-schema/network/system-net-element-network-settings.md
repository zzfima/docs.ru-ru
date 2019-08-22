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
ms.openlocfilehash: 449146612938700f59f5e2ec761526d1dc66a3fc
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663960"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="293e0-102">Элемент \<system.Net> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="293e0-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="293e0-103">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="293e0-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
 <span data-ttu-id="293e0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="293e0-104">\<configuration></span></span>  
<span data-ttu-id="293e0-105">\<> System. NET</span><span class="sxs-lookup"><span data-stu-id="293e0-105">\<system.net></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="293e0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="293e0-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="293e0-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="293e0-107">Attributes and Elements</span></span>  
 <span data-ttu-id="293e0-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="293e0-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="293e0-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="293e0-109">Attributes</span></span>  
 <span data-ttu-id="293e0-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="293e0-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="293e0-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="293e0-111">Child Elements</span></span>  
  
|<span data-ttu-id="293e0-112">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="293e0-112">**Element**</span></span>|<span data-ttu-id="293e0-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="293e0-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="293e0-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="293e0-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="293e0-115">Указывает модули, используемые для проверки подлинности интернет запросов.</span><span class="sxs-lookup"><span data-stu-id="293e0-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="293e0-116">Элемент connectionManagement</span><span class="sxs-lookup"><span data-stu-id="293e0-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="293e0-117">Указывает максимальное число подключений к узлу в Интернете.</span><span class="sxs-lookup"><span data-stu-id="293e0-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="293e0-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="293e0-118">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="293e0-119">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="293e0-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="293e0-120">маилсеттингс</span><span class="sxs-lookup"><span data-stu-id="293e0-120">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="293e0-121">Настраивает параметры отправки почты по протоколу SMTP.</span><span class="sxs-lookup"><span data-stu-id="293e0-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="293e0-122">Элемент requestcaching</span><span class="sxs-lookup"><span data-stu-id="293e0-122">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="293e0-123">Управляет механизмом кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="293e0-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="293e0-124">Параметры</span><span class="sxs-lookup"><span data-stu-id="293e0-124">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="293e0-125">Настраивает основные сетевые параметры для классов в <xref:System.Net> и связанных дочерних пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="293e0-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="293e0-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="293e0-126">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="293e0-127">Указывает модули, используемые для запроса информации от узлов Интернета.</span><span class="sxs-lookup"><span data-stu-id="293e0-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="293e0-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="293e0-128">Parent Elements</span></span>  
  
|<span data-ttu-id="293e0-129">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="293e0-129">**Element**</span></span>|<span data-ttu-id="293e0-130">**Описание**</span><span class="sxs-lookup"><span data-stu-id="293e0-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="293e0-131">Настройка</span><span class="sxs-lookup"><span data-stu-id="293e0-131">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="293e0-132">Содержит параметры для всех пространств имен.</span><span class="sxs-lookup"><span data-stu-id="293e0-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="293e0-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="293e0-133">Remarks</span></span>  
 <span data-ttu-id="293e0-134"><xref:System.Net> [ ЭлементSystem.NET>содержитпараметрыдляклассоввсвязанных\<](system-net-element-network-settings.md) дочерних пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="293e0-134">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="293e0-135">Параметры настройки модулей проверки подлинности, управления подключениями, параметров почты, прокси-сервера и модулей запросов Интернета для получения данных от узлов Интернета.</span><span class="sxs-lookup"><span data-stu-id="293e0-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="293e0-136">Пример</span><span class="sxs-lookup"><span data-stu-id="293e0-136">Example</span></span>  
 <span data-ttu-id="293e0-137">В следующем примере показана типичная конфигурация, <xref:System.Net> используемая классами.</span><span class="sxs-lookup"><span data-stu-id="293e0-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="293e0-138">См. также</span><span class="sxs-lookup"><span data-stu-id="293e0-138">See also</span></span>

- [<span data-ttu-id="293e0-139">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="293e0-139">Network Settings Schema</span></span>](index.md)
