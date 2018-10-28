---
title: '&lt;system.Net&gt; (сетевые параметры)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 82e022e28d3559791be3236fb80081807426a456
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192542"
---
# <a name="ltsystemnetgt-element-network-settings"></a><span data-ttu-id="bdf61-102">&lt;system.Net&gt; (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="bdf61-102">&lt;system.Net&gt; Element (Network Settings)</span></span>
<span data-ttu-id="bdf61-103">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="bdf61-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
 <span data-ttu-id="bdf61-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bdf61-104">\<configuration></span></span>  
<span data-ttu-id="bdf61-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="bdf61-105">\<system.net></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdf61-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdf61-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bdf61-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bdf61-107">Attributes and Elements</span></span>  
 <span data-ttu-id="bdf61-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bdf61-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdf61-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bdf61-109">Attributes</span></span>  
 <span data-ttu-id="bdf61-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bdf61-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bdf61-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bdf61-111">Child Elements</span></span>  
  
|<span data-ttu-id="bdf61-112">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="bdf61-112">**Element**</span></span>|<span data-ttu-id="bdf61-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="bdf61-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bdf61-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="bdf61-114">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="bdf61-115">Задает модули, используемые для проверки подлинности Интернет-запросов.</span><span class="sxs-lookup"><span data-stu-id="bdf61-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="bdf61-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="bdf61-116">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="bdf61-117">Указывает максимальное число подключений к Интернет-узле.</span><span class="sxs-lookup"><span data-stu-id="bdf61-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="bdf61-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="bdf61-118">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="bdf61-119">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="bdf61-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="bdf61-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="bdf61-120">mailSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="bdf61-121">Настраивает параметры отправки сообщений транспортного протокола SMTP (Simple Mail).</span><span class="sxs-lookup"><span data-stu-id="bdf61-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="bdf61-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="bdf61-122">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="bdf61-123">Определяет механизм кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="bdf61-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="bdf61-124">Параметры</span><span class="sxs-lookup"><span data-stu-id="bdf61-124">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="bdf61-125">Настраивает основные параметры сети для классов в <xref:System.Net> и связанные с ней дочерние пространства имен.</span><span class="sxs-lookup"><span data-stu-id="bdf61-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="bdf61-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="bdf61-126">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="bdf61-127">Задает модули, используемые для запроса данных из Интернет-узлов.</span><span class="sxs-lookup"><span data-stu-id="bdf61-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bdf61-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bdf61-128">Parent Elements</span></span>  
  
|<span data-ttu-id="bdf61-129">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="bdf61-129">**Element**</span></span>|<span data-ttu-id="bdf61-130">**Описание**</span><span class="sxs-lookup"><span data-stu-id="bdf61-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bdf61-131">Конфигурации</span><span class="sxs-lookup"><span data-stu-id="bdf61-131">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="bdf61-132">Содержит параметры для всех пространств имен.</span><span class="sxs-lookup"><span data-stu-id="bdf61-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdf61-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="bdf61-133">Remarks</span></span>  
 <span data-ttu-id="bdf61-134">[ \<System.net >](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) элемент содержит параметры для классов в <xref:System.Net> и связанные с ней дочерние пространства имен.</span><span class="sxs-lookup"><span data-stu-id="bdf61-134">The [\<system.net>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="bdf61-135">Параметры настройки модулей проверки подлинности, управление подключениями, параметры электронной почты, прокси-сервера и модулей Интернет-запросов на получение информации от Интернет-узлов.</span><span class="sxs-lookup"><span data-stu-id="bdf61-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdf61-136">Пример</span><span class="sxs-lookup"><span data-stu-id="bdf61-136">Example</span></span>  
 <span data-ttu-id="bdf61-137">В следующем примере показано Типовая конфигурация, используемая с <xref:System.Net> классы.</span><span class="sxs-lookup"><span data-stu-id="bdf61-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bdf61-138">См. также</span><span class="sxs-lookup"><span data-stu-id="bdf61-138">See Also</span></span>  
- [<span data-ttu-id="bdf61-139">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="bdf61-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
