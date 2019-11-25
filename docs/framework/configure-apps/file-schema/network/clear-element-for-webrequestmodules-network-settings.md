---
title: Элемент <clear> для webRequestModules (параметры сети)
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
ms.openlocfilehash: 5832d120824df75d374fc94cb0aa4e08189cb965
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088499"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="76b41-102">\<Clear > элемента для webRequestModules (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="76b41-102">\<clear> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="76b41-103">Удаляет из приложения все зарегистрированные модули веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="76b41-103">Removes all registered Web request modules from the application.</span></span>  

<span data-ttu-id="76b41-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="76b41-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="76b41-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="76b41-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="76b41-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<webRequestModules >** ](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="76b41-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="76b41-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="76b41-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="76b41-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76b41-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76b41-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="76b41-109">Attributes and Elements</span></span>  
 <span data-ttu-id="76b41-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="76b41-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76b41-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="76b41-111">Attributes</span></span>  
 <span data-ttu-id="76b41-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="76b41-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="76b41-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="76b41-113">Child Elements</span></span>  
 <span data-ttu-id="76b41-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="76b41-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76b41-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="76b41-115">Parent Elements</span></span>  
  
|<span data-ttu-id="76b41-116">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="76b41-116">**Element**</span></span>|<span data-ttu-id="76b41-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="76b41-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="76b41-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="76b41-118">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="76b41-119">Указывает модули, используемые для запроса сведений от сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="76b41-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76b41-120">Заметки</span><span class="sxs-lookup"><span data-stu-id="76b41-120">Remarks</span></span>  
 <span data-ttu-id="76b41-121">Элемент `clear` удаляет все зарегистрированные модули веб-запросов, определенные ранее в файле конфигурации или на более высоком уровне иерархии конфигурации.</span><span class="sxs-lookup"><span data-stu-id="76b41-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="76b41-122">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="76b41-122">Configuration Files</span></span>  
 <span data-ttu-id="76b41-123">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="76b41-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="76b41-124">Пример</span><span class="sxs-lookup"><span data-stu-id="76b41-124">Example</span></span>  
 <span data-ttu-id="76b41-125">В следующем примере очищаются все модули веб-запросов, а затем выполняется регистрация модуля веб-запросов для HTTP.</span><span class="sxs-lookup"><span data-stu-id="76b41-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="76b41-126">См. также</span><span class="sxs-lookup"><span data-stu-id="76b41-126">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="76b41-127">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="76b41-127">Network Settings Schema</span></span>](index.md)
