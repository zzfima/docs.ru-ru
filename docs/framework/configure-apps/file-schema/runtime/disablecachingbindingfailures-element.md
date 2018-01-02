---
title: "&lt;disableCachingBindingFailures&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd86bc2f58bc216f741c32a51925d3f4f8ef47df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltdisablecachingbindingfailuresgt-element"></a><span data-ttu-id="a0995-102">&lt;disableCachingBindingFailures&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="a0995-102">&lt;disableCachingBindingFailures&gt; Element</span></span>
<span data-ttu-id="a0995-103">Указывает, следует ли отключить кэширование привязки ошибок, возникающих при проверке сборка не найдена.</span><span class="sxs-lookup"><span data-stu-id="a0995-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
 <span data-ttu-id="a0995-104">\<Конфигурация > элемент</span><span class="sxs-lookup"><span data-stu-id="a0995-104">\<configuration> Element</span></span>  
<span data-ttu-id="a0995-105">\<Среда выполнения > элемент</span><span class="sxs-lookup"><span data-stu-id="a0995-105">\<runtime> Element</span></span>  
<span data-ttu-id="a0995-106">\<disableCachingBindingFailures ></span><span class="sxs-lookup"><span data-stu-id="a0995-106">\<disableCachingBindingFailures></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0995-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0995-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0995-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a0995-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a0995-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a0995-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0995-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a0995-110">Attributes</span></span>  
  
|<span data-ttu-id="a0995-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a0995-111">Attribute</span></span>|<span data-ttu-id="a0995-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a0995-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a0995-113">enabled</span><span class="sxs-lookup"><span data-stu-id="a0995-113">enabled</span></span>|<span data-ttu-id="a0995-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a0995-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="a0995-115">Указывает, следует ли отключить кэширование привязки ошибок, возникающих при проверке сборка не найдена.</span><span class="sxs-lookup"><span data-stu-id="a0995-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a0995-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="a0995-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="a0995-117">Значение</span><span class="sxs-lookup"><span data-stu-id="a0995-117">Value</span></span>|<span data-ttu-id="a0995-118">Описание</span><span class="sxs-lookup"><span data-stu-id="a0995-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a0995-119">0</span><span class="sxs-lookup"><span data-stu-id="a0995-119">0</span></span>|<span data-ttu-id="a0995-120">Не отключайте кэширование привязки ошибок, возникающих при проверке сборка не найдена.</span><span class="sxs-lookup"><span data-stu-id="a0995-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="a0995-121">Это поведение по умолчанию привязки, начиная с .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="a0995-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="a0995-122">1</span><span class="sxs-lookup"><span data-stu-id="a0995-122">1</span></span>|<span data-ttu-id="a0995-123">Отключите кэширование привязки ошибок, возникающих при проверке сборка не найдена.</span><span class="sxs-lookup"><span data-stu-id="a0995-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="a0995-124">Этот параметр возвращается к поведение привязки для .NET Framework версии 1.1.</span><span class="sxs-lookup"><span data-stu-id="a0995-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0995-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a0995-125">Child Elements</span></span>  
 <span data-ttu-id="a0995-126">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a0995-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0995-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a0995-127">Parent Elements</span></span>  
  
|<span data-ttu-id="a0995-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="a0995-128">Element</span></span>|<span data-ttu-id="a0995-129">Описание</span><span class="sxs-lookup"><span data-stu-id="a0995-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a0995-130">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a0995-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a0995-131">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="a0995-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0995-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0995-132">Remarks</span></span>  
 <span data-ttu-id="a0995-133">Начиная с .NET Framework версии 2.0, поведение по умолчанию для загрузки сборок является все привязки и сбои загрузки.</span><span class="sxs-lookup"><span data-stu-id="a0995-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="a0995-134">То есть при неудачной попытке загрузить сборку, последующие запросы на загрузку той же сборке сбоем немедленно, без любая попытка найти сборку.</span><span class="sxs-lookup"><span data-stu-id="a0995-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="a0995-135">Этот элемент отключает поведение по умолчанию для ошибок привязки, возникающих, так как не удалось найти сборку в путь поиска сборок.</span><span class="sxs-lookup"><span data-stu-id="a0995-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="a0995-136">Эти ошибки throw <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="a0995-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="a0995-137">Некоторые привязки и сбои при загрузке не затрагиваются этим элементом и всегда кэшируются.</span><span class="sxs-lookup"><span data-stu-id="a0995-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="a0995-138">Эти сбои возникают, поскольку сборка найдена, но не может быть загружена.</span><span class="sxs-lookup"><span data-stu-id="a0995-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="a0995-139">Они создают <xref:System.BadImageFormatException> или <xref:System.IO.FileLoadException>.</span><span class="sxs-lookup"><span data-stu-id="a0995-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="a0995-140">Ниже приведены некоторые примеры таких сбоев.</span><span class="sxs-lookup"><span data-stu-id="a0995-140">The following list includes some examples of such failures.</span></span>  
  
-   <span data-ttu-id="a0995-141">При попытке загрузить файл не является допустимой сборкой, последующие попытки загрузить сборку завершится ошибкой, даже если неверный файл заменяется правильную сборку.</span><span class="sxs-lookup"><span data-stu-id="a0995-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
-   <span data-ttu-id="a0995-142">При попытке загрузить сборку, заблокированную файловой системой, последующие попытки загрузить сборку не удастся даже после освобождения сборки файловой системой.</span><span class="sxs-lookup"><span data-stu-id="a0995-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
-   <span data-ttu-id="a0995-143">Если один или несколько версий сборки, который вы пытаетесь загрузить в путь поиска сборок, но между ними не конкретной версии, запрашиваемый, последующие попытки загрузить эту версию завершится ошибкой, даже если правильная версия перемещается в путь поиска сборок.</span><span class="sxs-lookup"><span data-stu-id="a0995-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0995-144">Пример</span><span class="sxs-lookup"><span data-stu-id="a0995-144">Example</span></span>  
 <span data-ttu-id="a0995-145">В следующем примере показано, как отключить кэширование ошибок привязки сборок, возникающих при проверке сборка не найдена.</span><span class="sxs-lookup"><span data-stu-id="a0995-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a0995-146">См. также</span><span class="sxs-lookup"><span data-stu-id="a0995-146">See Also</span></span>  
 [<span data-ttu-id="a0995-147">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a0995-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="a0995-148">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="a0995-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="a0995-149">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="a0995-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
