---
title: "&lt;Удалить&gt; элемент для webRequestModules (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 43f0d30f8c18c4755f31d0c851c773207bc15b78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltremovegt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="f6e03-102">&lt;Удалить&gt; элемент для webRequestModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="f6e03-102">&lt;remove&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="f6e03-103">Удаляет пользовательский модуль веб-запросов из приложения.</span><span class="sxs-lookup"><span data-stu-id="f6e03-103">Removes a custom Web request module from the application.</span></span>  
  
 <span data-ttu-id="f6e03-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f6e03-104">\<configuration></span></span>  
<span data-ttu-id="f6e03-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="f6e03-105">\<system.net></span></span>  
<span data-ttu-id="f6e03-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="f6e03-106">\<webRequestModules></span></span>  
<span data-ttu-id="f6e03-107">\<Удалите ></span><span class="sxs-lookup"><span data-stu-id="f6e03-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6e03-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6e03-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6e03-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f6e03-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f6e03-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f6e03-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6e03-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f6e03-111">Attributes</span></span>  
  
|<span data-ttu-id="f6e03-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="f6e03-112">**Attribute**</span></span>|<span data-ttu-id="f6e03-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f6e03-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="f6e03-114">Префикс URI для запросов, обрабатываемых этот модуль веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="f6e03-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6e03-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f6e03-115">Child Elements</span></span>  
 <span data-ttu-id="f6e03-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f6e03-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f6e03-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f6e03-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f6e03-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="f6e03-118">**Element**</span></span>|<span data-ttu-id="f6e03-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f6e03-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f6e03-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="f6e03-120">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="f6e03-121">Задает модули, используемые для запроса данных от сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="f6e03-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6e03-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="f6e03-122">Remarks</span></span>  
 <span data-ttu-id="f6e03-123">`remove` Элемент удаляет зарегистрированный модуль веб-запросов для заданного префикса URI.</span><span class="sxs-lookup"><span data-stu-id="f6e03-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="f6e03-124">Значение для `prefix` атрибут должен иметь первые символы допустимый URI — например, «http» или «http://www.contoso.com».</span><span class="sxs-lookup"><span data-stu-id="f6e03-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "http", or "http://www.contoso.com".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f6e03-125">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="f6e03-125">Configuration Files</span></span>  
 <span data-ttu-id="f6e03-126">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f6e03-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6e03-127">Пример</span><span class="sxs-lookup"><span data-stu-id="f6e03-127">Example</span></span>  
 <span data-ttu-id="f6e03-128">Следующий пример удаляет существующий модуль веб-запросов для HTTP, а затем выполняется регистрация нового пользовательского модуля для HTTP-запросов к www.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f6e03-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to www.contoso.com.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f6e03-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f6e03-129">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="f6e03-130">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="f6e03-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
