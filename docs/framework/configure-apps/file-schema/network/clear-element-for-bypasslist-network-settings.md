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
ms.openlocfilehash: 4d078dac14103560423bfccdd4a1717031e7a60f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699503"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="f3e54-102">Элемент > @no__t 0clear для бипасслист (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="f3e54-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="f3e54-103">Очищает список обхода прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="f3e54-103">Clears the proxy bypass list.</span></span>  
  
[<span data-ttu-id="f3e54-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f3e54-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f3e54-105">&nbsp; @ no__t-1[ **@no__t -4system. NET >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f3e54-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="f3e54-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f3e54-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="f3e54-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<bypasslist >** ](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f3e54-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>  
<span data-ttu-id="f3e54-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="f3e54-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3e54-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3e54-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3e54-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f3e54-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f3e54-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f3e54-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3e54-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f3e54-112">Attributes</span></span>  
 <span data-ttu-id="f3e54-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="f3e54-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f3e54-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f3e54-114">Child Elements</span></span>  
 <span data-ttu-id="f3e54-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="f3e54-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3e54-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f3e54-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f3e54-117">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="f3e54-117">**Element**</span></span>|<span data-ttu-id="f3e54-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f3e54-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f3e54-119">бипасслист</span><span class="sxs-lookup"><span data-stu-id="f3e54-119">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="f3e54-120">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="f3e54-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3e54-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3e54-121">Remarks</span></span>  
 <span data-ttu-id="f3e54-122">Элемент `clear` удаляет все записи из списка обхода.</span><span class="sxs-lookup"><span data-stu-id="f3e54-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f3e54-123">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="f3e54-123">Configuration Files</span></span>  
 <span data-ttu-id="f3e54-124">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f3e54-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3e54-125">Пример</span><span class="sxs-lookup"><span data-stu-id="f3e54-125">Example</span></span>  
 <span data-ttu-id="f3e54-126">В следующем примере очищается список обхода, а затем два адреса добавляются в список обхода.</span><span class="sxs-lookup"><span data-stu-id="f3e54-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="f3e54-127">Первый обход прокси-сервера для всех серверов в домене contoso.com; во втором пропускается прокси-сервер для всех серверов, IP-адрес которых начинается с 192,168.</span><span class="sxs-lookup"><span data-stu-id="f3e54-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f3e54-128">См. также</span><span class="sxs-lookup"><span data-stu-id="f3e54-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="f3e54-129">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="f3e54-129">Network Settings Schema</span></span>](index.md)
