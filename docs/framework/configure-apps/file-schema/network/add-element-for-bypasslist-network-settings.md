---
title: Элемент <add> для bypasslist (параметры сети)
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
ms.openlocfilehash: 904c8e23f7a09a975a6f3b9322ed6bc4148d9ba4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674672"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="ba9a9-102">\<Добавить > элемент для bypasslist (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="ba9a9-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="ba9a9-103">Добавляет IP-адрес или DNS-имя в список обхода прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
 <span data-ttu-id="ba9a9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ba9a9-104">\<configuration></span></span>  
<span data-ttu-id="ba9a9-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="ba9a9-105">\<system.net></span></span>  
<span data-ttu-id="ba9a9-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="ba9a9-106">\<defaultProxy></span></span>  
<span data-ttu-id="ba9a9-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="ba9a9-107">\<bypasslist></span></span>  
<span data-ttu-id="ba9a9-108">\<add></span><span class="sxs-lookup"><span data-stu-id="ba9a9-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba9a9-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba9a9-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba9a9-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ba9a9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ba9a9-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba9a9-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ba9a9-112">Attributes</span></span>  
  
|<span data-ttu-id="ba9a9-113">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="ba9a9-113">**Attribute**</span></span>|<span data-ttu-id="ba9a9-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ba9a9-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="ba9a9-115">**address**</span><span class="sxs-lookup"><span data-stu-id="ba9a9-115">**address**</span></span>|<span data-ttu-id="ba9a9-116">Регулярное выражение, описывающее IP-адрес или DNS-имя.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba9a9-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ba9a9-117">Child Elements</span></span>  
 <span data-ttu-id="ba9a9-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba9a9-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ba9a9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ba9a9-120">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="ba9a9-120">**Element**</span></span>|<span data-ttu-id="ba9a9-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ba9a9-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ba9a9-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="ba9a9-122">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="ba9a9-123">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba9a9-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="ba9a9-124">Remarks</span></span>  
 <span data-ttu-id="ba9a9-125">`add` Элемент вставляет регулярное выражение, описывающее IP-адреса или имена DNS-серверов в список адресов, которые обходят прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="ba9a9-126">Значение `address` атрибут должен быть регулярное выражение, которое описывает набор IP-адресов или имен узлов.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="ba9a9-127">Будьте внимательны при указании регулярное выражение для этого элемента.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="ba9a9-128">Регулярное выражение «[a-z] +\\.contoso\\.com» совпадений, любого узла в домене contoso.com, но он также соответствует любому узлу в contoso.com.cpandl.com домена.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="ba9a9-129">Чтобы сопоставить только на узле в домене contoso.com, используйте привязку («$»): «[a-z] +\\.contoso\\.com$».</span><span class="sxs-lookup"><span data-stu-id="ba9a9-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="ba9a9-130">Дополнительные сведения о регулярных выражениях см. в разделе. [Регулярные выражения .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ba9a9-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ba9a9-131">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="ba9a9-131">Configuration Files</span></span>  
 <span data-ttu-id="ba9a9-132">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ba9a9-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba9a9-133">Пример</span><span class="sxs-lookup"><span data-stu-id="ba9a9-133">Example</span></span>  
 <span data-ttu-id="ba9a9-134">Следующий пример добавляет два адреса в списке пропускаемых адресов.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="ba9a9-135">Первый обходит прокси-сервер для всех серверов в домене contoso.com. второй обходит прокси-сервер для всех серверов, IP-адрес начинается с 192.168.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ba9a9-136">См. также</span><span class="sxs-lookup"><span data-stu-id="ba9a9-136">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="ba9a9-137">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="ba9a9-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
