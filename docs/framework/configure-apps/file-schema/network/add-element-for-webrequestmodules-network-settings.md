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
ms.openlocfilehash: 0248706ed78de160ef0131a0c7595374febf1aa9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699586"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="45498-102">Элемент > @no__t 0add для webRequestModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="45498-102">\<add> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="45498-103">Добавляет пользовательский модуль веб-запросов в приложение.</span><span class="sxs-lookup"><span data-stu-id="45498-103">Adds a custom Web request module to the application.</span></span>  
  
[<span data-ttu-id="45498-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="45498-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="45498-105">&nbsp; @ no__t-1[ **@no__t -4system. NET >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="45498-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="45498-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<webRequestModules >** ](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="45498-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="45498-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="45498-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45498-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="45498-108">Syntax</span></span>  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45498-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="45498-109">Attributes and Elements</span></span>  
 <span data-ttu-id="45498-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="45498-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45498-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="45498-111">Attributes</span></span>  
  
|<span data-ttu-id="45498-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="45498-112">**Attribute**</span></span>|<span data-ttu-id="45498-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="45498-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="45498-114">Префикс URI для запросов, обрабатываемых этим модулем веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="45498-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="45498-115">Полное имя типа (указанное свойством <xref:System.Type.FullName%2A>) и имя сборки (обозначенное свойством <xref:System.Reflection.Assembly.FullName%2A>), разделенные запятыми, которые реализуют этот модуль веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="45498-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45498-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="45498-116">Child Elements</span></span>  
 <span data-ttu-id="45498-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="45498-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45498-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="45498-118">Parent Elements</span></span>  
  
|<span data-ttu-id="45498-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="45498-119">**Element**</span></span>|<span data-ttu-id="45498-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="45498-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="45498-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="45498-121">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="45498-122">Указывает модули, используемые для запроса сведений от сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="45498-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45498-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="45498-123">Remarks</span></span>  
 <span data-ttu-id="45498-124">Атрибут `prefix` определяет префикс URI, который использует указанный модуль веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="45498-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="45498-125">Модули веб-запросов обычно регистрируются для работы с конкретным протоколом, например HTTP или FTP, но могут быть зарегистрированы, чтобы обрабатывать запросы к определенному серверу или пути на сервере.</span><span class="sxs-lookup"><span data-stu-id="45498-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="45498-126">Модуль веб-запросов создается, когда соответствующий префикс URI передается в метод <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="45498-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="45498-127">Значение атрибута `prefix` должно быть начальным символом допустимого URI.</span><span class="sxs-lookup"><span data-stu-id="45498-127">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="45498-128">Например, `http` или `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="45498-128">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="45498-129">Значением атрибута `type` должно быть допустимое имя типа и соответствующее имя сборки, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="45498-129">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="45498-130">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="45498-130">Configuration Files</span></span>  
 <span data-ttu-id="45498-131">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="45498-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="45498-132">Пример</span><span class="sxs-lookup"><span data-stu-id="45498-132">Example</span></span>  
 <span data-ttu-id="45498-133">В следующем примере регистрируется пользовательский модуль веб-запросов для HTTP.</span><span class="sxs-lookup"><span data-stu-id="45498-133">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="45498-134">Необходимо заменить значения для Version и PublicKeyToken правильными значениями для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="45498-134">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="45498-135">См. также</span><span class="sxs-lookup"><span data-stu-id="45498-135">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="45498-136">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="45498-136">Network Settings Schema</span></span>](index.md)
