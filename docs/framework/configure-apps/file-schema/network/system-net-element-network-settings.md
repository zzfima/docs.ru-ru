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
ms.openlocfilehash: 88098f2afaad9728e38c4f9935b45f45826a0ca9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154560"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="43431-102">Элемент \<system.Net> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="43431-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="43431-103">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="43431-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[<span data-ttu-id="43431-104">**\<конфигурация>**</span><span class="sxs-lookup"><span data-stu-id="43431-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="43431-105">&nbsp;&nbsp;**\<system.net>**</span><span class="sxs-lookup"><span data-stu-id="43431-105">&nbsp;&nbsp;**\<system.net>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43431-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43431-106">Syntax</span></span>  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43431-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="43431-107">Attributes and Elements</span></span>  
 <span data-ttu-id="43431-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="43431-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43431-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="43431-109">Attributes</span></span>  
 <span data-ttu-id="43431-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="43431-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="43431-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="43431-111">Child Elements</span></span>  
  
|<span data-ttu-id="43431-112">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="43431-112">**Element**</span></span>|<span data-ttu-id="43431-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="43431-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="43431-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="43431-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="43431-115">Определяет модули, используемые для проверки подлинности запросов в Интернете.</span><span class="sxs-lookup"><span data-stu-id="43431-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="43431-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="43431-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="43431-117">Определяет максимальное количество подключений к интернет-хостам.</span><span class="sxs-lookup"><span data-stu-id="43431-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="43431-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="43431-118">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="43431-119">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="43431-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="43431-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="43431-120">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="43431-121">Настраивает опции отправки почты Simple Mail Transport Protocol (SMTP).</span><span class="sxs-lookup"><span data-stu-id="43431-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="43431-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="43431-122">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="43431-123">Контролирует механизм кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="43431-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="43431-124">настройки</span><span class="sxs-lookup"><span data-stu-id="43431-124">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="43431-125">Настраивает основные сетевые <xref:System.Net> параметры для классов в и связанных с ними областях имен детей.</span><span class="sxs-lookup"><span data-stu-id="43431-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="43431-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="43431-126">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="43431-127">Определяет модули для использования для запроса информации у интернет-хостов.</span><span class="sxs-lookup"><span data-stu-id="43431-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="43431-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="43431-128">Parent Elements</span></span>  
  
|<span data-ttu-id="43431-129">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="43431-129">**Element**</span></span>|<span data-ttu-id="43431-130">**Описание**</span><span class="sxs-lookup"><span data-stu-id="43431-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="43431-131">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="43431-131">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="43431-132">Содержит настройки для всех областей имен.</span><span class="sxs-lookup"><span data-stu-id="43431-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43431-133">Remarks</span><span class="sxs-lookup"><span data-stu-id="43431-133">Remarks</span></span>  
 <span data-ttu-id="43431-134">Элемент [ \<system.net>](system-net-element-network-settings.md) содержит настройки <xref:System.Net> для классов в и связанных с ними областях имен ребенка.</span><span class="sxs-lookup"><span data-stu-id="43431-134">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="43431-135">Настройки настраивают модули аутентификации, управление подключением, настройки почты, прокси-сервер и модули запросов Интернета для получения информации от интернет-хостов.</span><span class="sxs-lookup"><span data-stu-id="43431-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43431-136">Пример</span><span class="sxs-lookup"><span data-stu-id="43431-136">Example</span></span>  
 <span data-ttu-id="43431-137">В следующем примере показана <xref:System.Net> типичная конфигурация, используемая классами.</span><span class="sxs-lookup"><span data-stu-id="43431-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="43431-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="43431-138">See also</span></span>

- [<span data-ttu-id="43431-139">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="43431-139">Network Settings Schema</span></span>](index.md)
