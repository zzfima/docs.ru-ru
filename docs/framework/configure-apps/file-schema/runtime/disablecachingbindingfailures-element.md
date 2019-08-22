---
title: Элемент <disableCachingBindingFailures>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba74907e2f6fc2ca14e12a24113fa7654c9b967e
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663802"
---
# <a name="disablecachingbindingfailures-element"></a><span data-ttu-id="e490e-102">\<Элемент > disableCachingBindingFailures</span><span class="sxs-lookup"><span data-stu-id="e490e-102">\<disableCachingBindingFailures> Element</span></span>
<span data-ttu-id="e490e-103">Указывает, следует ли отключать кэширование ошибок привязки, возникающих из-за того, что сборка не была найдена проверкой.</span><span class="sxs-lookup"><span data-stu-id="e490e-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
 <span data-ttu-id="e490e-104">\<Элемент Configuration ></span><span class="sxs-lookup"><span data-stu-id="e490e-104">\<configuration> Element</span></span>  
<span data-ttu-id="e490e-105">\<Элемент > среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e490e-105">\<runtime> Element</span></span>  
<span data-ttu-id="e490e-106">\<disableCachingBindingFailures ></span><span class="sxs-lookup"><span data-stu-id="e490e-106">\<disableCachingBindingFailures></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e490e-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e490e-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e490e-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e490e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e490e-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e490e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e490e-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e490e-110">Attributes</span></span>  
  
|<span data-ttu-id="e490e-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e490e-111">Attribute</span></span>|<span data-ttu-id="e490e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e490e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e490e-113">enabled</span><span class="sxs-lookup"><span data-stu-id="e490e-113">enabled</span></span>|<span data-ttu-id="e490e-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e490e-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="e490e-115">Указывает, следует ли отключать кэширование ошибок привязки, возникающих из-за того, что сборка не была найдена проверкой.</span><span class="sxs-lookup"><span data-stu-id="e490e-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e490e-116">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="e490e-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="e490e-117">Значение</span><span class="sxs-lookup"><span data-stu-id="e490e-117">Value</span></span>|<span data-ttu-id="e490e-118">Описание</span><span class="sxs-lookup"><span data-stu-id="e490e-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e490e-119">0</span><span class="sxs-lookup"><span data-stu-id="e490e-119">0</span></span>|<span data-ttu-id="e490e-120">Не отключайте кэширование ошибок привязки, возникающих из-за того, что сборка не была найдена проверкой.</span><span class="sxs-lookup"><span data-stu-id="e490e-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="e490e-121">Это поведение привязки по умолчанию, начинающееся с .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="e490e-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="e490e-122">1</span><span class="sxs-lookup"><span data-stu-id="e490e-122">1</span></span>|<span data-ttu-id="e490e-123">Отключите кэширование ошибок привязки, возникающих из-за того, что сборка не была найдена проверкой.</span><span class="sxs-lookup"><span data-stu-id="e490e-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="e490e-124">Этот параметр восстанавливает поведение привязки .NET Framework версии 1,1.</span><span class="sxs-lookup"><span data-stu-id="e490e-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e490e-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e490e-125">Child Elements</span></span>  
 <span data-ttu-id="e490e-126">Нет.</span><span class="sxs-lookup"><span data-stu-id="e490e-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e490e-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e490e-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e490e-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="e490e-128">Element</span></span>|<span data-ttu-id="e490e-129">Описание</span><span class="sxs-lookup"><span data-stu-id="e490e-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e490e-130">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e490e-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e490e-131">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="e490e-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e490e-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="e490e-132">Remarks</span></span>  
 <span data-ttu-id="e490e-133">Начиная с версии .NET Framework 2,0, поведением по умолчанию для загрузки сборок является кэширование всех ошибок привязки и загрузки.</span><span class="sxs-lookup"><span data-stu-id="e490e-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="e490e-134">То есть если попытка загрузить сборку завершается ошибкой, последующие запросы на загрузку одной и той же сборки будут завершаться сбоем немедленно, без каких-либо попыток нахождение сборки.</span><span class="sxs-lookup"><span data-stu-id="e490e-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="e490e-135">Этот элемент отключает поведение по умолчанию для сбоев привязки, возникающих из-за того, что сборка не найдена в пути поиска.</span><span class="sxs-lookup"><span data-stu-id="e490e-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="e490e-136">Эти ошибки вызываются <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="e490e-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="e490e-137">Этот элемент не влияет на некоторые ошибки привязки и загрузки и всегда кэшируется.</span><span class="sxs-lookup"><span data-stu-id="e490e-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="e490e-138">Эти сбои возникают из-за того, что сборка найдена, но не может быть загружена.</span><span class="sxs-lookup"><span data-stu-id="e490e-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="e490e-139">Они создают <xref:System.BadImageFormatException> или <xref:System.IO.FileLoadException>.</span><span class="sxs-lookup"><span data-stu-id="e490e-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="e490e-140">В следующем списке приведены некоторые примеры таких сбоев.</span><span class="sxs-lookup"><span data-stu-id="e490e-140">The following list includes some examples of such failures.</span></span>  
  
- <span data-ttu-id="e490e-141">Если попытка загрузить файл не является допустимой сборкой, последующие попытки загрузки сборки завершатся ошибкой, даже если поврежденный файл заменяется правильной сборкой.</span><span class="sxs-lookup"><span data-stu-id="e490e-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
- <span data-ttu-id="e490e-142">При попытке загрузить сборку, заблокированную файловой системой, последующие попытки загрузки сборки завершатся ошибкой даже после того, как сборка будет освобождена файловой системой.</span><span class="sxs-lookup"><span data-stu-id="e490e-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
- <span data-ttu-id="e490e-143">Если одна или несколько версий сборки, которые вы пытаетесь загрузить, находятся в пути поиска, но конкретная Запрашиваемая версия не существует, последующие попытки загрузки этой версии завершатся ошибкой, даже если в путь поиска проверки перемещается правильная версия.</span><span class="sxs-lookup"><span data-stu-id="e490e-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e490e-144">Пример</span><span class="sxs-lookup"><span data-stu-id="e490e-144">Example</span></span>  
 <span data-ttu-id="e490e-145">В следующем примере показано, как отключить кэширование ошибок привязки сборок, возникающих из-за того, что сборка не была найдена проверкой.</span><span class="sxs-lookup"><span data-stu-id="e490e-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e490e-146">См. также</span><span class="sxs-lookup"><span data-stu-id="e490e-146">See also</span></span>

- [<span data-ttu-id="e490e-147">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e490e-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e490e-148">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e490e-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e490e-149">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="e490e-149">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
