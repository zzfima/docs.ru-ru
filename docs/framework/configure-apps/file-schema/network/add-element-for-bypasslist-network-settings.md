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
ms.openlocfilehash: 652b8738a201aaa98fa2c5c435fee1a6da91673b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155081"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="30882-102">\<добавить элемент> для обвисать (Настройки сети)</span><span class="sxs-lookup"><span data-stu-id="30882-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="30882-103">Добавляет IP-адрес или имя DNS в список обхода прокси.</span><span class="sxs-lookup"><span data-stu-id="30882-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
[<span data-ttu-id="30882-104">**\<конфигурация>**</span><span class="sxs-lookup"><span data-stu-id="30882-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="30882-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="30882-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="30882-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<по умолчаниюПрокси>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="30882-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="30882-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<обвахние>**](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="30882-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>  
<span data-ttu-id="30882-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<добавить>**</span><span class="sxs-lookup"><span data-stu-id="30882-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30882-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30882-109">Syntax</span></span>  
  
```xml  
<add
  address="regular expression"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30882-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="30882-110">Attributes and Elements</span></span>  
 <span data-ttu-id="30882-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="30882-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30882-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="30882-112">Attributes</span></span>  
  
|<span data-ttu-id="30882-113">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="30882-113">**Attribute**</span></span>|<span data-ttu-id="30882-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="30882-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="30882-115">**address**</span><span class="sxs-lookup"><span data-stu-id="30882-115">**address**</span></span>|<span data-ttu-id="30882-116">Регулярное выражение, описывающее IP-адрес или имя DNS.</span><span class="sxs-lookup"><span data-stu-id="30882-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30882-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="30882-117">Child Elements</span></span>  
 <span data-ttu-id="30882-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="30882-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="30882-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="30882-119">Parent Elements</span></span>  
  
|<span data-ttu-id="30882-120">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="30882-120">**Element**</span></span>|<span data-ttu-id="30882-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="30882-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="30882-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="30882-122">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="30882-123">Предоставляет набор регулярных выражений, описывающие адреса, которые не используют прокси.</span><span class="sxs-lookup"><span data-stu-id="30882-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30882-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="30882-124">Remarks</span></span>  
 <span data-ttu-id="30882-125">Элемент `add` вставляет регулярные выражения, описывающие IP-адреса или имена серверов DNS, в список адресов, которые обходят прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="30882-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="30882-126">Значение `address` атрибута должно быть регулярным выражением, описывая набор IP-адресов или имен узла.</span><span class="sxs-lookup"><span data-stu-id="30882-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="30882-127">При указании регулярного выражения для этого элемента следует соблюдать осторожность.</span><span class="sxs-lookup"><span data-stu-id="30882-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="30882-128">Регулярное выражение «a-z»\\.contoso\\.com соответствует любому хозяину в домене contoso.com, но также соответствует любому хозяину в домене contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="30882-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="30882-129">Чтобы соответствовать только хостелу в домене contoso.com, используйте якорь («$»): «А-з.з\\.contoso\\.com$».</span><span class="sxs-lookup"><span data-stu-id="30882-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="30882-130">Для получения дополнительной информации о регулярных выражениях см. [.NET Рамки Регулярные выражения](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="30882-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="30882-131">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="30882-131">Configuration Files</span></span>  
 <span data-ttu-id="30882-132">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="30882-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="30882-133">Пример</span><span class="sxs-lookup"><span data-stu-id="30882-133">Example</span></span>  
 <span data-ttu-id="30882-134">Следующий пример добавляет два адреса в список обхода.</span><span class="sxs-lookup"><span data-stu-id="30882-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="30882-135">Первый обходит прокси для всех серверов в домене contoso.com; второй обходит прокси для всех серверов, чей IP-адрес начинается с 192.168.</span><span class="sxs-lookup"><span data-stu-id="30882-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="30882-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="30882-136">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="30882-137">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="30882-137">Network Settings Schema</span></span>](index.md)
