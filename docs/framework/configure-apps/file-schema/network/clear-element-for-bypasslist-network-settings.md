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
ms.openlocfilehash: 2ad6b16370f600299439d2e810dfefa1b5fa3c06
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087529"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="8fb45-102">\<Clear > элемента для бипасслист (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="8fb45-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="8fb45-103">Очищает список обхода прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="8fb45-103">Clears the proxy bypass list.</span></span>  
  
<span data-ttu-id="8fb45-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8fb45-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8fb45-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8fb45-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="8fb45-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8fb45-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="8fb45-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<бипасслист >** ](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8fb45-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>\
<span data-ttu-id="8fb45-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="8fb45-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8fb45-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8fb45-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8fb45-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8fb45-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8fb45-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8fb45-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8fb45-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8fb45-112">Attributes</span></span>  
 <span data-ttu-id="8fb45-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8fb45-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8fb45-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8fb45-114">Child Elements</span></span>  
 <span data-ttu-id="8fb45-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8fb45-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8fb45-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8fb45-116">Parent Elements</span></span>  
  
|<span data-ttu-id="8fb45-117">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="8fb45-117">**Element**</span></span>|<span data-ttu-id="8fb45-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8fb45-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8fb45-119">бипасслист</span><span class="sxs-lookup"><span data-stu-id="8fb45-119">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="8fb45-120">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="8fb45-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fb45-121">Заметки</span><span class="sxs-lookup"><span data-stu-id="8fb45-121">Remarks</span></span>  
 <span data-ttu-id="8fb45-122">Элемент `clear` удаляет все записи из списка обхода.</span><span class="sxs-lookup"><span data-stu-id="8fb45-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8fb45-123">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="8fb45-123">Configuration Files</span></span>  
 <span data-ttu-id="8fb45-124">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="8fb45-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fb45-125">Пример</span><span class="sxs-lookup"><span data-stu-id="8fb45-125">Example</span></span>  
 <span data-ttu-id="8fb45-126">В следующем примере очищается список обхода, а затем два адреса добавляются в список обхода.</span><span class="sxs-lookup"><span data-stu-id="8fb45-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="8fb45-127">Первый обход прокси-сервера для всех серверов в домене contoso.com; во втором пропускается прокси-сервер для всех серверов, IP-адрес которых начинается с 192,168.</span><span class="sxs-lookup"><span data-stu-id="8fb45-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8fb45-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8fb45-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="8fb45-129">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="8fb45-129">Network Settings Schema</span></span>](index.md)
