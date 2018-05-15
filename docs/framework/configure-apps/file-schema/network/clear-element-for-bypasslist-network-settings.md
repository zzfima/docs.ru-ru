---
title: '&lt;Очистить&gt; элемент для bypasslist (параметры сети)'
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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 9297b68a31117aabfa45328954ccb9c7cdac66c5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltcleargt-element-for-bypasslist-network-settings"></a><span data-ttu-id="ac1c9-102">&lt;Очистить&gt; элемент для bypasslist (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="ac1c9-102">&lt;clear&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="ac1c9-103">Очищает список обхода прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="ac1c9-103">Clears the proxy bypass list.</span></span>  
  
 <span data-ttu-id="ac1c9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ac1c9-104">\<configuration></span></span>  
<span data-ttu-id="ac1c9-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="ac1c9-105">\<system.net></span></span>  
<span data-ttu-id="ac1c9-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="ac1c9-106">\<defaultProxy></span></span>  
<span data-ttu-id="ac1c9-107">\<bypasslist ></span><span class="sxs-lookup"><span data-stu-id="ac1c9-107">\<bypasslist></span></span>  
<span data-ttu-id="ac1c9-108">\<Очистить ></span><span class="sxs-lookup"><span data-stu-id="ac1c9-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac1c9-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac1c9-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac1c9-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ac1c9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ac1c9-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ac1c9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac1c9-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ac1c9-112">Attributes</span></span>  
 <span data-ttu-id="ac1c9-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ac1c9-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ac1c9-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ac1c9-114">Child Elements</span></span>  
 <span data-ttu-id="ac1c9-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ac1c9-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac1c9-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ac1c9-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ac1c9-117">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="ac1c9-117">**Element**</span></span>|<span data-ttu-id="ac1c9-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ac1c9-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ac1c9-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="ac1c9-119">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="ac1c9-120">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="ac1c9-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac1c9-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="ac1c9-121">Remarks</span></span>  
 <span data-ttu-id="ac1c9-122">`clear` Элемент удаляет все записи из списка обхода.</span><span class="sxs-lookup"><span data-stu-id="ac1c9-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ac1c9-123">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="ac1c9-123">Configuration Files</span></span>  
 <span data-ttu-id="ac1c9-124">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ac1c9-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac1c9-125">Пример</span><span class="sxs-lookup"><span data-stu-id="ac1c9-125">Example</span></span>  
 <span data-ttu-id="ac1c9-126">В следующем примере очищает список обхода и затем добавляет два адреса в список обхода.</span><span class="sxs-lookup"><span data-stu-id="ac1c9-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="ac1c9-127">Первый обход прокси-сервера для всех серверов в домене contoso.com. второй обход прокси-сервера для всех серверов, IP-адрес начинается с 192.168.</span><span class="sxs-lookup"><span data-stu-id="ac1c9-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ac1c9-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ac1c9-128">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="ac1c9-129">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="ac1c9-129">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
