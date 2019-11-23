---
title: Элемент <webRequestModules> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: e119d9ce1f8bb6f07f8050612550db459a2f065c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697465"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="e13e6-102">Элемент \<webRequestModules > (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="e13e6-102">\<webRequestModules> Element (Network Settings)</span></span>
<span data-ttu-id="e13e6-103">Указывает модули, используемые для запроса сведений от сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="e13e6-103">Specifies modules to use to request information from network hosts.</span></span>  
  
[<span data-ttu-id="e13e6-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="e13e6-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="e13e6-105">&nbsp;&nbsp;[ **\<System. NET >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e13e6-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="e13e6-106">&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="e13e6-106">&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e13e6-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e13e6-107">Syntax</span></span>  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e13e6-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e13e6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e13e6-109">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e13e6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e13e6-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e13e6-110">Attributes</span></span>  
 <span data-ttu-id="e13e6-111">Нет</span><span class="sxs-lookup"><span data-stu-id="e13e6-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e13e6-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e13e6-112">Child Elements</span></span>  
  
|<span data-ttu-id="e13e6-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="e13e6-113">**Element**</span></span>|<span data-ttu-id="e13e6-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e13e6-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e13e6-115">add</span><span class="sxs-lookup"><span data-stu-id="e13e6-115">add</span></span>](add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="e13e6-116">Добавляет пользовательский модуль веб-запросов в приложение.</span><span class="sxs-lookup"><span data-stu-id="e13e6-116">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="e13e6-117">clear</span><span class="sxs-lookup"><span data-stu-id="e13e6-117">clear</span></span>](clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="e13e6-118">Удаляет из приложения все зарегистрированные модули веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="e13e6-118">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="e13e6-119">remove</span><span class="sxs-lookup"><span data-stu-id="e13e6-119">remove</span></span>](remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="e13e6-120">Удаляет пользовательский модуль веб-запросов из приложения.</span><span class="sxs-lookup"><span data-stu-id="e13e6-120">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e13e6-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e13e6-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e13e6-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="e13e6-122">**Element**</span></span>|<span data-ttu-id="e13e6-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e13e6-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e13e6-124">system.net</span><span class="sxs-lookup"><span data-stu-id="e13e6-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="e13e6-125">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="e13e6-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e13e6-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="e13e6-126">Remarks</span></span>  
 <span data-ttu-id="e13e6-127">Элемент `webRequestModules` регистрирует потомки класса <xref:System.Net.WebRequest>, чтобы обработать запросы информации к сетевым узлам.</span><span class="sxs-lookup"><span data-stu-id="e13e6-127">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="e13e6-128">Модули веб-запросов должны реализовывать интерфейс <xref:System.Net.IWebRequestCreate>.</span><span class="sxs-lookup"><span data-stu-id="e13e6-128">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="e13e6-129">.NET Framework включает модули веб-запросов для URI, которые начинаются с `http://`, `https://`и `file://`.</span><span class="sxs-lookup"><span data-stu-id="e13e6-129">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="e13e6-130">Модули по умолчанию можно переопределить только путем регистрации пользовательского модуля в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e13e6-130">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e13e6-131">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="e13e6-131">Configuration Files</span></span>  
 <span data-ttu-id="e13e6-132">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e13e6-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e13e6-133">Пример</span><span class="sxs-lookup"><span data-stu-id="e13e6-133">Example</span></span>  
 <span data-ttu-id="e13e6-134">В следующем примере регистрируется HTTP-модуль по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e13e6-134">The following example registers the default HTTP module.</span></span> <span data-ttu-id="e13e6-135">Необходимо заменить значения для Version и PublicKeyToken правильными значениями для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="e13e6-135">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e13e6-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="e13e6-136">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="e13e6-137">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="e13e6-137">Network Settings Schema</span></span>](index.md)
