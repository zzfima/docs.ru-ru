---
title: '&lt;Добавить&gt; элемент для webRequestModules (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 921f5f2bfda1a19d022d3f3f4131e3653fd17ea7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742794"
---
# <a name="ltaddgt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="74c87-102">&lt;Добавить&gt; элемент для webRequestModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="74c87-102">&lt;add&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="74c87-103">Добавляет в приложение пользовательский модуль веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="74c87-103">Adds a custom Web request module to the application.</span></span>  
  
 <span data-ttu-id="74c87-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="74c87-104">\<configuration></span></span>  
<span data-ttu-id="74c87-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="74c87-105">\<system.net></span></span>  
<span data-ttu-id="74c87-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="74c87-106">\<webRequestModules></span></span>  
<span data-ttu-id="74c87-107">\<add></span><span class="sxs-lookup"><span data-stu-id="74c87-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74c87-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74c87-108">Syntax</span></span>  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74c87-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="74c87-109">Attributes and Elements</span></span>  
 <span data-ttu-id="74c87-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="74c87-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74c87-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="74c87-111">Attributes</span></span>  
  
|<span data-ttu-id="74c87-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="74c87-112">**Attribute**</span></span>|<span data-ttu-id="74c87-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="74c87-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="74c87-114">Префикс URI для запросов, обрабатываемых этот модуль веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="74c87-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="74c87-115">Полное имя типа (обозначается <xref:System.Type.FullName%2A> свойства) и имя сборки (обозначается <xref:System.Reflection.Assembly.FullName%2A> свойства), разделенных запятыми, который реализует этот модуль веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="74c87-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74c87-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="74c87-116">Child Elements</span></span>  
 <span data-ttu-id="74c87-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="74c87-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74c87-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="74c87-118">Parent Elements</span></span>  
  
|<span data-ttu-id="74c87-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="74c87-119">**Element**</span></span>|<span data-ttu-id="74c87-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="74c87-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="74c87-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="74c87-121">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="74c87-122">Задает модули, используемые для запроса данных от сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="74c87-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74c87-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="74c87-123">Remarks</span></span>  
 <span data-ttu-id="74c87-124">`prefix` Атрибут определяет префикс URI, который использует указанный модуль веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="74c87-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="74c87-125">Модули веб-запросов обычно регистрируются для обработки определенных протоколов, таких как HTTP или FTP, но могут быть зарегистрированы для обработки запросов к определенному серверу или пути на сервере.</span><span class="sxs-lookup"><span data-stu-id="74c87-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="74c87-126">Модуль веб-запросов создается в том случае, если соответствующий префикс URI передается на <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="74c87-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="74c87-127">Значение для `prefix` атрибут должен иметь первые символы допустимый URI — например, «http», или «http://www.contoso.com».</span><span class="sxs-lookup"><span data-stu-id="74c87-127">The value for the `prefix` attribute should be the leading characters of a valid URI --for example, "http", or "http://www.contoso.com".</span></span>  
  
 <span data-ttu-id="74c87-128">Значение для `type` атрибут должен быть допустимым именем типа и соответствующее имя сборки, разделенных точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="74c87-128">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma .</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="74c87-129">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="74c87-129">Configuration Files</span></span>  
 <span data-ttu-id="74c87-130">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="74c87-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="74c87-131">Пример</span><span class="sxs-lookup"><span data-stu-id="74c87-131">Example</span></span>  
 <span data-ttu-id="74c87-132">В следующем примере регистрируется пользовательский модуль веб-запросов для HTTP.</span><span class="sxs-lookup"><span data-stu-id="74c87-132">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="74c87-133">Следует заменить значения для Version и PublicKeyToken правильные значения для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="74c87-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="74c87-134">См. также</span><span class="sxs-lookup"><span data-stu-id="74c87-134">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="74c87-135">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="74c87-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
