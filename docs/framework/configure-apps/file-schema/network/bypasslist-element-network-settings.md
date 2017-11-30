---
title: "&lt;bypasslist&gt; элемент (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3d349f14535de806e0b130ef64b58333e63f1b86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltbypasslistgt-element-network-settings"></a><span data-ttu-id="f39cd-102">&lt;bypasslist&gt; элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="f39cd-102">&lt;bypasslist&gt; Element (Network Settings)</span></span>
<span data-ttu-id="f39cd-103">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="f39cd-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="f39cd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f39cd-104">\<configuration></span></span>  
<span data-ttu-id="f39cd-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="f39cd-105">\<system.net></span></span>  
<span data-ttu-id="f39cd-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="f39cd-106">\<defaultProxy></span></span>  
<span data-ttu-id="f39cd-107">\<bypasslist ></span><span class="sxs-lookup"><span data-stu-id="f39cd-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f39cd-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f39cd-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f39cd-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f39cd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f39cd-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f39cd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f39cd-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f39cd-111">Attributes</span></span>  
 <span data-ttu-id="f39cd-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f39cd-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f39cd-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f39cd-113">Child Elements</span></span>  
  
|<span data-ttu-id="f39cd-114">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="f39cd-114">**Element**</span></span>|<span data-ttu-id="f39cd-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f39cd-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f39cd-116">add</span><span class="sxs-lookup"><span data-stu-id="f39cd-116">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="f39cd-117">Добавляет IP-адрес или DNS-имя в список обхода прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="f39cd-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="f39cd-118">clear</span><span class="sxs-lookup"><span data-stu-id="f39cd-118">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="f39cd-119">Очищает список обхода.</span><span class="sxs-lookup"><span data-stu-id="f39cd-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="f39cd-120">remove</span><span class="sxs-lookup"><span data-stu-id="f39cd-120">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="f39cd-121">Удаляет IP-адрес или DNS-имя из списка обхода прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="f39cd-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f39cd-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f39cd-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f39cd-123">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="f39cd-123">**Element**</span></span>|<span data-ttu-id="f39cd-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f39cd-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f39cd-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="f39cd-125">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="f39cd-126">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="f39cd-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f39cd-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="f39cd-127">Remarks</span></span>  
 <span data-ttu-id="f39cd-128">Список пропускаемых содержит регулярных выражений, описывающих URI, <xref:System.Net.WebRequest> экземпляры доступ напрямую вместо того, через прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="f39cd-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="f39cd-129">Следует проявлять осторожность при вводе регулярного выражения для данного элемента.</span><span class="sxs-lookup"><span data-stu-id="f39cd-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="f39cd-130">Регулярное выражение «[a-z] +\\.contoso\\.com» совпадает с любого узла в домене contoso.com, но он также соответствует любому узлу в contoso.com.cpandl.com домена.</span><span class="sxs-lookup"><span data-stu-id="f39cd-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="f39cd-131">Чтобы соответствовать только одному узлу в домене contoso.com, используйте элемент привязки («$»): «[a-z] +\\.contoso\\.com$».</span><span class="sxs-lookup"><span data-stu-id="f39cd-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="f39cd-132">Дополнительные сведения о регулярных выражениях см. в разделе. [Регулярные выражения .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f39cd-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f39cd-133">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="f39cd-133">Configuration Files</span></span>  
 <span data-ttu-id="f39cd-134">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f39cd-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f39cd-135">Пример</span><span class="sxs-lookup"><span data-stu-id="f39cd-135">Example</span></span>  
 <span data-ttu-id="f39cd-136">Список пропускаемых в следующем примере добавляются два адреса.</span><span class="sxs-lookup"><span data-stu-id="f39cd-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="f39cd-137">Первый обход прокси-сервера для всех серверов в домене contoso.com. второй обход прокси-сервера для всех серверов, IP-адреса которых начинаются с 192.168.</span><span class="sxs-lookup"><span data-stu-id="f39cd-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f39cd-138">См. также</span><span class="sxs-lookup"><span data-stu-id="f39cd-138">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="f39cd-139">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="f39cd-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
