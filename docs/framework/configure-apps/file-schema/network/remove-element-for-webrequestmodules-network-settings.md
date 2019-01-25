---
title: '&lt;Удалить&gt; элемент для webRequestModules (параметры сети)'
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
ms.openlocfilehash: 380438bbc6e0c93b26d2afb77ff6b04308c61caf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547070"
---
# <a name="ltremovegt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="598a1-102">&lt;Удалить&gt; элемент для webRequestModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="598a1-102">&lt;remove&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="598a1-103">Удаляет пользовательский модуль веб-запросов из приложения.</span><span class="sxs-lookup"><span data-stu-id="598a1-103">Removes a custom Web request module from the application.</span></span>  
  
 <span data-ttu-id="598a1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="598a1-104">\<configuration></span></span>  
<span data-ttu-id="598a1-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="598a1-105">\<system.net></span></span>  
<span data-ttu-id="598a1-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="598a1-106">\<webRequestModules></span></span>  
<span data-ttu-id="598a1-107">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="598a1-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="598a1-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="598a1-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="598a1-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="598a1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="598a1-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="598a1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="598a1-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="598a1-111">Attributes</span></span>  
  
|<span data-ttu-id="598a1-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="598a1-112">**Attribute**</span></span>|<span data-ttu-id="598a1-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="598a1-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="598a1-114">Префикс URI для запросов, обрабатываемых этот модуль веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="598a1-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="598a1-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="598a1-115">Child Elements</span></span>  
 <span data-ttu-id="598a1-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="598a1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="598a1-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="598a1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="598a1-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="598a1-118">**Element**</span></span>|<span data-ttu-id="598a1-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="598a1-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="598a1-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="598a1-120">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="598a1-121">Задает модули, используемые для запроса данных от сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="598a1-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="598a1-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="598a1-122">Remarks</span></span>  
 <span data-ttu-id="598a1-123">`remove` Элемент удаляет зарегистрированный модуль веб-запросов для заданного префикса URI.</span><span class="sxs-lookup"><span data-stu-id="598a1-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="598a1-124">Значение для `prefix` атрибут должен быть из ведущих символов является допустимым URI — например, "`http`«, или"`http://www.contoso.com`«.</span><span class="sxs-lookup"><span data-stu-id="598a1-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="598a1-125">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="598a1-125">Configuration Files</span></span>  
 <span data-ttu-id="598a1-126">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="598a1-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="598a1-127">Пример</span><span class="sxs-lookup"><span data-stu-id="598a1-127">Example</span></span>  

<span data-ttu-id="598a1-128">В следующем примере удаляется существующий модуль веб-запросов для HTTP и затем регистрирует новый пользовательский модуль веб-запросов для HTTP запрашивает `www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="598a1-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="598a1-129">См. также</span><span class="sxs-lookup"><span data-stu-id="598a1-129">See also</span></span>
- <xref:System.Net.WebRequest>
- [<span data-ttu-id="598a1-130">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="598a1-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
