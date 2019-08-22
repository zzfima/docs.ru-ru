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
ms.openlocfilehash: dd8790efa14018817c9e51e688b17c22d31d482f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659573"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="8aa83-102">\<Добавление элемента > для бипасслист (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="8aa83-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="8aa83-103">Добавление в список обхода прокси IP-адреса или DNS-имени.</span><span class="sxs-lookup"><span data-stu-id="8aa83-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
 <span data-ttu-id="8aa83-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8aa83-104">\<configuration></span></span>  
<span data-ttu-id="8aa83-105">\<> System. NET</span><span class="sxs-lookup"><span data-stu-id="8aa83-105">\<system.net></span></span>  
<span data-ttu-id="8aa83-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="8aa83-106">\<defaultProxy></span></span>  
<span data-ttu-id="8aa83-107">\<бипасслист ></span><span class="sxs-lookup"><span data-stu-id="8aa83-107">\<bypasslist></span></span>  
<span data-ttu-id="8aa83-108">\<add></span><span class="sxs-lookup"><span data-stu-id="8aa83-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aa83-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8aa83-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8aa83-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8aa83-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8aa83-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8aa83-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8aa83-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8aa83-112">Attributes</span></span>  
  
|<span data-ttu-id="8aa83-113">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="8aa83-113">**Attribute**</span></span>|<span data-ttu-id="8aa83-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8aa83-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="8aa83-115">**address**</span><span class="sxs-lookup"><span data-stu-id="8aa83-115">**address**</span></span>|<span data-ttu-id="8aa83-116">Регулярное выражение, описывающее IP-адрес или DNS-имя.</span><span class="sxs-lookup"><span data-stu-id="8aa83-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8aa83-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8aa83-117">Child Elements</span></span>  
 <span data-ttu-id="8aa83-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="8aa83-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8aa83-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8aa83-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8aa83-120">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="8aa83-120">**Element**</span></span>|<span data-ttu-id="8aa83-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8aa83-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8aa83-122">бипасслист</span><span class="sxs-lookup"><span data-stu-id="8aa83-122">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="8aa83-123">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="8aa83-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8aa83-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="8aa83-124">Remarks</span></span>  
 <span data-ttu-id="8aa83-125">`add` Элемент вставляет регулярные выражения, описывающие IP-адреса или имена DNS-серверов, в список адресов, которые обходят прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="8aa83-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="8aa83-126">Значение `address` атрибута должно быть регулярным выражением, описывающим набор IP-адресов или имен узлов.</span><span class="sxs-lookup"><span data-stu-id="8aa83-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="8aa83-127">При указании регулярного выражения для этого элемента следует соблюдать осторожность.</span><span class="sxs-lookup"><span data-stu-id="8aa83-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="8aa83-128">Регулярное выражение "[a-z] +\\. contoso\\. com" соответствует любому узлу в домене contoso.com, но также соответствует любому узлу в домене contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="8aa83-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="8aa83-129">Чтобы сопоставить только узел в домене contoso.com, используйте привязку ("$"): "[a-z] +\\. contoso\\. com $".</span><span class="sxs-lookup"><span data-stu-id="8aa83-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="8aa83-130">Дополнительные сведения о регулярных выражениях см. в разделе. [.NET Framework регулярных выражений](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="8aa83-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8aa83-131">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="8aa83-131">Configuration Files</span></span>  
 <span data-ttu-id="8aa83-132">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="8aa83-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8aa83-133">Пример</span><span class="sxs-lookup"><span data-stu-id="8aa83-133">Example</span></span>  
 <span data-ttu-id="8aa83-134">В следующем примере в список обхода добавляется два адреса.</span><span class="sxs-lookup"><span data-stu-id="8aa83-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="8aa83-135">Первый обход прокси-сервера для всех серверов в домене contoso.com; во втором пропускается прокси-сервер для всех серверов, IP-адрес которых начинается с 192,168.</span><span class="sxs-lookup"><span data-stu-id="8aa83-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8aa83-136">См. также</span><span class="sxs-lookup"><span data-stu-id="8aa83-136">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="8aa83-137">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="8aa83-137">Network Settings Schema</span></span>](index.md)
