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
ms.openlocfilehash: 7499d15f1d57887ffc3e78b83ed686c0c0f46cf4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203526"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="9b4e1-102">\<Очистить > элемент для bypasslist (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="9b4e1-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="9b4e1-103">Очищает список обхода прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="9b4e1-103">Clears the proxy bypass list.</span></span>  
  
 <span data-ttu-id="9b4e1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9b4e1-104">\<configuration></span></span>  
<span data-ttu-id="9b4e1-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="9b4e1-105">\<system.net></span></span>  
<span data-ttu-id="9b4e1-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="9b4e1-106">\<defaultProxy></span></span>  
<span data-ttu-id="9b4e1-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="9b4e1-107">\<bypasslist></span></span>  
<span data-ttu-id="9b4e1-108">\<Очистить ></span><span class="sxs-lookup"><span data-stu-id="9b4e1-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b4e1-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b4e1-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b4e1-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9b4e1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9b4e1-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9b4e1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b4e1-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9b4e1-112">Attributes</span></span>  
 <span data-ttu-id="9b4e1-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9b4e1-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9b4e1-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9b4e1-114">Child Elements</span></span>  
 <span data-ttu-id="9b4e1-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9b4e1-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b4e1-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9b4e1-116">Parent Elements</span></span>  
  
|<span data-ttu-id="9b4e1-117">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="9b4e1-117">**Element**</span></span>|<span data-ttu-id="9b4e1-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9b4e1-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9b4e1-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="9b4e1-119">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="9b4e1-120">Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="9b4e1-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b4e1-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="9b4e1-121">Remarks</span></span>  
 <span data-ttu-id="9b4e1-122">`clear` Элемент удаляет все записи из списка обхода.</span><span class="sxs-lookup"><span data-stu-id="9b4e1-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9b4e1-123">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="9b4e1-123">Configuration Files</span></span>  
 <span data-ttu-id="9b4e1-124">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="9b4e1-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b4e1-125">Пример</span><span class="sxs-lookup"><span data-stu-id="9b4e1-125">Example</span></span>  
 <span data-ttu-id="9b4e1-126">В следующем примере очищает список обхода и затем добавляются два адреса в списке пропускаемых адресов.</span><span class="sxs-lookup"><span data-stu-id="9b4e1-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="9b4e1-127">Первый обходит прокси-сервер для всех серверов в домене contoso.com. второй обходит прокси-сервер для всех серверов, IP-адрес начинается с 192.168.</span><span class="sxs-lookup"><span data-stu-id="9b4e1-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9b4e1-128">См. также</span><span class="sxs-lookup"><span data-stu-id="9b4e1-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="9b4e1-129">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="9b4e1-129">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
