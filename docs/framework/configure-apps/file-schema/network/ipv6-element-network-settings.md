---
title: '&lt;IPv6&gt; (сетевые параметры)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: 1ca1bb6a0b1a9c3deab9cb3ba15e9b3b2c29f1f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531893"
---
# <a name="ltipv6gt-element-network-settings"></a><span data-ttu-id="a02df-102">&lt;IPv6&gt; (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="a02df-102">&lt;ipv6&gt; Element (Network Settings)</span></span>
<span data-ttu-id="a02df-103">Включает протокол IP версии 6 (IPv6) ответы от устаревших членов из <xref:System.Net.Dns> класса.</span><span class="sxs-lookup"><span data-stu-id="a02df-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  
  
 <span data-ttu-id="a02df-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a02df-104">\<configuration></span></span>  
<span data-ttu-id="a02df-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="a02df-105">\<system.net></span></span>  
<span data-ttu-id="a02df-106">\<Параметры ></span><span class="sxs-lookup"><span data-stu-id="a02df-106">\<settings></span></span>  
<span data-ttu-id="a02df-107">\<ipv6></span><span class="sxs-lookup"><span data-stu-id="a02df-107">\<ipv6></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a02df-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a02df-108">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a02df-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a02df-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a02df-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a02df-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a02df-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a02df-111">Attributes</span></span>  
  
|<span data-ttu-id="a02df-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="a02df-112">**Attribute**</span></span>|<span data-ttu-id="a02df-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a02df-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="a02df-114">Указывает ли члены <xref:System.Net.Dns> класса вернуть IP версии 6 (IPv6) адреса.</span><span class="sxs-lookup"><span data-stu-id="a02df-114">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="a02df-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="a02df-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a02df-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a02df-116">Child Elements</span></span>  
 <span data-ttu-id="a02df-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a02df-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a02df-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a02df-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a02df-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="a02df-119">**Element**</span></span>|<span data-ttu-id="a02df-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a02df-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a02df-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="a02df-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="a02df-122">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="a02df-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a02df-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="a02df-123">Remarks</span></span>  
 <span data-ttu-id="a02df-124">Этот параметр обеспечивает поддержку IPv6 для устаревших членов <xref:System.Net.Dns> класса: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, и <xref:System.Net.Dns.Resolve%2A>.</span><span class="sxs-lookup"><span data-stu-id="a02df-124">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="a02df-125">Для других членов <xref:System.Net?displayProperty=nameWithType> пространства имен, IPv6-адреса может быть возвращено, если была включена поддержка IPv6 в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="a02df-125">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a02df-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="a02df-126">Configuration Files</span></span>  
 <span data-ttu-id="a02df-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a02df-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a02df-128">Пример</span><span class="sxs-lookup"><span data-stu-id="a02df-128">Example</span></span>  
 <span data-ttu-id="a02df-129">В следующем примере показано, как включить поддержку IPv6 для <xref:System.Net.Dns> класса.</span><span class="sxs-lookup"><span data-stu-id="a02df-129">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a02df-130">См. также</span><span class="sxs-lookup"><span data-stu-id="a02df-130">See also</span></span>
- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a02df-131">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="a02df-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
