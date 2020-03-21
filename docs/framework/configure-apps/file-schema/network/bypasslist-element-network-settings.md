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
ms.openlocfilehash: 97e69a4978aa4700d13a994619a65312cf70aeaa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154950"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="6e13b-102">\<шунтиста> элемент (Настройки сети)</span><span class="sxs-lookup"><span data-stu-id="6e13b-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="6e13b-103">Предоставляет набор регулярных выражений, описывающие адреса, которые не используют прокси.</span><span class="sxs-lookup"><span data-stu-id="6e13b-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  

<span data-ttu-id="6e13b-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6e13b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6e13b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6e13b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="6e13b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<по умолчаниюПрокси>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6e13b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="6e13b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<обвахние>**</span><span class="sxs-lookup"><span data-stu-id="6e13b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6e13b-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e13b-108">Syntax</span></span>  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e13b-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6e13b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6e13b-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6e13b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e13b-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6e13b-111">Attributes</span></span>  
 <span data-ttu-id="6e13b-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="6e13b-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6e13b-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6e13b-113">Child Elements</span></span>  
  
|<span data-ttu-id="6e13b-114">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="6e13b-114">**Element**</span></span>|<span data-ttu-id="6e13b-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6e13b-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6e13b-116">добавление</span><span class="sxs-lookup"><span data-stu-id="6e13b-116">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="6e13b-117">Добавляет IP-адрес или имя DNS в список обхода прокси.</span><span class="sxs-lookup"><span data-stu-id="6e13b-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="6e13b-118">Ясно</span><span class="sxs-lookup"><span data-stu-id="6e13b-118">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="6e13b-119">Очищает список обхода.</span><span class="sxs-lookup"><span data-stu-id="6e13b-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="6e13b-120">удаление</span><span class="sxs-lookup"><span data-stu-id="6e13b-120">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="6e13b-121">Удаляет IP-адрес или имя DNS из списка обхода прокси.</span><span class="sxs-lookup"><span data-stu-id="6e13b-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6e13b-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6e13b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="6e13b-123">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="6e13b-123">**Element**</span></span>|<span data-ttu-id="6e13b-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6e13b-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6e13b-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="6e13b-125">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="6e13b-126">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="6e13b-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e13b-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="6e13b-127">Remarks</span></span>  
 <span data-ttu-id="6e13b-128">Список обхода содержит регулярные выражения, <xref:System.Net.WebRequest> описывающие URIs, доступ к которым происходит непосредственно, а не через прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="6e13b-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="6e13b-129">При указании регулярного выражения для этого элемента следует соблюдать осторожность.</span><span class="sxs-lookup"><span data-stu-id="6e13b-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="6e13b-130">Регулярное выражение «a-z»\\.contoso\\.com соответствует любому хозяину в домене contoso.com, но также соответствует любому хозяину в домене contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="6e13b-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="6e13b-131">Чтобы соответствовать только хостелу в домене contoso.com, используйте якорь («$»): «А-з.з\\.contoso\\.com$».</span><span class="sxs-lookup"><span data-stu-id="6e13b-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="6e13b-132">Для получения дополнительной информации о регулярных выражениях см. [.NET Рамки Регулярные выражения](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="6e13b-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="6e13b-133">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="6e13b-133">Configuration Files</span></span>  
 <span data-ttu-id="6e13b-134">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="6e13b-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e13b-135">Пример</span><span class="sxs-lookup"><span data-stu-id="6e13b-135">Example</span></span>  
 <span data-ttu-id="6e13b-136">Следующий пример добавляет два адреса в список обхода.</span><span class="sxs-lookup"><span data-stu-id="6e13b-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="6e13b-137">Первый обходит прокси для всех серверов в домене contoso.com; второй обходит прокси для всех серверов, IP-адреса которых начинаются с 192.168.</span><span class="sxs-lookup"><span data-stu-id="6e13b-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6e13b-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6e13b-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="6e13b-139">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="6e13b-139">Network Settings Schema</span></span>](index.md)
