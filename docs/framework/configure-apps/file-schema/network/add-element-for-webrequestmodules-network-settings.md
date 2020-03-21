---
title: Элемент <add> для webRequestModules (параметры сети)
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
ms.openlocfilehash: f4edce948033478aab59a2aff61abadc55a327ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155028"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="cba15-102">\<добавить элемент> для webRequestModules (Настройки сети)</span><span class="sxs-lookup"><span data-stu-id="cba15-102">\<add> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="cba15-103">Добавляет пользовательский модуль веб-запроса в приложение.</span><span class="sxs-lookup"><span data-stu-id="cba15-103">Adds a custom Web request module to the application.</span></span>  

<span data-ttu-id="cba15-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cba15-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cba15-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cba15-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="cba15-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cba15-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="cba15-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<добавить>**</span><span class="sxs-lookup"><span data-stu-id="cba15-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="cba15-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cba15-108">Syntax</span></span>  
  
```xml  
<add
  prefix="URI prefix"
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cba15-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cba15-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cba15-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cba15-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cba15-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cba15-111">Attributes</span></span>  
  
|<span data-ttu-id="cba15-112">**Атрибут**</span><span class="sxs-lookup"><span data-stu-id="cba15-112">**Attribute**</span></span>|<span data-ttu-id="cba15-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="cba15-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="cba15-114">Префикс URI для запросов, обрабатываемых этим модулем веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="cba15-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="cba15-115">Полностью квалифицированное имя <xref:System.Type.FullName%2A> типа (указано свойством) <xref:System.Reflection.Assembly.FullName%2A> и имя сборки (указанное свойством), разделенное запятой, которая реализует этот модуль веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="cba15-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cba15-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cba15-116">Child Elements</span></span>  
 <span data-ttu-id="cba15-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="cba15-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cba15-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cba15-118">Parent Elements</span></span>  
  
|<span data-ttu-id="cba15-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="cba15-119">**Element**</span></span>|<span data-ttu-id="cba15-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="cba15-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cba15-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="cba15-121">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="cba15-122">Определяет модули для использования для запроса информации у сетевых хостов.</span><span class="sxs-lookup"><span data-stu-id="cba15-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cba15-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="cba15-123">Remarks</span></span>  
 <span data-ttu-id="cba15-124">Атрибут `prefix` определяет префикс URI, который использует указанный модуль веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="cba15-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="cba15-125">Модули веб-запросов обычно регистрируются для обработки определенного протокола, например HTTP или FTP, но могут быть зарегистрированы для обработки запроса на конкретный сервер или путь на сервере.</span><span class="sxs-lookup"><span data-stu-id="cba15-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="cba15-126">Модуль веб-запроса создается, когда приставка <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> URI, соответствующая, передается методу.</span><span class="sxs-lookup"><span data-stu-id="cba15-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="cba15-127">Значение атрибута `prefix` должно быть ведущими символами действительного URI.</span><span class="sxs-lookup"><span data-stu-id="cba15-127">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="cba15-128">Например, `http` или `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="cba15-128">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="cba15-129">Значение для `type` атрибута должно быть действительным именем типа и соответствующим именем сборки, разделенным запятой.</span><span class="sxs-lookup"><span data-stu-id="cba15-129">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="cba15-130">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="cba15-130">Configuration Files</span></span>  
 <span data-ttu-id="cba15-131">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="cba15-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cba15-132">Пример</span><span class="sxs-lookup"><span data-stu-id="cba15-132">Example</span></span>  
 <span data-ttu-id="cba15-133">В следующем примере регистрируется пользовательский модуль веб-запросов для HTTP.</span><span class="sxs-lookup"><span data-stu-id="cba15-133">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="cba15-134">Необходимо заменить значения для версии и PublicKeyToken правильными значениями для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="cba15-134">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cba15-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cba15-135">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="cba15-136">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="cba15-136">Network Settings Schema</span></span>](index.md)
