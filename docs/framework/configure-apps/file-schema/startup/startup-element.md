---
title: '&lt;При запуске&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 60699f0335bb35589341558800cfd64503d0aa0a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltstartupgt-element"></a><span data-ttu-id="198d6-102">&lt;При запуске&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="198d6-102">&lt;startup&gt; Element</span></span>
<span data-ttu-id="198d6-103">Указывает информация запуска среды CLR.</span><span class="sxs-lookup"><span data-stu-id="198d6-103">Specifies common language runtime startup information.</span></span>  
  
 <span data-ttu-id="198d6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="198d6-104">\<configuration></span></span>  
<span data-ttu-id="198d6-105">\<При запуске ></span><span class="sxs-lookup"><span data-stu-id="198d6-105">\<startup></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="198d6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="198d6-106">Syntax</span></span>  
  
```xml  
<startup useLegacyV2RuntimeActivationPolicy="true|false" >   
</startup>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="198d6-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="198d6-107">Attributes and Elements</span></span>  
 <span data-ttu-id="198d6-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="198d6-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="198d6-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="198d6-109">Attributes</span></span>  
  
|<span data-ttu-id="198d6-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="198d6-110">Attribute</span></span>|<span data-ttu-id="198d6-111">Описание</span><span class="sxs-lookup"><span data-stu-id="198d6-111">Description</span></span>|  
|---------------|-----------------|  
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="198d6-112">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="198d6-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="198d6-113">Указывает, следует ли включить [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] политике активации среды выполнения или использовать [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] политике активации.</span><span class="sxs-lookup"><span data-stu-id="198d6-113">Specifies whether to enable the [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy or to use the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] activation policy.</span></span>|  
  
## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="198d6-114">Атрибут useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="198d6-114">useLegacyV2RuntimeActivationPolicy Attribute</span></span>  
  
|<span data-ttu-id="198d6-115">Значение</span><span class="sxs-lookup"><span data-stu-id="198d6-115">Value</span></span>|<span data-ttu-id="198d6-116">Описание</span><span class="sxs-lookup"><span data-stu-id="198d6-116">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="198d6-117">Включить [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] политике активации среды выполнения для выбранной среды выполнения, является привязка методы активации прежних версий среды выполнения (например, [CorBindToRuntimeEx-функция](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)) в среду выполнения из файла конфигурации, а не выбраны ограниченного их в среде CLR версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="198d6-117">Enable [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="198d6-118">Таким образом Если вы выбрали CLR версии 4 или более поздней версии из файла конфигурации, смешанных сборок, созданных в более ранних версиях платформы .NET Framework, загружаются с выбранной версией среды CLR.</span><span class="sxs-lookup"><span data-stu-id="198d6-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="198d6-119">Установка этого значения предотвращает CLR версии 1.1 или среда CLR версии 2.0 загрузку в один процесс, эффективно отключив функцию side-by-side-process.</span><span class="sxs-lookup"><span data-stu-id="198d6-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|  
|`false`|<span data-ttu-id="198d6-120">Используйте политику активации по умолчанию для [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] и более поздних версиях это разрешить методы активации для загрузки среды CLR версии 1.1 или 2.0 в процесс прежних версий среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="198d6-120">Use the default activation policy for the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="198d6-121">Установка этого значения предотвращает сборки смешанного режима от загрузки в .NET Framework 4 или более поздней версии, если они были созданы с .NET Framework 4 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="198d6-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="198d6-122">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="198d6-122">This value is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="198d6-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="198d6-123">Child Elements</span></span>  
  
|<span data-ttu-id="198d6-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="198d6-124">Element</span></span>|<span data-ttu-id="198d6-125">Описание</span><span class="sxs-lookup"><span data-stu-id="198d6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="198d6-126">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="198d6-126">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="198d6-127">Указывает, что приложение поддерживает только версию 1.0 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="198d6-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="198d6-128">Приложения, собранные с помощью версии 1.1 или более поздней, должны использовать  **\<supportedRuntime >** элемента.</span><span class="sxs-lookup"><span data-stu-id="198d6-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="198d6-129">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="198d6-129">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="198d6-130">Указывает, какие версии среды CLR поддерживает приложение.</span><span class="sxs-lookup"><span data-stu-id="198d6-130">Specifies which versions of the common language runtime the application supports.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="198d6-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="198d6-131">Parent Elements</span></span>  
  
|<span data-ttu-id="198d6-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="198d6-132">Element</span></span>|<span data-ttu-id="198d6-133">Описание</span><span class="sxs-lookup"><span data-stu-id="198d6-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="198d6-134">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="198d6-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="198d6-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="198d6-135">Remarks</span></span>  
 <span data-ttu-id="198d6-136">**\<SupportedRuntime >** элемент должен использоваться всеми приложениями, собранными с помощью версии 1.1 или более поздней версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="198d6-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="198d6-137">Приложения, созданные для поддержки только версии 1.0 среды выполнения, должны использовать  **\<requiredRuntime >** элемента.</span><span class="sxs-lookup"><span data-stu-id="198d6-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>  
  
 <span data-ttu-id="198d6-138">Код запуска для приложения, размещенного в Internet Explorer не учитывает  **\<запуска >** и его дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="198d6-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>  
  
## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="198d6-139">Атрибут useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="198d6-139">The useLegacyV2RuntimeActivationPolicy Attribute</span></span>  
 <span data-ttu-id="198d6-140">Этот атрибут полезен, если приложение использует устаревшие активации пути, такие как [функция CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), и нужно, чтобы эти пути для активации версии 4 среды CLR вместо более ранней версии, или если ваше приложение созданные с помощью [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] но имеет зависимость от сборки смешанного режима, созданного с помощью более ранней версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="198d6-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="198d6-141">В этих сценариях, присвойте атрибуту значение `true`.</span><span class="sxs-lookup"><span data-stu-id="198d6-141">In those scenarios, set the attribute to `true`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="198d6-142">Присвоение атрибуту `true` запрещает загрузку в один процесс, эффективно отключив функцию-process side-by-side CLR версии 1.1 или среда CLR версии 2.0 (в разделе [Side-by-Side выполнение COM-взаимодействия](http://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)).</span><span class="sxs-lookup"><span data-stu-id="198d6-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](http://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="198d6-143">Пример</span><span class="sxs-lookup"><span data-stu-id="198d6-143">Example</span></span>  
 <span data-ttu-id="198d6-144">Приведенный ниже показано, как указать версию среды выполнения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="198d6-144">The following example shows how to specify the runtime version in a configuration file.</span></span>  
  
```xml  
<!-- When used with version 1.0 of the .NET Framework runtime -->  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
<!-- When used with version 1.1 (or later) of the runtime -->  
<configuration>  
   <startup>  
      <supportedRuntime version="v1.1.4322"/>  
      <supportedRuntime version="v1.0.3705"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="198d6-145">См. также</span><span class="sxs-lookup"><span data-stu-id="198d6-145">See Also</span></span>  
 [<span data-ttu-id="198d6-146">Схема параметров запуска</span><span class="sxs-lookup"><span data-stu-id="198d6-146">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="198d6-147">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="198d6-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="198d6-148">\<PaveOver> Указание используемой версии среды выполнения</span><span class="sxs-lookup"><span data-stu-id="198d6-148">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)  
 [<span data-ttu-id="198d6-149">Выполнение Side-by-Side COM-взаимодействия</span><span class="sxs-lookup"><span data-stu-id="198d6-149">Side-by-Side Execution for COM Interop</span></span>](http://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)  
 [<span data-ttu-id="198d6-150">Внутрипроцессное параллельное выполнение</span><span class="sxs-lookup"><span data-stu-id="198d6-150">In-Process Side-by-Side Execution</span></span>](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)
