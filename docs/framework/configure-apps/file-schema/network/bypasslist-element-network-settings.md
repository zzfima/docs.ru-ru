---
title: Элемент <bypasslist> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: d3d986dae478f49504dae21b9f39574b7887b4d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202226"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="fcb54-102">\<bypasslist > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="fcb54-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="fcb54-103">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="fcb54-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="fcb54-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fcb54-104">\<configuration></span></span>  
<span data-ttu-id="fcb54-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="fcb54-105">\<system.net></span></span>  
<span data-ttu-id="fcb54-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="fcb54-106">\<defaultProxy></span></span>  
<span data-ttu-id="fcb54-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="fcb54-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcb54-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fcb54-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fcb54-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fcb54-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fcb54-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fcb54-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fcb54-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fcb54-111">Attributes</span></span>  
 <span data-ttu-id="fcb54-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fcb54-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fcb54-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fcb54-113">Child Elements</span></span>  
  
|<span data-ttu-id="fcb54-114">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="fcb54-114">**Element**</span></span>|<span data-ttu-id="fcb54-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fcb54-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fcb54-116">add</span><span class="sxs-lookup"><span data-stu-id="fcb54-116">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="fcb54-117">Добавляет IP-адрес или DNS-имя в список обхода прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="fcb54-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="fcb54-118">clear</span><span class="sxs-lookup"><span data-stu-id="fcb54-118">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="fcb54-119">Очищает список вариантов обхода.</span><span class="sxs-lookup"><span data-stu-id="fcb54-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="fcb54-120">remove</span><span class="sxs-lookup"><span data-stu-id="fcb54-120">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="fcb54-121">Удаляет IP-адрес или DNS-имя из списка обхода прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="fcb54-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fcb54-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fcb54-122">Parent Elements</span></span>  
  
|<span data-ttu-id="fcb54-123">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="fcb54-123">**Element**</span></span>|<span data-ttu-id="fcb54-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fcb54-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fcb54-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="fcb54-125">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="fcb54-126">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="fcb54-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcb54-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="fcb54-127">Remarks</span></span>  
 <span data-ttu-id="fcb54-128">В списке пропускаемых адресов содержит регулярных выражений, описывающих URI, <xref:System.Net.WebRequest> экземпляры доступ напрямую вместо того, через прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="fcb54-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="fcb54-129">Будьте внимательны при указании регулярное выражение для этого элемента.</span><span class="sxs-lookup"><span data-stu-id="fcb54-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="fcb54-130">Регулярное выражение «[a-z] +\\.contoso\\.com» совпадений, любого узла в домене contoso.com, но он также соответствует любому узлу в contoso.com.cpandl.com домена.</span><span class="sxs-lookup"><span data-stu-id="fcb54-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="fcb54-131">Чтобы сопоставить только на узле в домене contoso.com, используйте привязку («$»): «[a-z] +\\.contoso\\.com$».</span><span class="sxs-lookup"><span data-stu-id="fcb54-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="fcb54-132">Дополнительные сведения о регулярных выражениях см. в разделе. [Регулярные выражения .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="fcb54-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="fcb54-133">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="fcb54-133">Configuration Files</span></span>  
 <span data-ttu-id="fcb54-134">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="fcb54-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcb54-135">Пример</span><span class="sxs-lookup"><span data-stu-id="fcb54-135">Example</span></span>  
 <span data-ttu-id="fcb54-136">Следующий пример добавляет два адреса в списке пропускаемых адресов.</span><span class="sxs-lookup"><span data-stu-id="fcb54-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="fcb54-137">Первый обходит прокси-сервер для всех серверов в домене contoso.com. второй обходит прокси-сервер для всех серверов, IP-адреса начинается с 192.168.</span><span class="sxs-lookup"><span data-stu-id="fcb54-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fcb54-138">См. также</span><span class="sxs-lookup"><span data-stu-id="fcb54-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="fcb54-139">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="fcb54-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
