---
title: Элемент <remove> для webRequestModules (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: afa1aef8ea71f43a136987ec5b6e1925c6d9fb40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154729"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="8d793-102">\<удалить элемент> для webRequestModules (Настройки сети)</span><span class="sxs-lookup"><span data-stu-id="8d793-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="8d793-103">Удаляет из приложения пользовательский модуль веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="8d793-103">Removes a custom Web request module from the application.</span></span>  
  
<span data-ttu-id="8d793-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8d793-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8d793-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8d793-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="8d793-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8d793-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="8d793-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<удалить>**</span><span class="sxs-lookup"><span data-stu-id="8d793-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="8d793-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d793-108">Syntax</span></span>  
  
```xml  
<remove
  prefix="URI prefix"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d793-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8d793-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8d793-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8d793-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d793-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8d793-111">Attributes</span></span>  
  
|<span data-ttu-id="8d793-112">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="8d793-112">**Attribute**</span></span>|<span data-ttu-id="8d793-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8d793-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="8d793-114">Префикс URI для запросов, обрабатываемых этим модулем веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="8d793-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8d793-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8d793-115">Child Elements</span></span>  
 <span data-ttu-id="8d793-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="8d793-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8d793-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8d793-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8d793-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="8d793-118">**Element**</span></span>|<span data-ttu-id="8d793-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8d793-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8d793-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="8d793-120">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="8d793-121">Определяет модули для использования для запроса информации у сетевых хостов.</span><span class="sxs-lookup"><span data-stu-id="8d793-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d793-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="8d793-122">Remarks</span></span>  
 <span data-ttu-id="8d793-123">Элемент `remove` удаляет зарегистрированный модуль веб-запроса для указанной префикса URI.</span><span class="sxs-lookup"><span data-stu-id="8d793-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="8d793-124">Значение для `prefix` атрибута должно быть ведущими символами действительного URI`http`- например, "" или ""`http://www.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="8d793-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8d793-125">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="8d793-125">Configuration Files</span></span>  
 <span data-ttu-id="8d793-126">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="8d793-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d793-127">Пример</span><span class="sxs-lookup"><span data-stu-id="8d793-127">Example</span></span>  

<span data-ttu-id="8d793-128">Следующий пример удаляет существующий модуль веб-запроса для HTTP, а затем `www.contoso.com`регистрирует новый пользовательский модуль веб-запроса для запросов HTTP.</span><span class="sxs-lookup"><span data-stu-id="8d793-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d793-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8d793-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="8d793-130">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="8d793-130">Network Settings Schema</span></span>](index.md)
