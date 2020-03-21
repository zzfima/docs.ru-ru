---
title: Элемент <clear> для bypasslist (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, bypasslist
- <clear> element, bypasslist
- <bypasslist>, clear element
- bypasslist, clear element
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
ms.openlocfilehash: c25477c2c99be66b34b07e1f7e50115bfa8d14e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154937"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="e7467-102">\<ясно> элемент для обвисаем (Настройки сети)</span><span class="sxs-lookup"><span data-stu-id="e7467-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="e7467-103">Очищает список обхода прокси.</span><span class="sxs-lookup"><span data-stu-id="e7467-103">Clears the proxy bypass list.</span></span>  
  
<span data-ttu-id="e7467-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e7467-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e7467-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e7467-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="e7467-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<по умолчаниюПрокси>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e7467-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="e7467-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<обвахние>**](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e7467-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>\
<span data-ttu-id="e7467-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ясно>**</span><span class="sxs-lookup"><span data-stu-id="e7467-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e7467-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7467-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7467-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e7467-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e7467-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e7467-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7467-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e7467-112">Attributes</span></span>  
 <span data-ttu-id="e7467-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="e7467-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e7467-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e7467-114">Child Elements</span></span>  
 <span data-ttu-id="e7467-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="e7467-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7467-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e7467-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e7467-117">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="e7467-117">**Element**</span></span>|<span data-ttu-id="e7467-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e7467-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e7467-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="e7467-119">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="e7467-120">Предоставляет набор регулярных выражений, описывающие адреса, которые не используют прокси.</span><span class="sxs-lookup"><span data-stu-id="e7467-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7467-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="e7467-121">Remarks</span></span>  
 <span data-ttu-id="e7467-122">Элемент `clear` очищает все записи из списка обхода.</span><span class="sxs-lookup"><span data-stu-id="e7467-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e7467-123">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="e7467-123">Configuration Files</span></span>  
 <span data-ttu-id="e7467-124">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e7467-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7467-125">Пример</span><span class="sxs-lookup"><span data-stu-id="e7467-125">Example</span></span>  
 <span data-ttu-id="e7467-126">Следующий пример очищает список обхода, а затем добавляет два адреса в список обхода.</span><span class="sxs-lookup"><span data-stu-id="e7467-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="e7467-127">Первый обходит прокси для всех серверов в домене contoso.com; второй обходит прокси для всех серверов, чей IP-адрес начинается с 192.168.</span><span class="sxs-lookup"><span data-stu-id="e7467-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
         <clear/>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="e7467-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e7467-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="e7467-129">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="e7467-129">Network Settings Schema</span></span>](index.md)
