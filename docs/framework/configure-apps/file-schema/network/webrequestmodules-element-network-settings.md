---
title: '&lt;webRequestModules&gt; (сетевые параметры)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 34173812f4f6fac940632e23e6641e458250a4ee
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47110896"
---
# <a name="ltwebrequestmodulesgt-element-network-settings"></a><span data-ttu-id="f9d91-102">&lt;webRequestModules&gt; (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="f9d91-102">&lt;webRequestModules&gt; Element (Network Settings)</span></span>
<span data-ttu-id="f9d91-103">Задает модули, используемые для запроса данных от сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="f9d91-103">Specifies modules to use to request information from network hosts.</span></span>  
  
 <span data-ttu-id="f9d91-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f9d91-104">\<configuration></span></span>  
<span data-ttu-id="f9d91-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="f9d91-105">\<system.net></span></span>  
<span data-ttu-id="f9d91-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="f9d91-106">\<webRequestModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9d91-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9d91-107">Syntax</span></span>  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9d91-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f9d91-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f9d91-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f9d91-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9d91-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f9d91-110">Attributes</span></span>  
 <span data-ttu-id="f9d91-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f9d91-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f9d91-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f9d91-112">Child Elements</span></span>  
  
|<span data-ttu-id="f9d91-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="f9d91-113">**Element**</span></span>|<span data-ttu-id="f9d91-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f9d91-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f9d91-115">add</span><span class="sxs-lookup"><span data-stu-id="f9d91-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="f9d91-116">Добавляет пользовательский модуль веб-запросов к приложению.</span><span class="sxs-lookup"><span data-stu-id="f9d91-116">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="f9d91-117">clear</span><span class="sxs-lookup"><span data-stu-id="f9d91-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="f9d91-118">Удаляет все зарегистрированные модули веб-запросов из приложения.</span><span class="sxs-lookup"><span data-stu-id="f9d91-118">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="f9d91-119">remove</span><span class="sxs-lookup"><span data-stu-id="f9d91-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="f9d91-120">Удаляет пользовательский модуль веб-запросов из приложения.</span><span class="sxs-lookup"><span data-stu-id="f9d91-120">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f9d91-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f9d91-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f9d91-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="f9d91-122">**Element**</span></span>|<span data-ttu-id="f9d91-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f9d91-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f9d91-124">System.NET</span><span class="sxs-lookup"><span data-stu-id="f9d91-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="f9d91-125">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="f9d91-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9d91-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="f9d91-126">Remarks</span></span>  
 <span data-ttu-id="f9d91-127">Элемент `webRequestModules` регистрирует потомки класса <xref:System.Net.WebRequest>, чтобы обработать запросы информации к сетевым узлам.</span><span class="sxs-lookup"><span data-stu-id="f9d91-127">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="f9d91-128">Модули веб-запросов необходимо реализовать <xref:System.Net.IWebRequestCreate> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f9d91-128">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="f9d91-129">.NET Framework включает модули веб-запросов для URI, который начинается с http://, https:// и file://.</span><span class="sxs-lookup"><span data-stu-id="f9d91-129">The .NET Framework includes Web request modules for URIs that begin with http://, https://, and file://.</span></span> <span data-ttu-id="f9d91-130">Модули по умолчанию можно переопределить только путем регистрации пользовательского модуля в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f9d91-130">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f9d91-131">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="f9d91-131">Configuration Files</span></span>  
 <span data-ttu-id="f9d91-132">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f9d91-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9d91-133">Пример</span><span class="sxs-lookup"><span data-stu-id="f9d91-133">Example</span></span>  
 <span data-ttu-id="f9d91-134">В следующем примере регистрируется модуль HTTP по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f9d91-134">The following example registers the default HTTP module.</span></span> <span data-ttu-id="f9d91-135">Следует заменить значения для версии и PublicKeyToken правильными значениями для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="f9d91-135">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f9d91-136">См. также</span><span class="sxs-lookup"><span data-stu-id="f9d91-136">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.IWebRequestCreate>  
 [<span data-ttu-id="f9d91-137">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="f9d91-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
