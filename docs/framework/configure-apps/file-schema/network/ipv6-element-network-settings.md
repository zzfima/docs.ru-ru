---
title: "&lt;IPv6&gt; элемент (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
caps.latest.revision: "19"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: dd5366b4110d9ec2290e2669919575e07e8ec98a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltipv6gt-element-network-settings"></a><span data-ttu-id="b0b20-102">&lt;IPv6&gt; элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="b0b20-102">&lt;ipv6&gt; Element (Network Settings)</span></span>
<span data-ttu-id="b0b20-103">Включает протокол IP версии 6 (IPv6) ответов от устаревшие члены <xref:System.Net.Dns> класса.</span><span class="sxs-lookup"><span data-stu-id="b0b20-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  
  
 <span data-ttu-id="b0b20-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b0b20-104">\<configuration></span></span>  
<span data-ttu-id="b0b20-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="b0b20-105">\<system.net></span></span>  
<span data-ttu-id="b0b20-106">\<Параметры ></span><span class="sxs-lookup"><span data-stu-id="b0b20-106">\<settings></span></span>  
<span data-ttu-id="b0b20-107">\<IPv6 ></span><span class="sxs-lookup"><span data-stu-id="b0b20-107">\<ipv6></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0b20-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0b20-108">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0b20-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b0b20-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b0b20-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b0b20-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0b20-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b0b20-111">Attributes</span></span>  
  
|<span data-ttu-id="b0b20-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="b0b20-112">**Attribute**</span></span>|<span data-ttu-id="b0b20-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b0b20-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="b0b20-114">Указывает ли члены <xref:System.Net.Dns> класс возвращать протокола IP версии 6 (IPv6) адресов.</span><span class="sxs-lookup"><span data-stu-id="b0b20-114">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="b0b20-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="b0b20-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0b20-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b0b20-116">Child Elements</span></span>  
 <span data-ttu-id="b0b20-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b0b20-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0b20-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b0b20-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b0b20-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="b0b20-119">**Element**</span></span>|<span data-ttu-id="b0b20-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b0b20-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b0b20-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="b0b20-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="b0b20-122">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="b0b20-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0b20-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="b0b20-123">Remarks</span></span>  
 <span data-ttu-id="b0b20-124">Этот параметр обеспечивает поддержку IPv6 для устаревших членов <xref:System.Net.Dns> класса: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, и <xref:System.Net.Dns.Resolve%2A>.</span><span class="sxs-lookup"><span data-stu-id="b0b20-124">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="b0b20-125">Для других членов <xref:System.Net?displayProperty=nameWithType> пространства имен, IPv6-адресов может быть возвращено, если IPv6 включен в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="b0b20-125">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b0b20-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="b0b20-126">Configuration Files</span></span>  
 <span data-ttu-id="b0b20-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b0b20-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0b20-128">Пример</span><span class="sxs-lookup"><span data-stu-id="b0b20-128">Example</span></span>  
 <span data-ttu-id="b0b20-129">Приведенный ниже показано, как включить поддержку IPv6 <xref:System.Net.Dns> класса.</span><span class="sxs-lookup"><span data-stu-id="b0b20-129">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0b20-130">См. также</span><span class="sxs-lookup"><span data-stu-id="b0b20-130">See Also</span></span>  
 <xref:System.Net?displayProperty=nameWithType>  
 <xref:System.Net.Dns?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="b0b20-131">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="b0b20-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
