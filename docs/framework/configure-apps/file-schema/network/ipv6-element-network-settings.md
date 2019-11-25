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
ms.openlocfilehash: c16949171d082bd02abb0a02db83c2e71c2f17df
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088134"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="c4537-102">Элемент \<ipv6> (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="c4537-102">\<ipv6> Element (Network Settings)</span></span>
<span data-ttu-id="c4537-103">Включает отклики протокола IP версии 6 (IPv6) от устаревших членов класса <xref:System.Net.Dns>.</span><span class="sxs-lookup"><span data-stu-id="c4537-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  

<span data-ttu-id="c4537-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c4537-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c4537-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c4537-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="c4537-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](settings-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="c4537-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>\
<span data-ttu-id="c4537-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**ipv6 >**</span><span class="sxs-lookup"><span data-stu-id="c4537-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ipv6>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c4537-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4537-108">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4537-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c4537-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c4537-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c4537-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4537-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c4537-111">Attributes</span></span>  
  
|<span data-ttu-id="c4537-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="c4537-112">**Attribute**</span></span>|<span data-ttu-id="c4537-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c4537-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="c4537-114">Указывает, возвращают ли члены класса <xref:System.Net.Dns> IPv6-адреса.</span><span class="sxs-lookup"><span data-stu-id="c4537-114">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="c4537-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="c4537-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4537-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c4537-116">Child Elements</span></span>  
 <span data-ttu-id="c4537-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c4537-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4537-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c4537-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c4537-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="c4537-119">**Element**</span></span>|<span data-ttu-id="c4537-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c4537-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c4537-121">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4537-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="c4537-122">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="c4537-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4537-123">Заметки</span><span class="sxs-lookup"><span data-stu-id="c4537-123">Remarks</span></span>  
 <span data-ttu-id="c4537-124">Этот параметр включает поддержку IPv6 для устаревших членов класса <xref:System.Net.Dns>: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>и <xref:System.Net.Dns.Resolve%2A>.</span><span class="sxs-lookup"><span data-stu-id="c4537-124">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="c4537-125">Для других членов пространства имен <xref:System.Net?displayProperty=nameWithType> IPv6-адреса могут возвращаться, если в операционной системе включен протокол IPv6.</span><span class="sxs-lookup"><span data-stu-id="c4537-125">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c4537-126">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="c4537-126">Configuration Files</span></span>  
 <span data-ttu-id="c4537-127">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c4537-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4537-128">Пример</span><span class="sxs-lookup"><span data-stu-id="c4537-128">Example</span></span>  
 <span data-ttu-id="c4537-129">В следующем примере показано, как включить поддержку IPv6 для класса <xref:System.Net.Dns>.</span><span class="sxs-lookup"><span data-stu-id="c4537-129">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4537-130">См. также</span><span class="sxs-lookup"><span data-stu-id="c4537-130">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c4537-131">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="c4537-131">Network Settings Schema</span></span>](index.md)
