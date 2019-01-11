---
title: '&lt;requiredRuntime&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: 66de3e30ce862cd317e80ea267bf22ce728aca82
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222133"
---
# <a name="ltrequiredruntimegt-element"></a><span data-ttu-id="ceb90-102">&lt;requiredRuntime&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="ceb90-102">&lt;requiredRuntime&gt; element</span></span>

<span data-ttu-id="ceb90-103">Указывает, что приложение поддерживает только версию 1.0 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ceb90-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="ceb90-104">Этот элемент устарел и больше не используется.</span><span class="sxs-lookup"><span data-stu-id="ceb90-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="ceb90-105">[ `supportedRuntime` ](supportedruntime-element.md) Элемента, которые должны использоваться вместо нее.</span><span class="sxs-lookup"><span data-stu-id="ceb90-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

<span data-ttu-id="ceb90-106">\<Конфигурация > \<startup > \<requiredRuntime ></span><span class="sxs-lookup"><span data-stu-id="ceb90-106">\<configuration> \<startup> \<requiredRuntime></span></span>

## <a name="syntax"></a><span data-ttu-id="ceb90-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ceb90-107">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ceb90-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="ceb90-108">Attributes and elements</span></span>

<span data-ttu-id="ceb90-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ceb90-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ceb90-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ceb90-110">Attributes</span></span>

|<span data-ttu-id="ceb90-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ceb90-111">Attribute</span></span>|<span data-ttu-id="ceb90-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ceb90-112">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="ceb90-113">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ceb90-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ceb90-114">Строковое значение, указывающее версию платформы .NET Framework, которая поддерживается данным приложением.</span><span class="sxs-lookup"><span data-stu-id="ceb90-114">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="ceb90-115">Строковое значение должно соответствовать имени каталога, найден в корневом каталоге установки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ceb90-115">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="ceb90-116">Содержимое строкового значения не анализируется.</span><span class="sxs-lookup"><span data-stu-id="ceb90-116">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="ceb90-117">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ceb90-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ceb90-118">Указывает, выполняет ли код запуска среды выполнения реестра для определения версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ceb90-118">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="ceb90-119">атрибут безопасный режим</span><span class="sxs-lookup"><span data-stu-id="ceb90-119">safemode attribute</span></span>

|<span data-ttu-id="ceb90-120">Значение</span><span class="sxs-lookup"><span data-stu-id="ceb90-120">Value</span></span>|<span data-ttu-id="ceb90-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="ceb90-121">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="ceb90-122">Код запуска среды выполнения ищет в реестре.</span><span class="sxs-lookup"><span data-stu-id="ceb90-122">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="ceb90-123">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ceb90-123">This is the default value.</span></span>|
|`true`|<span data-ttu-id="ceb90-124">Код запуска среды выполнения не выглядит в реестре.</span><span class="sxs-lookup"><span data-stu-id="ceb90-124">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ceb90-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ceb90-125">Child elements</span></span>

<span data-ttu-id="ceb90-126">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ceb90-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ceb90-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ceb90-127">Parent elements</span></span>

|<span data-ttu-id="ceb90-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="ceb90-128">Element</span></span>|<span data-ttu-id="ceb90-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="ceb90-129">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="ceb90-130">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ceb90-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="ceb90-131">Содержит `<requiredRuntime>` элемент.</span><span class="sxs-lookup"><span data-stu-id="ceb90-131">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ceb90-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="ceb90-132">Remarks</span></span>
 <span data-ttu-id="ceb90-133">Приложения, созданные для поддержки только версии 1.0 среды выполнения, должны использовать `<requiredRuntime>` элемент.</span><span class="sxs-lookup"><span data-stu-id="ceb90-133">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="ceb90-134">Приложения, созданные с помощью версии 1.1 или более поздней версии среды выполнения, должны использовать `<supportedRuntime>` элемент.</span><span class="sxs-lookup"><span data-stu-id="ceb90-134">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="ceb90-135">Если вы используете [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) функции для указания файла конфигурации, необходимо использовать `<requiredRuntime>` элемент для всех версий среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ceb90-135">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="ceb90-136">`<supportedRuntime>` Элемент учитывается при использовании [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="ceb90-136">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="ceb90-137">`version` Строки атрибута должно соответствовать имени папки установки для указанной версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ceb90-137">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="ceb90-138">Эта строка не интерпретируется.</span><span class="sxs-lookup"><span data-stu-id="ceb90-138">This string is not interpreted.</span></span> <span data-ttu-id="ceb90-139">Если код запуска среды выполнения не находит соответствующей папки, среда выполнения не загружается; код запуска, отобразится сообщение об ошибке и завершает работу.</span><span class="sxs-lookup"><span data-stu-id="ceb90-139">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="ceb90-140">Код запуска для приложения, размещенного в Microsoft Internet Explorer не учитывает `<requiredRuntime>` элемент.</span><span class="sxs-lookup"><span data-stu-id="ceb90-140">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="ceb90-141">Пример</span><span class="sxs-lookup"><span data-stu-id="ceb90-141">Example</span></span>

<span data-ttu-id="ceb90-142">Приведенный ниже показано, как указать версию среды выполнения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ceb90-142">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="ceb90-143">См. также</span><span class="sxs-lookup"><span data-stu-id="ceb90-143">See also</span></span>

- [<span data-ttu-id="ceb90-144">Схема параметров запуска</span><span class="sxs-lookup"><span data-stu-id="ceb90-144">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ceb90-145">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="ceb90-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ceb90-146">Практическое руководство. Настройка приложения для поддержки .NET Framework 4 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="ceb90-146">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)