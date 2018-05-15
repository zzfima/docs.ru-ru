---
title: '&lt;Очистить&gt; элемент для webRequestModules (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, webRequestModules
- <webRequestModules>, clear element
- webRequestModules, clear element
- clear element, webRequestModules
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 4d89fbc757198f25219b8051bf77dbdeea0cef53
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltcleargt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="c4f84-102">&lt;Очистить&gt; элемент для webRequestModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="c4f84-102">&lt;clear&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="c4f84-103">Удаляет все зарегистрированные модули веб-запросов из приложения.</span><span class="sxs-lookup"><span data-stu-id="c4f84-103">Removes all registered Web request modules from the application.</span></span>  
  
 <span data-ttu-id="c4f84-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c4f84-104">\<configuration></span></span>  
<span data-ttu-id="c4f84-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="c4f84-105">\<system.net></span></span>  
<span data-ttu-id="c4f84-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="c4f84-106">\<webRequestModules></span></span>  
<span data-ttu-id="c4f84-107">\<Очистить ></span><span class="sxs-lookup"><span data-stu-id="c4f84-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4f84-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4f84-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4f84-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c4f84-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c4f84-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c4f84-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4f84-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c4f84-111">Attributes</span></span>  
 <span data-ttu-id="c4f84-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c4f84-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c4f84-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c4f84-113">Child Elements</span></span>  
 <span data-ttu-id="c4f84-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c4f84-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4f84-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c4f84-115">Parent Elements</span></span>  
  
|<span data-ttu-id="c4f84-116">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="c4f84-116">**Element**</span></span>|<span data-ttu-id="c4f84-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c4f84-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c4f84-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="c4f84-118">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="c4f84-119">Задает модули, используемые для запроса данных от сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="c4f84-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4f84-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="c4f84-120">Remarks</span></span>  
 <span data-ttu-id="c4f84-121">`clear` Элемент удаляет все зарегистрированные модули веб-запросов, определенные ранее в файле конфигурации или на более высоком уровне в иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c4f84-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c4f84-122">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="c4f84-122">Configuration Files</span></span>  
 <span data-ttu-id="c4f84-123">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c4f84-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4f84-124">Пример</span><span class="sxs-lookup"><span data-stu-id="c4f84-124">Example</span></span>  
 <span data-ttu-id="c4f84-125">Следующий пример удаляет все модули веб-запросов и затем регистрирует модуль веб-запросов для HTTP.</span><span class="sxs-lookup"><span data-stu-id="c4f84-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <clear/>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4f84-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c4f84-126">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="c4f84-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="c4f84-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
