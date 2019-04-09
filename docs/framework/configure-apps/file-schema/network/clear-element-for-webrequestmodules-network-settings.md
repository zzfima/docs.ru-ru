---
title: <clear> Элемент для webRequestModules (параметры сети)
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
ms.openlocfilehash: 5dea238629b282776cb45f7b388e655fa557d084
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078984"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="60ef5-102">\<Очистить > элемент для webRequestModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="60ef5-102">\<clear> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="60ef5-103">Удаляет все зарегистрированные модули веб-запросов из приложения.</span><span class="sxs-lookup"><span data-stu-id="60ef5-103">Removes all registered Web request modules from the application.</span></span>  
  
 <span data-ttu-id="60ef5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="60ef5-104">\<configuration></span></span>  
<span data-ttu-id="60ef5-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="60ef5-105">\<system.net></span></span>  
<span data-ttu-id="60ef5-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="60ef5-106">\<webRequestModules></span></span>  
<span data-ttu-id="60ef5-107">\<Очистить ></span><span class="sxs-lookup"><span data-stu-id="60ef5-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60ef5-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60ef5-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60ef5-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="60ef5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="60ef5-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="60ef5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60ef5-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="60ef5-111">Attributes</span></span>  
 <span data-ttu-id="60ef5-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="60ef5-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="60ef5-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="60ef5-113">Child Elements</span></span>  
 <span data-ttu-id="60ef5-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="60ef5-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60ef5-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="60ef5-115">Parent Elements</span></span>  
  
|**<span data-ttu-id="60ef5-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="60ef5-116">Element</span></span>**|**<span data-ttu-id="60ef5-117">Описание</span><span class="sxs-lookup"><span data-stu-id="60ef5-117">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="60ef5-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="60ef5-118">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="60ef5-119">Задает модули, используемые для запроса данных от сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="60ef5-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60ef5-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="60ef5-120">Remarks</span></span>  
 <span data-ttu-id="60ef5-121">`clear` Элемент удаляет все зарегистрированные модули веб-запросов, которые были ранее определены в файле конфигурации или на более высоком уровне в иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="60ef5-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="60ef5-122">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="60ef5-122">Configuration Files</span></span>  
 <span data-ttu-id="60ef5-123">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="60ef5-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="60ef5-124">Пример</span><span class="sxs-lookup"><span data-stu-id="60ef5-124">Example</span></span>  
 <span data-ttu-id="60ef5-125">В следующем примере удаляет все модули веб-запросов и затем регистрирует модуль веб-запросов для HTTP.</span><span class="sxs-lookup"><span data-stu-id="60ef5-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="60ef5-126">См. также</span><span class="sxs-lookup"><span data-stu-id="60ef5-126">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="60ef5-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="60ef5-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
