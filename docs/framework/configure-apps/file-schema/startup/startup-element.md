---
title: <startup> - элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: e936c069275bfa9f7ac81ef1c6fc6228828182a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153739"
---
# <a name="startup-element"></a><span data-ttu-id="0a383-102">\<элемент запуска></span><span class="sxs-lookup"><span data-stu-id="0a383-102">\<startup> element</span></span>

<span data-ttu-id="0a383-103">Определяет информацию о запуске запуска общего языка.</span><span class="sxs-lookup"><span data-stu-id="0a383-103">Specifies common language runtime startup information.</span></span>

[<span data-ttu-id="0a383-104">**\<конфигурация>**</span><span class="sxs-lookup"><span data-stu-id="0a383-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="0a383-105">&nbsp;&nbsp;**\<>стартапа**</span><span class="sxs-lookup"><span data-stu-id="0a383-105">&nbsp;&nbsp;**\<startup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="0a383-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a383-106">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" >
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0a383-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="0a383-107">Attributes and elements</span></span>

 <span data-ttu-id="0a383-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0a383-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0a383-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0a383-109">Attributes</span></span>

|<span data-ttu-id="0a383-110">attribute</span><span class="sxs-lookup"><span data-stu-id="0a383-110">Attribute</span></span>|<span data-ttu-id="0a383-111">Описание</span><span class="sxs-lookup"><span data-stu-id="0a383-111">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="0a383-112">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0a383-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0a383-113">Уточняется, включать ли политику активации времени выполнения .NET Framework 2.0 или использовать политику активации .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="0a383-113">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="0a383-114">useLegacyV2RuntimeActivationPolicy атрибут</span><span class="sxs-lookup"><span data-stu-id="0a383-114">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="0a383-115">Значение</span><span class="sxs-lookup"><span data-stu-id="0a383-115">Value</span></span>|<span data-ttu-id="0a383-116">Описание</span><span class="sxs-lookup"><span data-stu-id="0a383-116">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="0a383-117">Включить политику активации времени выполнения .NET 2.0 для выбранного времени выполнения, которая заключается в том, чтобы связать устаревшие методы активации времени выполнения (например, [функцию CorBindToRuntimeEx)](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)с выбранным из файла конфигурации вместо того, чтобы укупорывать их в версию CLR 2.0.</span><span class="sxs-lookup"><span data-stu-id="0a383-117">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="0a383-118">Таким образом, если версия CLR 4 или более позднее выбрана из файла конфигурации, сборки смешанного режима, созданные с более ранними версиями рамочного .NET, загружаются с выбранной версией CLR.</span><span class="sxs-lookup"><span data-stu-id="0a383-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="0a383-119">Установка этого значения предотвращает загрузку версии CLR 1.1 или CLR 2.0 в тот же процесс, что фактически отключит функцию «в процессе» бок о бок.</span><span class="sxs-lookup"><span data-stu-id="0a383-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="0a383-120">Используйте политику активации по умолчанию для системы .NET 4 и позже, которая должна позволить устаревшим методам активации времени выполнения загрузить версию CLR 1.1 или 2.0 в процесс.</span><span class="sxs-lookup"><span data-stu-id="0a383-120">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="0a383-121">Установка этого значения предотвращает загрузку сборок смешанного режима в рамках .NET 4 или позже, если они не были построены с помощью .NET Framework 4 или позже.</span><span class="sxs-lookup"><span data-stu-id="0a383-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="0a383-122">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0a383-122">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0a383-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0a383-123">Child elements</span></span>

|<span data-ttu-id="0a383-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="0a383-124">Element</span></span>|<span data-ttu-id="0a383-125">Описание</span><span class="sxs-lookup"><span data-stu-id="0a383-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0a383-126">\<требуетсяRuntime></span><span class="sxs-lookup"><span data-stu-id="0a383-126">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="0a383-127">Указывает, что приложение поддерживает только версию 1.0 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="0a383-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="0a383-128">Приложения, построенные с версией времени выполнения 1.1 или позже, должны использовать \*\* \<поддерживаемыйэлемент>\*\* элемент.</span><span class="sxs-lookup"><span data-stu-id="0a383-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="0a383-129">\<поддерживаетRuntime></span><span class="sxs-lookup"><span data-stu-id="0a383-129">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="0a383-130">Указывает, какие версии среды CLR поддерживает приложение.</span><span class="sxs-lookup"><span data-stu-id="0a383-130">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0a383-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0a383-131">Parent elements</span></span>

|<span data-ttu-id="0a383-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="0a383-132">Element</span></span>|<span data-ttu-id="0a383-133">Описание</span><span class="sxs-lookup"><span data-stu-id="0a383-133">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="0a383-134">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0a383-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0a383-135">Remarks</span><span class="sxs-lookup"><span data-stu-id="0a383-135">Remarks</span></span>

 <span data-ttu-id="0a383-136">\*\* \<Поддерживаемыйэлемент>\*\* элемент должен использоваться всеми приложениями, построенными с использованием версии 1.1 или позже времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="0a383-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="0a383-137">Приложения, созданные для поддержки только версии 1.0 времени выполнения, должны использовать \*\* \<необходимый элементRuntime>.\*\*</span><span class="sxs-lookup"><span data-stu-id="0a383-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="0a383-138">Код запуска приложения, размещенного в Microsoft Internet Explorer, игнорирует \*\* \<запуск>\*\* элементии и его элементы ребенка.</span><span class="sxs-lookup"><span data-stu-id="0a383-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="0a383-139">Атрибут useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="0a383-139">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="0a383-140">Этот атрибут полезен, если приложение использует устаревшие пути активации, такие как [функция CorBindToRuntimeEx,](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)и вы хотите, чтобы эти пути активировали версию 4 CLR вместо более ранней версии, или если ваше приложение построено с помощью .NET Framework 4, но имеет зависимость от сборки смешанного режима, построенной с более ранней версией рамочного .NET.</span><span class="sxs-lookup"><span data-stu-id="0a383-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="0a383-141">В этих сценариях установите атрибут. `true`</span><span class="sxs-lookup"><span data-stu-id="0a383-141">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="0a383-142">Установка атрибута `true` предотвращает загрузку версии CLR 1.1 или CLR 2.0 в тот же процесс, эффективно отключая функцию «в процессе» бок о бок (см. [бок о бок для COM Interop).](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0a383-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="0a383-143">Пример</span><span class="sxs-lookup"><span data-stu-id="0a383-143">Example</span></span>

 <span data-ttu-id="0a383-144">В следующем примере показано, как указать версию времени выполнения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0a383-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0a383-145">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0a383-145">See also</span></span>

- [<span data-ttu-id="0a383-146">Настройки стартапа Схема</span><span class="sxs-lookup"><span data-stu-id="0a383-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0a383-147">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="0a383-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0a383-148">Как: Нанастройка приложения для поддержки .NET Framework 4 или более поздних версий</span><span class="sxs-lookup"><span data-stu-id="0a383-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="0a383-149">[Параллельное выполнение для COM- взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0a383-149">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="0a383-150">Внутрипроцессное параллельное выполнение</span><span class="sxs-lookup"><span data-stu-id="0a383-150">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
