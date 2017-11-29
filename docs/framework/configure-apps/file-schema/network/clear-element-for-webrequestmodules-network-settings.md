---
title: "&lt;Очистить&gt; элемент для webRequestModules (параметры сети)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, webRequestModules
- <webRequestModules>, clear element
- webRequestModules, clear element
- clear element, webRequestModules
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c88792663b07ace7250b6ee4065e60d6cfb90afd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltcleargt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="8d56a-102">&lt;Очистить&gt; элемент для webRequestModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="8d56a-102">&lt;clear&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="8d56a-103">Удаляет все зарегистрированные модули веб-запросов из приложения.</span><span class="sxs-lookup"><span data-stu-id="8d56a-103">Removes all registered Web request modules from the application.</span></span>  
  
 <span data-ttu-id="8d56a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8d56a-104">\<configuration></span></span>  
<span data-ttu-id="8d56a-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="8d56a-105">\<system.net></span></span>  
<span data-ttu-id="8d56a-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="8d56a-106">\<webRequestModules></span></span>  
<span data-ttu-id="8d56a-107">\<Очистить ></span><span class="sxs-lookup"><span data-stu-id="8d56a-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d56a-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d56a-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d56a-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8d56a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8d56a-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8d56a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d56a-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8d56a-111">Attributes</span></span>  
 <span data-ttu-id="8d56a-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8d56a-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8d56a-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8d56a-113">Child Elements</span></span>  
 <span data-ttu-id="8d56a-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8d56a-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8d56a-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8d56a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="8d56a-116">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="8d56a-116">**Element**</span></span>|<span data-ttu-id="8d56a-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8d56a-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8d56a-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="8d56a-118">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="8d56a-119">Задает модули, используемые для запроса данных от сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="8d56a-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d56a-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="8d56a-120">Remarks</span></span>  
 <span data-ttu-id="8d56a-121">`clear` Элемент удаляет все зарегистрированные модули веб-запросов, определенные ранее в файле конфигурации или на более высоком уровне в иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8d56a-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8d56a-122">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="8d56a-122">Configuration Files</span></span>  
 <span data-ttu-id="8d56a-123">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="8d56a-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d56a-124">Пример</span><span class="sxs-lookup"><span data-stu-id="8d56a-124">Example</span></span>  
 <span data-ttu-id="8d56a-125">Следующий пример удаляет все модули веб-запросов и затем регистрирует модуль веб-запросов для HTTP.</span><span class="sxs-lookup"><span data-stu-id="8d56a-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8d56a-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8d56a-126">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="8d56a-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="8d56a-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
