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
ms.openlocfilehash: 1db0ba3b0a213de1175e6e0cee347753d2a413b7
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699614"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="67233-102">\<добавить элемент > для бипасслист (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="67233-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="67233-103">Добавление в список обхода прокси IP-адреса или DNS-имени.</span><span class="sxs-lookup"><span data-stu-id="67233-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
[<span data-ttu-id="67233-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="67233-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="67233-105">&nbsp;&nbsp;[ **\<System. NET >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="67233-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="67233-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="67233-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="67233-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<бипасслист >** ](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="67233-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>  
<span data-ttu-id="67233-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<добавить >**</span><span class="sxs-lookup"><span data-stu-id="67233-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67233-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67233-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67233-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="67233-110">Attributes and Elements</span></span>  
 <span data-ttu-id="67233-111">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="67233-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67233-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="67233-112">Attributes</span></span>  
  
|<span data-ttu-id="67233-113">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="67233-113">**Attribute**</span></span>|<span data-ttu-id="67233-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="67233-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="67233-115">**address**</span><span class="sxs-lookup"><span data-stu-id="67233-115">**address**</span></span>|<span data-ttu-id="67233-116">Регулярное выражение, описывающее IP-адрес или DNS-имя.</span><span class="sxs-lookup"><span data-stu-id="67233-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67233-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="67233-117">Child Elements</span></span>  
 <span data-ttu-id="67233-118">Нет</span><span class="sxs-lookup"><span data-stu-id="67233-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="67233-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="67233-119">Parent Elements</span></span>  
  
|<span data-ttu-id="67233-120">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="67233-120">**Element**</span></span>|<span data-ttu-id="67233-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="67233-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="67233-122">бипасслист</span><span class="sxs-lookup"><span data-stu-id="67233-122">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="67233-123">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="67233-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67233-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="67233-124">Remarks</span></span>  
 <span data-ttu-id="67233-125">Элемент `add` вставляет регулярные выражения, описывающие IP-адреса или имена DNS-серверов, в список адресов, которые обходят прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="67233-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="67233-126">Значение атрибута `address` должно быть регулярным выражением, описывающим набор IP-адресов или имен узлов.</span><span class="sxs-lookup"><span data-stu-id="67233-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="67233-127">При указании регулярного выражения для этого элемента следует соблюдать осторожность.</span><span class="sxs-lookup"><span data-stu-id="67233-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="67233-128">Регулярное выражение "[a-z] +\\. contoso\\. com" соответствует любому узлу в домене contoso.com, но также соответствует любому узлу в домене contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="67233-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="67233-129">Чтобы сопоставить только узел в домене contoso.com, используйте привязку ("$"): "[a-z] +\\. contoso\\. com $".</span><span class="sxs-lookup"><span data-stu-id="67233-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="67233-130">Дополнительные сведения о регулярных выражениях см. в разделе. [.NET Framework регулярных выражений](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="67233-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="67233-131">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="67233-131">Configuration Files</span></span>  
 <span data-ttu-id="67233-132">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="67233-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="67233-133">Пример</span><span class="sxs-lookup"><span data-stu-id="67233-133">Example</span></span>  
 <span data-ttu-id="67233-134">В следующем примере в список обхода добавляется два адреса.</span><span class="sxs-lookup"><span data-stu-id="67233-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="67233-135">Первый обход прокси-сервера для всех серверов в домене contoso.com; во втором пропускается прокси-сервер для всех серверов, IP-адрес которых начинается с 192,168.</span><span class="sxs-lookup"><span data-stu-id="67233-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="67233-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="67233-136">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="67233-137">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="67233-137">Network Settings Schema</span></span>](index.md)
