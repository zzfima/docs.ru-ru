---
title: '&lt;Добавление&gt; элемент для bypasslist (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
author: mcleblanc
ms.author: markl
ms.openlocfilehash: b6cf22fcaff928e53c33a8eb4987acd5a7f6250e
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48779118"
---
# <a name="ltaddgt-element-for-bypasslist-network-settings"></a><span data-ttu-id="1faac-102">&lt;Добавление&gt; элемент для bypasslist (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="1faac-102">&lt;add&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="1faac-103">Добавляет IP-адрес или DNS-имя в список обхода прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="1faac-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
 <span data-ttu-id="1faac-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1faac-104">\<configuration></span></span>  
<span data-ttu-id="1faac-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="1faac-105">\<system.net></span></span>  
<span data-ttu-id="1faac-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="1faac-106">\<defaultProxy></span></span>  
<span data-ttu-id="1faac-107">\<bypasslist ></span><span class="sxs-lookup"><span data-stu-id="1faac-107">\<bypasslist></span></span>  
<span data-ttu-id="1faac-108">\<add></span><span class="sxs-lookup"><span data-stu-id="1faac-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1faac-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1faac-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1faac-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1faac-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1faac-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1faac-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1faac-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1faac-112">Attributes</span></span>  
  
|<span data-ttu-id="1faac-113">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="1faac-113">**Attribute**</span></span>|<span data-ttu-id="1faac-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1faac-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="1faac-115">**address**</span><span class="sxs-lookup"><span data-stu-id="1faac-115">**address**</span></span>|<span data-ttu-id="1faac-116">Регулярное выражение, описывающее IP-адрес или DNS-имя.</span><span class="sxs-lookup"><span data-stu-id="1faac-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1faac-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1faac-117">Child Elements</span></span>  
 <span data-ttu-id="1faac-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1faac-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1faac-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1faac-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1faac-120">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="1faac-120">**Element**</span></span>|<span data-ttu-id="1faac-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1faac-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1faac-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="1faac-122">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="1faac-123">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="1faac-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1faac-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="1faac-124">Remarks</span></span>  
 <span data-ttu-id="1faac-125">`add` Элемент вставляет регулярное выражение, описывающее IP-адреса или имена DNS-серверов в список адресов, которые обходят прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="1faac-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="1faac-126">Значение `address` атрибут должен быть регулярное выражение, которое описывает набор IP-адресов или имен узлов.</span><span class="sxs-lookup"><span data-stu-id="1faac-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="1faac-127">Будьте внимательны при указании регулярное выражение для этого элемента.</span><span class="sxs-lookup"><span data-stu-id="1faac-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="1faac-128">Регулярное выражение «[a-z] +\\.contoso\\.com» совпадений, любого узла в домене contoso.com, но он также соответствует любому узлу в contoso.com.cpandl.com домена.</span><span class="sxs-lookup"><span data-stu-id="1faac-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="1faac-129">Чтобы сопоставить только на узле в домене contoso.com, используйте привязку («$»): «[a-z] +\\.contoso\\.com$».</span><span class="sxs-lookup"><span data-stu-id="1faac-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="1faac-130">Дополнительные сведения о регулярных выражениях см. в разделе. [Регулярные выражения .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="1faac-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1faac-131">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="1faac-131">Configuration Files</span></span>  
 <span data-ttu-id="1faac-132">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="1faac-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1faac-133">Пример</span><span class="sxs-lookup"><span data-stu-id="1faac-133">Example</span></span>  
 <span data-ttu-id="1faac-134">Следующий пример добавляет два адреса в списке пропускаемых адресов.</span><span class="sxs-lookup"><span data-stu-id="1faac-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="1faac-135">Первый обходит прокси-сервер для всех серверов в домене contoso.com. второй обходит прокси-сервер для всех серверов, IP-адрес начинается с 192.168.</span><span class="sxs-lookup"><span data-stu-id="1faac-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1faac-136">См. также</span><span class="sxs-lookup"><span data-stu-id="1faac-136">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="1faac-137">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="1faac-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
