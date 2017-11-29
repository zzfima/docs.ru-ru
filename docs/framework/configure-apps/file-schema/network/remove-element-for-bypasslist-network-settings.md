---
title: "&lt;Удалить&gt; элемент для bypasslist (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove elemment, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
caps.latest.revision: "16"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a87632ec9725aa24d085ca6c1bf1e54545b324fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltremovegt-element-for-bypasslist-network-settings"></a><span data-ttu-id="a2671-102">&lt;Удалить&gt; элемент для bypasslist (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="a2671-102">&lt;remove&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="a2671-103">Удаляет IP-адрес или DNS-имя из списка обхода прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="a2671-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>  
  
 <span data-ttu-id="a2671-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a2671-104">\<configuration></span></span>  
<span data-ttu-id="a2671-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="a2671-105">\<system.net></span></span>  
<span data-ttu-id="a2671-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="a2671-106">\<defaultProxy></span></span>  
<span data-ttu-id="a2671-107">\<bypasslist ></span><span class="sxs-lookup"><span data-stu-id="a2671-107">\<bypasslist></span></span>  
<span data-ttu-id="a2671-108">\<Удалите ></span><span class="sxs-lookup"><span data-stu-id="a2671-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2671-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2671-109">Syntax</span></span>  
  
```xml  
<remove   
  address="regular expression"   
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2671-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a2671-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a2671-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a2671-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2671-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a2671-112">Attributes</span></span>  
  
|<span data-ttu-id="a2671-113">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="a2671-113">**Attribute**</span></span>|<span data-ttu-id="a2671-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a2671-114">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="a2671-115">Регулярное выражение, описывающее IP-адрес или DNS-имя.</span><span class="sxs-lookup"><span data-stu-id="a2671-115">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2671-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a2671-116">Child Elements</span></span>  
 <span data-ttu-id="a2671-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a2671-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a2671-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a2671-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a2671-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="a2671-119">**Element**</span></span>|<span data-ttu-id="a2671-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a2671-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a2671-121">bypasslist</span><span class="sxs-lookup"><span data-stu-id="a2671-121">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="a2671-122">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="a2671-122">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2671-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="a2671-123">Remarks</span></span>  
 <span data-ttu-id="a2671-124">`remove` Элемент удаляет регулярное выражение, описывающее IP-адреса или имена DNS-серверов в списке адресов, которые обходят прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="a2671-124">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="a2671-125">Эти адреса были заданы ранее в файле конфигурации или на более высоком уровне в иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a2671-125">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="a2671-126">Значение для `address` атрибут должен иметь регулярное выражение, которое описывает набор IP-адресов или имен узлов.</span><span class="sxs-lookup"><span data-stu-id="a2671-126">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="a2671-127">Дополнительные сведения о регулярных выражениях см. в разделе. [Регулярные выражения .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a2671-127">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a2671-128">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="a2671-128">Configuration Files</span></span>  
 <span data-ttu-id="a2671-129">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a2671-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2671-130">Пример</span><span class="sxs-lookup"><span data-stu-id="a2671-130">Example</span></span>  
 <span data-ttu-id="a2671-131">Следующий пример удаляет все предыдущие определения для домена adventure-works.com и затем добавляет в список пропускаемых домена contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a2671-131">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <remove address="[a-z]+\.adventure-works\.com$" />  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2671-132">См. также</span><span class="sxs-lookup"><span data-stu-id="a2671-132">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="a2671-133">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="a2671-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
