---
title: Элемент <requiredRuntime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: fe96673b95f48cb75d36662a680bf56a59363f9f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697487"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="aa34e-102">\<requiredRuntime > элемент</span><span class="sxs-lookup"><span data-stu-id="aa34e-102">\<requiredRuntime> element</span></span>

<span data-ttu-id="aa34e-103">Указывает, что приложение поддерживает только версию 1.0 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="aa34e-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="aa34e-104">Этот элемент является устаревшим и больше не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="aa34e-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="aa34e-105">Вместо этого следует использовать элемент [`supportedRuntime`](supportedruntime-element.md) .</span><span class="sxs-lookup"><span data-stu-id="aa34e-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

[<span data-ttu-id="aa34e-106"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="aa34e-106">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="aa34e-107">&nbsp;&nbsp;[ **\<запуска >** ](startup-element.md)</span><span class="sxs-lookup"><span data-stu-id="aa34e-107">&nbsp;&nbsp;[**\<startup>**](startup-element.md)</span></span>  
<span data-ttu-id="aa34e-108">&nbsp;&nbsp;&nbsp;&nbsp; **\<requiredRuntime >**</span><span class="sxs-lookup"><span data-stu-id="aa34e-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="aa34e-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa34e-109">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aa34e-110">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa34e-110">Attributes and elements</span></span>

<span data-ttu-id="aa34e-111">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aa34e-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="aa34e-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa34e-112">Attributes</span></span>

|<span data-ttu-id="aa34e-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="aa34e-113">Attribute</span></span>|<span data-ttu-id="aa34e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="aa34e-114">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="aa34e-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="aa34e-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="aa34e-116">Строковое значение, указывающее версию .NET Framework, которую поддерживает это приложение.</span><span class="sxs-lookup"><span data-stu-id="aa34e-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="aa34e-117">Строковое значение должно соответствовать имени каталога, обнаруженному в корне установки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="aa34e-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="aa34e-118">Содержимое строкового значения не анализируется.</span><span class="sxs-lookup"><span data-stu-id="aa34e-118">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="aa34e-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="aa34e-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="aa34e-120">Указывает, будет ли код запуска среды выполнения выполнять поиск в реестре для определения версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="aa34e-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="aa34e-121">атрибут безопасный режим</span><span class="sxs-lookup"><span data-stu-id="aa34e-121">safemode attribute</span></span>

|<span data-ttu-id="aa34e-122">Значение</span><span class="sxs-lookup"><span data-stu-id="aa34e-122">Value</span></span>|<span data-ttu-id="aa34e-123">Описание</span><span class="sxs-lookup"><span data-stu-id="aa34e-123">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="aa34e-124">Код запуска среды выполнения выполняет поиск в реестре.</span><span class="sxs-lookup"><span data-stu-id="aa34e-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="aa34e-125">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aa34e-125">This is the default value.</span></span>|
|`true`|<span data-ttu-id="aa34e-126">Код запуска среды выполнения не выполняет поиск в реестре.</span><span class="sxs-lookup"><span data-stu-id="aa34e-126">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="aa34e-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aa34e-127">Child elements</span></span>

<span data-ttu-id="aa34e-128">Нет</span><span class="sxs-lookup"><span data-stu-id="aa34e-128">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="aa34e-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aa34e-129">Parent elements</span></span>

|<span data-ttu-id="aa34e-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="aa34e-130">Element</span></span>|<span data-ttu-id="aa34e-131">Описание</span><span class="sxs-lookup"><span data-stu-id="aa34e-131">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="aa34e-132">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="aa34e-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="aa34e-133">Содержит элемент `<requiredRuntime>`.</span><span class="sxs-lookup"><span data-stu-id="aa34e-133">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aa34e-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="aa34e-134">Remarks</span></span>
 <span data-ttu-id="aa34e-135">Приложения, созданные для поддержки только версии 1,0 среды выполнения, должны использовать элемент `<requiredRuntime>`.</span><span class="sxs-lookup"><span data-stu-id="aa34e-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="aa34e-136">Приложения, созданные с помощью версии 1,1 или более поздней версии среды выполнения, должны использовать элемент `<supportedRuntime>`.</span><span class="sxs-lookup"><span data-stu-id="aa34e-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="aa34e-137">При использовании функции [корбиндторунтимебикфг](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) для указания файла конфигурации необходимо использовать элемент `<requiredRuntime>` для всех версий среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="aa34e-137">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="aa34e-138">Элемент `<supportedRuntime>` игнорируется при использовании [корбиндторунтимебикфг](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="aa34e-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="aa34e-139">Строка атрибута `version` должна соответствовать имени папки установки для указанной версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="aa34e-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="aa34e-140">Эта строка не интерпретируется.</span><span class="sxs-lookup"><span data-stu-id="aa34e-140">This string is not interpreted.</span></span> <span data-ttu-id="aa34e-141">Если код запуска среды выполнения не находит совпадающую папку, среда выполнения не загружается; код запуска отображает сообщение об ошибке и завершает работу.</span><span class="sxs-lookup"><span data-stu-id="aa34e-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="aa34e-142">Код запуска для приложения, размещенного в Microsoft Internet Explorer, игнорирует элемент `<requiredRuntime>`.</span><span class="sxs-lookup"><span data-stu-id="aa34e-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="aa34e-143">Пример</span><span class="sxs-lookup"><span data-stu-id="aa34e-143">Example</span></span>

<span data-ttu-id="aa34e-144">В следующем примере показано, как указать версию среды выполнения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="aa34e-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="aa34e-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="aa34e-145">See also</span></span>

- [<span data-ttu-id="aa34e-146">Схема параметров запуска</span><span class="sxs-lookup"><span data-stu-id="aa34e-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="aa34e-147">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="aa34e-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="aa34e-148">Как настроить приложение для поддержки .NET Framework 4 или более поздних версий</span><span class="sxs-lookup"><span data-stu-id="aa34e-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
