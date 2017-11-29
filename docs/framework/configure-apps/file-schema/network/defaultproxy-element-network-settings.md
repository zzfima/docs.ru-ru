---
title: "&lt;defaultProxy&gt; элемент (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
caps.latest.revision: "21"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5fb58c01f8a8e3135878036454a1265e6b92e939
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltdefaultproxygt-element-network-settings"></a><span data-ttu-id="329fb-102">&lt;defaultProxy&gt; элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="329fb-102">&lt;defaultProxy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="329fb-103">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="329fb-103">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
 <span data-ttu-id="329fb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="329fb-104">\<configuration></span></span>  
<span data-ttu-id="329fb-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="329fb-105">\<system.net></span></span>  
<span data-ttu-id="329fb-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="329fb-106">\<defaultProxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="329fb-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="329fb-107">Syntax</span></span>  
  
```xml  
      <defaultProxy  
        enabled="true|false"  
        useDefaultCredentials="true|false">  
           <bypasslist> … </bypasslist>  
           <proxy> … </proxy>  
           <module> … </module>  
      </defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="329fb-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="329fb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="329fb-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="329fb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="329fb-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="329fb-110">Attributes</span></span>  
  
|<span data-ttu-id="329fb-111">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="329fb-111">**Element**</span></span>|<span data-ttu-id="329fb-112">**Описание**</span><span class="sxs-lookup"><span data-stu-id="329fb-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="329fb-113">Указывает, используется ли веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="329fb-113">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="329fb-114">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="329fb-114">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="329fb-115">Указывает, используются ли учетные данные по умолчанию для этого узла для доступа к веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="329fb-115">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="329fb-116">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="329fb-116">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="329fb-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="329fb-117">Child Elements</span></span>  
  
|<span data-ttu-id="329fb-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="329fb-118">**Element**</span></span>|<span data-ttu-id="329fb-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="329fb-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="329fb-120">bypasslist</span><span class="sxs-lookup"><span data-stu-id="329fb-120">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="329fb-121">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="329fb-121">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="329fb-122">модуль</span><span class="sxs-lookup"><span data-stu-id="329fb-122">module</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md)|<span data-ttu-id="329fb-123">Добавляет в приложение новый модуль прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="329fb-123">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="329fb-124">прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="329fb-124">proxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md)|<span data-ttu-id="329fb-125">Определяет прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="329fb-125">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="329fb-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="329fb-126">Parent Elements</span></span>  
  
|<span data-ttu-id="329fb-127">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="329fb-127">**Element**</span></span>|<span data-ttu-id="329fb-128">**Описание**</span><span class="sxs-lookup"><span data-stu-id="329fb-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="329fb-129">System.NET</span><span class="sxs-lookup"><span data-stu-id="329fb-129">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="329fb-130">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="329fb-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="329fb-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="329fb-131">Remarks</span></span>  
 <span data-ttu-id="329fb-132">Если элемент defaultProxy пуст, будут использоваться параметры прокси-сервера из Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="329fb-132">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="329fb-133">Это поведение отличается от поведения в .NET Framework версии 1.1.</span><span class="sxs-lookup"><span data-stu-id="329fb-133">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="329fb-134">Исключение возникает, если [модуль](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md) элемент задает тип закрытым, тип не является производным от <xref:System.Net.IWebProxy> класса, произошло исключение в конструкторе по умолчанию для этого объекта или возникло исключение во время Получение прокси-сервера по умолчанию, заданного в системе.</span><span class="sxs-lookup"><span data-stu-id="329fb-134">An exception is thrown if the [module](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the default constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="329fb-135">Свойство <xref:System.Exception.InnerException%2A> исключения должно иметь дополнительные сведения о корневой причине ошибки.</span><span class="sxs-lookup"><span data-stu-id="329fb-135">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="329fb-136">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="329fb-136">Configuration Files</span></span>  
 <span data-ttu-id="329fb-137">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="329fb-137">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="329fb-138">Пример</span><span class="sxs-lookup"><span data-stu-id="329fb-138">Example</span></span>  
 <span data-ttu-id="329fb-139">Следующий пример использует значения по умолчанию из прокси-сервера обозревателя Internet Explorer, указывает адрес прокси-сервера и обходит прокси-сервер для локальных адресов и домена contoso.com.</span><span class="sxs-lookup"><span data-stu-id="329fb-139">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="329fb-140">См. также</span><span class="sxs-lookup"><span data-stu-id="329fb-140">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="329fb-141">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="329fb-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
