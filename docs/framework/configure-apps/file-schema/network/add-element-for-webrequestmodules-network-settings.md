---
title: "&lt;Добавить&gt; элемент для webRequestModules (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
caps.latest.revision: "16"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: fd407f77e75bce4bdbc37acd5f28bbe39f92d564
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="7ccea-102">&lt;Добавить&gt; элемент для webRequestModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="7ccea-102">&lt;add&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="7ccea-103">Добавляет в приложение пользовательский модуль веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="7ccea-103">Adds a custom Web request module to the application.</span></span>  
  
 <span data-ttu-id="7ccea-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7ccea-104">\<configuration></span></span>  
<span data-ttu-id="7ccea-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="7ccea-105">\<system.net></span></span>  
<span data-ttu-id="7ccea-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="7ccea-106">\<webRequestModules></span></span>  
<span data-ttu-id="7ccea-107">\<add></span><span class="sxs-lookup"><span data-stu-id="7ccea-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ccea-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ccea-108">Syntax</span></span>  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ccea-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7ccea-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7ccea-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7ccea-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ccea-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7ccea-111">Attributes</span></span>  
  
|<span data-ttu-id="7ccea-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="7ccea-112">**Attribute**</span></span>|<span data-ttu-id="7ccea-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7ccea-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="7ccea-114">Префикс URI для запросов, обрабатываемых этот модуль веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="7ccea-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="7ccea-115">Полное имя типа (обозначается <xref:System.Type.FullName%2A> свойства) и имя сборки (обозначается <xref:System.Reflection.Assembly.FullName%2A> свойства), разделенных запятыми, который реализует этот модуль веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="7ccea-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ccea-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7ccea-116">Child Elements</span></span>  
 <span data-ttu-id="7ccea-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7ccea-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ccea-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7ccea-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7ccea-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="7ccea-119">**Element**</span></span>|<span data-ttu-id="7ccea-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7ccea-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7ccea-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="7ccea-121">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="7ccea-122">Задает модули, используемые для запроса данных от сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="7ccea-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ccea-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="7ccea-123">Remarks</span></span>  
 <span data-ttu-id="7ccea-124">`prefix` Атрибут определяет префикс URI, который использует указанный модуль веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="7ccea-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="7ccea-125">Модули веб-запросов обычно регистрируются для обработки определенных протоколов, таких как HTTP или FTP, но могут быть зарегистрированы для обработки запросов к определенному серверу или пути на сервере.</span><span class="sxs-lookup"><span data-stu-id="7ccea-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="7ccea-126">Модуль веб-запросов создается в том случае, если соответствующий префикс URI передается на <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="7ccea-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="7ccea-127">Значение для `prefix` атрибут должен иметь первые символы допустимый URI — например, «http» или «http://www.contoso.com».</span><span class="sxs-lookup"><span data-stu-id="7ccea-127">The value for the `prefix` attribute should be the leading characters of a valid URI --for example, "http", or "http://www.contoso.com".</span></span>  
  
 <span data-ttu-id="7ccea-128">Значение для `type` атрибут должен быть допустимым именем типа и соответствующее имя сборки, разделенных точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="7ccea-128">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma .</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7ccea-129">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="7ccea-129">Configuration Files</span></span>  
 <span data-ttu-id="7ccea-130">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="7ccea-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ccea-131">Пример</span><span class="sxs-lookup"><span data-stu-id="7ccea-131">Example</span></span>  
 <span data-ttu-id="7ccea-132">В следующем примере регистрируется пользовательский модуль веб-запросов для HTTP.</span><span class="sxs-lookup"><span data-stu-id="7ccea-132">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="7ccea-133">Следует заменить значения для Version и PublicKeyToken правильные значения для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="7ccea-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ccea-134">См. также</span><span class="sxs-lookup"><span data-stu-id="7ccea-134">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="7ccea-135">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="7ccea-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
