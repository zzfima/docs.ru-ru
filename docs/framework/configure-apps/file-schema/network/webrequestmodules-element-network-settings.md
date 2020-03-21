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
ms.openlocfilehash: 7f2805283f89e6165d336b3e593d34054e02115d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154547"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="263f8-102">\<Элемент webRequestModules> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="263f8-102">\<webRequestModules> Element (Network Settings)</span></span>
<span data-ttu-id="263f8-103">Определяет модули для использования для запроса информации у сетевых хостов.</span><span class="sxs-lookup"><span data-stu-id="263f8-103">Specifies modules to use to request information from network hosts.</span></span>  
  
[<span data-ttu-id="263f8-104">**\<конфигурация>**</span><span class="sxs-lookup"><span data-stu-id="263f8-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="263f8-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="263f8-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="263f8-106">&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="263f8-106">&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="263f8-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="263f8-107">Syntax</span></span>  
  
```xml  
<webRequestModules>
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="263f8-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="263f8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="263f8-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="263f8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="263f8-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="263f8-110">Attributes</span></span>  
 <span data-ttu-id="263f8-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="263f8-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="263f8-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="263f8-112">Child Elements</span></span>  
  
|<span data-ttu-id="263f8-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="263f8-113">**Element**</span></span>|<span data-ttu-id="263f8-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="263f8-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="263f8-115">добавление</span><span class="sxs-lookup"><span data-stu-id="263f8-115">add</span></span>](add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="263f8-116">Добавляет пользовательский модуль веб-запроса в приложение.</span><span class="sxs-lookup"><span data-stu-id="263f8-116">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="263f8-117">Ясно</span><span class="sxs-lookup"><span data-stu-id="263f8-117">clear</span></span>](clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="263f8-118">Удаляет из приложения все зарегистрированные модули веб-запросов.</span><span class="sxs-lookup"><span data-stu-id="263f8-118">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="263f8-119">удаление</span><span class="sxs-lookup"><span data-stu-id="263f8-119">remove</span></span>](remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="263f8-120">Удаляет из приложения пользовательский модуль веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="263f8-120">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="263f8-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="263f8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="263f8-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="263f8-122">**Element**</span></span>|<span data-ttu-id="263f8-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="263f8-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="263f8-124">system.net</span><span class="sxs-lookup"><span data-stu-id="263f8-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="263f8-125">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="263f8-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="263f8-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="263f8-126">Remarks</span></span>  
 <span data-ttu-id="263f8-127">Элемент `webRequestModules` регистрирует потомки класса <xref:System.Net.WebRequest>, чтобы обработать запросы информации к сетевым узлам.</span><span class="sxs-lookup"><span data-stu-id="263f8-127">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="263f8-128">Модули веб-запроса должны реализовать <xref:System.Net.IWebRequestCreate> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="263f8-128">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="263f8-129">Рамочка .NET включает в себя веб-запросы модулей для URI, которые начинаются с `http://` `https://`, и `file://`.</span><span class="sxs-lookup"><span data-stu-id="263f8-129">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="263f8-130">Переопределить модули по умолчанию можно только зарегистрировав пользовательский модуль в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="263f8-130">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="263f8-131">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="263f8-131">Configuration Files</span></span>  
 <span data-ttu-id="263f8-132">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="263f8-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="263f8-133">Пример</span><span class="sxs-lookup"><span data-stu-id="263f8-133">Example</span></span>  
 <span data-ttu-id="263f8-134">Следующий пример регистрирует модуль HTTP по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="263f8-134">The following example registers the default HTTP module.</span></span> <span data-ttu-id="263f8-135">Необходимо заменить значения для версии и PublicKeyToken правильными значениями для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="263f8-135">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="263f8-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="263f8-136">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="263f8-137">Схема настройки сети</span><span class="sxs-lookup"><span data-stu-id="263f8-137">Network Settings Schema</span></span>](index.md)
