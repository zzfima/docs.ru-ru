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
ms.openlocfilehash: 5b15c504a01a0ab8e17b8ad8811d9ed183609322
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456264"
---
# <a name="startup-element"></a><span data-ttu-id="35a5f-102">\<Startup > элемент</span><span class="sxs-lookup"><span data-stu-id="35a5f-102">\<startup> element</span></span>

<span data-ttu-id="35a5f-103">Указывает информация запуска среды CLR.</span><span class="sxs-lookup"><span data-stu-id="35a5f-103">Specifies common language runtime startup information.</span></span>

 <span data-ttu-id="35a5f-104">\<Конфигурация > \<startup ></span><span class="sxs-lookup"><span data-stu-id="35a5f-104">\<configuration> \<startup></span></span>

## <a name="syntax"></a><span data-ttu-id="35a5f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35a5f-105">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="35a5f-106">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="35a5f-106">Attributes and elements</span></span>

 <span data-ttu-id="35a5f-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="35a5f-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="35a5f-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="35a5f-108">Attributes</span></span>

|<span data-ttu-id="35a5f-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="35a5f-109">Attribute</span></span>|<span data-ttu-id="35a5f-110">Описание</span><span class="sxs-lookup"><span data-stu-id="35a5f-110">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="35a5f-111">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="35a5f-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="35a5f-112">Указывает, следует ли включить [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] политике активации среды выполнения или использовать [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] политике активации.</span><span class="sxs-lookup"><span data-stu-id="35a5f-112">Specifies whether to enable the [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy or to use the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="35a5f-113">атрибут useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="35a5f-113">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="35a5f-114">Значение</span><span class="sxs-lookup"><span data-stu-id="35a5f-114">Value</span></span>|<span data-ttu-id="35a5f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="35a5f-115">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="35a5f-116">Включить [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] политике активации среды выполнения для выбранной среды выполнения, используемого для привязки методы активации старой среды выполнения (таких как [функция CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) в среду выполнения, выбранный из файла конфигурации вместо ограничивая их в среде CLR версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="35a5f-116">Enable [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="35a5f-117">Таким образом Если вы выбрали CLR версии 4 или более поздней версии из файла конфигурации, смешанных сборок, созданных в более ранних версиях платформы .NET Framework, загружаются с выбранной версией среды CLR.</span><span class="sxs-lookup"><span data-stu-id="35a5f-117">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="35a5f-118">Установка этого значения предотвращает CLR версии 1.1 или среду CLR версии 2.0 загрузку в одном процессе, эффективно отключение функции-process side-by-side.</span><span class="sxs-lookup"><span data-stu-id="35a5f-118">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="35a5f-119">Используйте политику активации по умолчанию для .NET Framework 4 и более поздних версий, чтобы разрешить старой среды выполнения методов активации для загрузки в процесс среды CLR версии 1.1 или 2.0.</span><span class="sxs-lookup"><span data-stu-id="35a5f-119">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="35a5f-120">Установка этого значения предотвращает смешанной сборки от загрузки в .NET Framework 4 или более поздней версии, если они были созданы с помощью .NET Framework 4 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="35a5f-120">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="35a5f-121">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="35a5f-121">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="35a5f-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="35a5f-122">Child elements</span></span>

|<span data-ttu-id="35a5f-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="35a5f-123">Element</span></span>|<span data-ttu-id="35a5f-124">Описание</span><span class="sxs-lookup"><span data-stu-id="35a5f-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="35a5f-125">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="35a5f-125">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="35a5f-126">Указывает, что приложение поддерживает только версию 1.0 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="35a5f-126">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="35a5f-127">Приложения, созданные с помощью среды выполнения версии 1.1 или более поздней, должны использовать  **\<supportedRuntime >** элемент.</span><span class="sxs-lookup"><span data-stu-id="35a5f-127">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="35a5f-128">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="35a5f-128">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="35a5f-129">Указывает, какие версии среды CLR поддерживает приложение.</span><span class="sxs-lookup"><span data-stu-id="35a5f-129">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="35a5f-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="35a5f-130">Parent elements</span></span>

|<span data-ttu-id="35a5f-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="35a5f-131">Element</span></span>|<span data-ttu-id="35a5f-132">Описание</span><span class="sxs-lookup"><span data-stu-id="35a5f-132">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="35a5f-133">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="35a5f-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="35a5f-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="35a5f-134">Remarks</span></span>

 <span data-ttu-id="35a5f-135">**\<SupportedRuntime>** элемент должен использоваться всеми приложениями, собранными с применением версии 1.1 или более поздней версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="35a5f-135">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="35a5f-136">Приложения, созданные для поддержки только версии 1.0 среды выполнения, должны использовать  **\<requiredRuntime >** элемент.</span><span class="sxs-lookup"><span data-stu-id="35a5f-136">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="35a5f-137">Код запуска для приложения, размещенного в Internet Explorer не учитывает  **\<startup >** элемент и его дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="35a5f-137">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="35a5f-138">Атрибут useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="35a5f-138">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="35a5f-139">Этот атрибут полезен, если приложение использует устаревшие активации пути, такие как [функция CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), и нужно, чтобы эти пути для активации версии 4 среды CLR вместо более ранней версии, или если приложение созданные с помощью .NET Framework 4, но имеет зависимость от сборки смешанного режима, созданных с помощью более ранней версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="35a5f-139">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="35a5f-140">В этих сценариях, задать для атрибута `true`.</span><span class="sxs-lookup"><span data-stu-id="35a5f-140">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="35a5f-141">Присвоение атрибуту `true` предотвращает загрузку в одном процессе, эффективно отключение функции-process side-by-side CLR версии 1.1 или среду CLR версии 2.0 (см. в разделе [Side-by-Side выполнение для COM-взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="35a5f-141">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="35a5f-142">Пример</span><span class="sxs-lookup"><span data-stu-id="35a5f-142">Example</span></span>

 <span data-ttu-id="35a5f-143">Приведенный ниже показано, как указать версию среды выполнения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="35a5f-143">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="35a5f-144">См. также</span><span class="sxs-lookup"><span data-stu-id="35a5f-144">See also</span></span>

- [<span data-ttu-id="35a5f-145">Схема параметров запуска</span><span class="sxs-lookup"><span data-stu-id="35a5f-145">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="35a5f-146">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="35a5f-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="35a5f-147">Практическое руководство. Настройка приложения для включения поддержки .NET Framework версии 4 и выше</span><span class="sxs-lookup"><span data-stu-id="35a5f-147">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="35a5f-148">[Выполнение Side-by-Side COM-взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="35a5f-148">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="35a5f-149">Внутрипроцессное параллельное выполнение</span><span class="sxs-lookup"><span data-stu-id="35a5f-149">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
