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
ms.openlocfilehash: 10d2a025096579c6bed64f82cc955deb0542717c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664208"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="4c9a2-102">\<Элемент > бипасслист (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="4c9a2-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="4c9a2-103">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="4c9a2-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="4c9a2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4c9a2-104">\<configuration></span></span>  
<span data-ttu-id="4c9a2-105">\<> System. NET</span><span class="sxs-lookup"><span data-stu-id="4c9a2-105">\<system.net></span></span>  
<span data-ttu-id="4c9a2-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="4c9a2-106">\<defaultProxy></span></span>  
<span data-ttu-id="4c9a2-107">\<бипасслист ></span><span class="sxs-lookup"><span data-stu-id="4c9a2-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c9a2-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c9a2-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c9a2-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4c9a2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4c9a2-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4c9a2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c9a2-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4c9a2-111">Attributes</span></span>  
 <span data-ttu-id="4c9a2-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="4c9a2-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4c9a2-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4c9a2-113">Child Elements</span></span>  
  
|<span data-ttu-id="4c9a2-114">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="4c9a2-114">**Element**</span></span>|<span data-ttu-id="4c9a2-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4c9a2-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4c9a2-116">add</span><span class="sxs-lookup"><span data-stu-id="4c9a2-116">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="4c9a2-117">Добавление в список обхода прокси IP-адреса или DNS-имени.</span><span class="sxs-lookup"><span data-stu-id="4c9a2-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="4c9a2-118">clear</span><span class="sxs-lookup"><span data-stu-id="4c9a2-118">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="4c9a2-119">Очищает список обхода.</span><span class="sxs-lookup"><span data-stu-id="4c9a2-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="4c9a2-120">remove</span><span class="sxs-lookup"><span data-stu-id="4c9a2-120">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="4c9a2-121">Удаляет IP-адрес или DNS-имя из списка обхода прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="4c9a2-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4c9a2-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4c9a2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4c9a2-123">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="4c9a2-123">**Element**</span></span>|<span data-ttu-id="4c9a2-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4c9a2-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4c9a2-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="4c9a2-125">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="4c9a2-126">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="4c9a2-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c9a2-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="4c9a2-127">Remarks</span></span>  
 <span data-ttu-id="4c9a2-128">Список обхода содержит регулярные выражения, описывающие URI, <xref:System.Net.WebRequest> которые обращаются к экземплярам напрямую, а не через прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="4c9a2-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="4c9a2-129">При указании регулярного выражения для этого элемента следует соблюдать осторожность.</span><span class="sxs-lookup"><span data-stu-id="4c9a2-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="4c9a2-130">Регулярное выражение "[a-z] +\\. contoso\\. com" соответствует любому узлу в домене contoso.com, но также соответствует любому узлу в домене contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="4c9a2-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="4c9a2-131">Чтобы сопоставить только узел в домене contoso.com, используйте привязку ("$"): "[a-z] +\\. contoso\\. com $".</span><span class="sxs-lookup"><span data-stu-id="4c9a2-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="4c9a2-132">Дополнительные сведения о регулярных выражениях см. в разделе. [.NET Framework регулярных выражений](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4c9a2-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4c9a2-133">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="4c9a2-133">Configuration Files</span></span>  
 <span data-ttu-id="4c9a2-134">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4c9a2-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c9a2-135">Пример</span><span class="sxs-lookup"><span data-stu-id="4c9a2-135">Example</span></span>  
 <span data-ttu-id="4c9a2-136">В следующем примере в список обхода добавляется два адреса.</span><span class="sxs-lookup"><span data-stu-id="4c9a2-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="4c9a2-137">Первый обход прокси-сервера для всех серверов в домене contoso.com; во втором случае прокси-сервер обходится для всех серверов, IP-адреса которых начинаются с 192,168.</span><span class="sxs-lookup"><span data-stu-id="4c9a2-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4c9a2-138">См. также</span><span class="sxs-lookup"><span data-stu-id="4c9a2-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="4c9a2-139">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="4c9a2-139">Network Settings Schema</span></span>](index.md)
