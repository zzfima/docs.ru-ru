---
title: Элемент <ipv6> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: d89c2e2c6943aca38f8a71092ba3121447a77574
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664101"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="40df4-102">Элемент \<ipv6> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="40df4-102">\<ipv6> Element (Network Settings)</span></span>
<span data-ttu-id="40df4-103">Включает отклики протокола IP версии 6 (IPv6) от устаревших <xref:System.Net.Dns> членов класса.</span><span class="sxs-lookup"><span data-stu-id="40df4-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  
  
 <span data-ttu-id="40df4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="40df4-104">\<configuration></span></span>  
<span data-ttu-id="40df4-105">\<> System. NET</span><span class="sxs-lookup"><span data-stu-id="40df4-105">\<system.net></span></span>  
<span data-ttu-id="40df4-106">\<> параметров</span><span class="sxs-lookup"><span data-stu-id="40df4-106">\<settings></span></span>  
<span data-ttu-id="40df4-107">\<> IPv6</span><span class="sxs-lookup"><span data-stu-id="40df4-107">\<ipv6></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40df4-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40df4-108">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40df4-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="40df4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="40df4-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="40df4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40df4-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="40df4-111">Attributes</span></span>  
  
|<span data-ttu-id="40df4-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="40df4-112">**Attribute**</span></span>|<span data-ttu-id="40df4-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="40df4-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="40df4-114">Указывает, <xref:System.Net.Dns> возвращают ли члены класса IPv6-адреса.</span><span class="sxs-lookup"><span data-stu-id="40df4-114">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="40df4-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="40df4-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40df4-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="40df4-116">Child Elements</span></span>  
 <span data-ttu-id="40df4-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="40df4-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40df4-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="40df4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="40df4-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="40df4-119">**Element**</span></span>|<span data-ttu-id="40df4-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="40df4-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="40df4-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="40df4-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="40df4-122">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="40df4-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40df4-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="40df4-123">Remarks</span></span>  
 <span data-ttu-id="40df4-124">Этот параметр включает <xref:System.Net.Dns> поддержку IPv6 для устаревших членов класса: <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Net.Dns.BeginResolve%2A> <xref:System.Net.Dns.EndGetHostByName%2A> <xref:System.Net.Dns.GetHostByAddress%2A> <xref:System.Net.Dns.EndResolve%2A> <xref:System.Net.Dns.Resolve%2A>,,, ,,и.<xref:System.Net.Dns.GetHostByName%2A></span><span class="sxs-lookup"><span data-stu-id="40df4-124">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="40df4-125">Для других членов <xref:System.Net?displayProperty=nameWithType> пространства имен IPv6-адреса могут возвращаться, если в операционной системе включен протокол IPv6.</span><span class="sxs-lookup"><span data-stu-id="40df4-125">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="40df4-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="40df4-126">Configuration Files</span></span>  
 <span data-ttu-id="40df4-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="40df4-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="40df4-128">Пример</span><span class="sxs-lookup"><span data-stu-id="40df4-128">Example</span></span>  
 <span data-ttu-id="40df4-129">В следующем примере показано, как включить поддержку IPv6 для <xref:System.Net.Dns> класса.</span><span class="sxs-lookup"><span data-stu-id="40df4-129">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="40df4-130">См. также</span><span class="sxs-lookup"><span data-stu-id="40df4-130">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="40df4-131">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="40df4-131">Network Settings Schema</span></span>](index.md)
