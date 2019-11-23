---
title: Элемент <startup>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: 634d9c5248c33619abec50d441d95c111febdcbf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699416"
---
# <a name="startup-element"></a><span data-ttu-id="26529-102">Элемент > запуска \<</span><span class="sxs-lookup"><span data-stu-id="26529-102">\<startup> element</span></span>

<span data-ttu-id="26529-103">Задает сведения о запуске среды CLR.</span><span class="sxs-lookup"><span data-stu-id="26529-103">Specifies common language runtime startup information.</span></span>

[<span data-ttu-id="26529-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="26529-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="26529-105">&nbsp;&nbsp; **\<запуска >**</span><span class="sxs-lookup"><span data-stu-id="26529-105">&nbsp;&nbsp;**\<startup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="26529-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26529-106">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="26529-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="26529-107">Attributes and elements</span></span>

 <span data-ttu-id="26529-108">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="26529-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="26529-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="26529-109">Attributes</span></span>

|<span data-ttu-id="26529-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="26529-110">Attribute</span></span>|<span data-ttu-id="26529-111">Описание</span><span class="sxs-lookup"><span data-stu-id="26529-111">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="26529-112">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="26529-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="26529-113">Указывает, следует ли включить политику активации среды выполнения .NET Framework 2,0 или использовать политику активации .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="26529-113">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="26529-114">атрибут useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="26529-114">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="26529-115">Значение</span><span class="sxs-lookup"><span data-stu-id="26529-115">Value</span></span>|<span data-ttu-id="26529-116">Описание</span><span class="sxs-lookup"><span data-stu-id="26529-116">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="26529-117">Включите политику активации среды выполнения .NET Framework 2,0 для выбранной среды выполнения, чтобы привязать устаревшие методы активации среды выполнения (например, [функцию CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) к среде выполнения, выбранной из файла конфигурации, вместо того, чтобы заключать их в CLR версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="26529-117">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="26529-118">Таким же, если в файле конфигурации выбрана среда CLR версии 4 или более поздней, сборки в смешанном режиме, созданные в более ранних версиях .NET Framework, загружаются с выбранной версией среды CLR.</span><span class="sxs-lookup"><span data-stu-id="26529-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="26529-119">Установка этого значения предотвращает загрузку среды CLR версии 1,1 или CLR версии 2,0 в один и тот же процесс, фактически отключив внутрипроцессный параллельный компонент.</span><span class="sxs-lookup"><span data-stu-id="26529-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="26529-120">Используйте политику активации по умолчанию для .NET Framework 4 и более поздних версий, которая позволяет использовать устаревшие методы активации среды выполнения для загрузки среды CLR версии 1,1 или 2,0 в процесс.</span><span class="sxs-lookup"><span data-stu-id="26529-120">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="26529-121">Установка этого значения предотвращает загрузку сборок в смешанном режиме в .NET Framework 4 или более поздней версии, если они не были созданы с помощью .NET Framework 4 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="26529-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="26529-122">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="26529-122">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="26529-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="26529-123">Child elements</span></span>

|<span data-ttu-id="26529-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="26529-124">Element</span></span>|<span data-ttu-id="26529-125">Описание</span><span class="sxs-lookup"><span data-stu-id="26529-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="26529-126">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="26529-126">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="26529-127">Указывает, что приложение поддерживает только версию 1.0 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="26529-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="26529-128">Приложения, созданные с помощью среды выполнения версии 1,1 или более поздней, должны использовать элемент **\<supportedRuntime >** .</span><span class="sxs-lookup"><span data-stu-id="26529-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="26529-129">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="26529-129">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="26529-130">Указывает, какие версии среды CLR поддерживает приложение.</span><span class="sxs-lookup"><span data-stu-id="26529-130">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="26529-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="26529-131">Parent elements</span></span>

|<span data-ttu-id="26529-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="26529-132">Element</span></span>|<span data-ttu-id="26529-133">Описание</span><span class="sxs-lookup"><span data-stu-id="26529-133">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="26529-134">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="26529-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="26529-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="26529-135">Remarks</span></span>

 <span data-ttu-id="26529-136">**\<SupportedRuntime>** элемент должен использоваться всеми приложениями, собранными с применением версии 1.1 или более поздней версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="26529-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="26529-137">Приложения, созданные для поддержки только версии 1,0 среды выполнения, должны использовать элемент **\<requiredRuntime >** .</span><span class="sxs-lookup"><span data-stu-id="26529-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="26529-138">Код запуска приложения, размещенного в Microsoft Internet Explorer, игнорирует элемент **> запуска\<** и его дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="26529-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="26529-139">Атрибут useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="26529-139">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="26529-140">Этот атрибут полезен, если ваше приложение использует пути активации прежних версий, например [функцию CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), и вы хотите, чтобы эти пути активировали версию 4 среды CLR вместо более ранней версии или если приложение создано с .NET Framework 4, но зависит от сборки в смешанном режиме, построенной с использованием более ранней версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="26529-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="26529-141">В этих сценариях присвойте атрибуту значение `true`.</span><span class="sxs-lookup"><span data-stu-id="26529-141">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="26529-142">Присвоение атрибуту значения `true` предотвращает загрузку CLR версии 1,1 или CLR версии 2,0 в один и тот же процесс, фактически отключив внутрипроцессный параллельный компонент (см. раздел [параллельное выполнение для COM-взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="26529-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="26529-143">Пример</span><span class="sxs-lookup"><span data-stu-id="26529-143">Example</span></span>

 <span data-ttu-id="26529-144">В следующем примере показано, как указать версию среды выполнения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="26529-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="26529-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="26529-145">See also</span></span>

- [<span data-ttu-id="26529-146">Схема параметров запуска</span><span class="sxs-lookup"><span data-stu-id="26529-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="26529-147">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="26529-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="26529-148">Как настроить приложение для поддержки .NET Framework 4 или более поздних версий</span><span class="sxs-lookup"><span data-stu-id="26529-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="26529-149">[Параллельное выполнение для COM-взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="26529-149">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="26529-150">Внутрипроцессное параллельное выполнение</span><span class="sxs-lookup"><span data-stu-id="26529-150">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
