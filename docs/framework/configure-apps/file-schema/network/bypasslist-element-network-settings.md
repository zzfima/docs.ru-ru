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
ms.openlocfilehash: bd746f07b4c4eb08bf34b01d555b5799d9af0cf3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927479"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="2f16d-102">\<Элемент > бипасслист (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="2f16d-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="2f16d-103">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="2f16d-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="2f16d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2f16d-104">\<configuration></span></span>  
<span data-ttu-id="2f16d-105">\<> System. NET</span><span class="sxs-lookup"><span data-stu-id="2f16d-105">\<system.net></span></span>  
<span data-ttu-id="2f16d-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="2f16d-106">\<defaultProxy></span></span>  
<span data-ttu-id="2f16d-107">\<бипасслист ></span><span class="sxs-lookup"><span data-stu-id="2f16d-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f16d-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f16d-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f16d-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2f16d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2f16d-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2f16d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f16d-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2f16d-111">Attributes</span></span>  
 <span data-ttu-id="2f16d-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="2f16d-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2f16d-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2f16d-113">Child Elements</span></span>  
  
|<span data-ttu-id="2f16d-114">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="2f16d-114">**Element**</span></span>|<span data-ttu-id="2f16d-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2f16d-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2f16d-116">add</span><span class="sxs-lookup"><span data-stu-id="2f16d-116">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="2f16d-117">Добавление в список обхода прокси IP-адреса или DNS-имени.</span><span class="sxs-lookup"><span data-stu-id="2f16d-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="2f16d-118">clear</span><span class="sxs-lookup"><span data-stu-id="2f16d-118">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="2f16d-119">Очищает список обхода.</span><span class="sxs-lookup"><span data-stu-id="2f16d-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="2f16d-120">remove</span><span class="sxs-lookup"><span data-stu-id="2f16d-120">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="2f16d-121">Удаляет IP-адрес или DNS-имя из списка обхода прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="2f16d-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2f16d-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2f16d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2f16d-123">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="2f16d-123">**Element**</span></span>|<span data-ttu-id="2f16d-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2f16d-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2f16d-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="2f16d-125">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="2f16d-126">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="2f16d-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f16d-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="2f16d-127">Remarks</span></span>  
 <span data-ttu-id="2f16d-128">Список обхода содержит регулярные выражения, описывающие URI, <xref:System.Net.WebRequest> которые обращаются к экземплярам напрямую, а не через прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="2f16d-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="2f16d-129">При указании регулярного выражения для этого элемента следует соблюдать осторожность.</span><span class="sxs-lookup"><span data-stu-id="2f16d-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="2f16d-130">Регулярное выражение "[a-z] +\\. contoso\\. com" соответствует любому узлу в домене contoso.com, но также соответствует любому узлу в домене contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="2f16d-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="2f16d-131">Чтобы сопоставить только узел в домене contoso.com, используйте привязку ("$"): "[a-z] +\\. contoso\\. com $".</span><span class="sxs-lookup"><span data-stu-id="2f16d-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="2f16d-132">Дополнительные сведения о регулярных выражениях см. в разделе. [.NET Framework регулярных выражений](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2f16d-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2f16d-133">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="2f16d-133">Configuration Files</span></span>  
 <span data-ttu-id="2f16d-134">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="2f16d-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f16d-135">Пример</span><span class="sxs-lookup"><span data-stu-id="2f16d-135">Example</span></span>  
 <span data-ttu-id="2f16d-136">В следующем примере в список обхода добавляется два адреса.</span><span class="sxs-lookup"><span data-stu-id="2f16d-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="2f16d-137">Первый обход прокси-сервера для всех серверов в домене contoso.com; во втором случае прокси-сервер обходится для всех серверов, IP-адреса которых начинаются с 192,168.</span><span class="sxs-lookup"><span data-stu-id="2f16d-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2f16d-138">См. также</span><span class="sxs-lookup"><span data-stu-id="2f16d-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="2f16d-139">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="2f16d-139">Network Settings Schema</span></span>](index.md)
