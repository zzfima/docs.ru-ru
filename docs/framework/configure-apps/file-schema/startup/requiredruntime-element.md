---
title: "&lt;requiredRuntime&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 2e864eec2ddf51d5cc88110654f6c23f146938d5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="ltrequiredruntimegt-element"></a><span data-ttu-id="fce5a-102">&lt;requiredRuntime&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="fce5a-102">&lt;requiredRuntime&gt; Element</span></span>
<span data-ttu-id="fce5a-103">Указывает, что приложение поддерживает только версию 1.0 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="fce5a-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="fce5a-104">Этот элемент устарел и больше не может использоваться.</span><span class="sxs-lookup"><span data-stu-id="fce5a-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="fce5a-105">[ `supportedRuntime` ](supportedruntime-element.md) Следует использовать элемент.</span><span class="sxs-lookup"><span data-stu-id="fce5a-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>
  
 <span data-ttu-id="fce5a-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fce5a-106">\<configuration></span></span>  
<span data-ttu-id="fce5a-107">\<При запуске ></span><span class="sxs-lookup"><span data-stu-id="fce5a-107">\<startup></span></span>  
<span data-ttu-id="fce5a-108">\<requiredRuntime ></span><span class="sxs-lookup"><span data-stu-id="fce5a-108">\<requiredRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fce5a-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fce5a-109">Syntax</span></span>  
  
```xml  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fce5a-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fce5a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fce5a-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fce5a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fce5a-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fce5a-112">Attributes</span></span>  
  
|<span data-ttu-id="fce5a-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fce5a-113">Attribute</span></span>|<span data-ttu-id="fce5a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="fce5a-114">Description</span></span>|  
|---------------|-----------------|  
|`version`|<span data-ttu-id="fce5a-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="fce5a-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="fce5a-116">Строковое значение, указывающее версию платформы .NET Framework, поддерживаемую этим приложением.</span><span class="sxs-lookup"><span data-stu-id="fce5a-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="fce5a-117">Строковое значение должно соответствовать имени каталога, находятся в папке установки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fce5a-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="fce5a-118">Содержимое строкового значения не анализируется.</span><span class="sxs-lookup"><span data-stu-id="fce5a-118">The contents of the string value are not parsed.</span></span>|  
|`safemode`|<span data-ttu-id="fce5a-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="fce5a-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="fce5a-120">Указывает, является ли код запуска среды выполнения ищет в реестре для определения версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="fce5a-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|  
  
## <a name="safemode-attribute"></a><span data-ttu-id="fce5a-121">безопасный режим атрибута</span><span class="sxs-lookup"><span data-stu-id="fce5a-121">safemode Attribute</span></span>  
  
|<span data-ttu-id="fce5a-122">Значение</span><span class="sxs-lookup"><span data-stu-id="fce5a-122">Value</span></span>|<span data-ttu-id="fce5a-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="fce5a-123">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="fce5a-124">Код запуска среды выполнения ищет в реестре.</span><span class="sxs-lookup"><span data-stu-id="fce5a-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="fce5a-125">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fce5a-125">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="fce5a-126">Код запуска среды выполнения не проверяет реестр.</span><span class="sxs-lookup"><span data-stu-id="fce5a-126">The runtime startup code does not look in the registry.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fce5a-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fce5a-127">Child Elements</span></span>  
 <span data-ttu-id="fce5a-128">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fce5a-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fce5a-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fce5a-129">Parent Elements</span></span>  
  
|<span data-ttu-id="fce5a-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="fce5a-130">Element</span></span>|<span data-ttu-id="fce5a-131">Описание:</span><span class="sxs-lookup"><span data-stu-id="fce5a-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fce5a-132">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fce5a-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`startup`|<span data-ttu-id="fce5a-133">Содержит `<requiredRuntime>` элемента.</span><span class="sxs-lookup"><span data-stu-id="fce5a-133">Contains the `<requiredRuntime>` element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fce5a-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="fce5a-134">Remarks</span></span>  
 <span data-ttu-id="fce5a-135">Приложения, созданные для поддержки только версии 1.0 среды выполнения, должны использовать `<requiredRuntime>` элемент.</span><span class="sxs-lookup"><span data-stu-id="fce5a-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="fce5a-136">Приложения, построенные с помощью версии 1.1 или более поздней версии среды выполнения должны использовать `<supportedRuntime>` элемент.</span><span class="sxs-lookup"><span data-stu-id="fce5a-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fce5a-137">Если вы используете [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) для указания файла конфигурации, необходимо использовать `<requiredRuntime>` элемент для всех версий среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="fce5a-137">If you use the [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="fce5a-138">`<supportedRuntime>` Элемент игнорируется при использовании [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="fce5a-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
 <span data-ttu-id="fce5a-139">`version` Строки атрибута должно соответствовать имени папки установки для данной версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fce5a-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="fce5a-140">Эта строка не интерпретируется.</span><span class="sxs-lookup"><span data-stu-id="fce5a-140">This string is not interpreted.</span></span> <span data-ttu-id="fce5a-141">Если код запуска среды выполнения не находит соответствующей папки, среда выполнения не загружается; код запуска отобразится сообщение об ошибке и завершает работу.</span><span class="sxs-lookup"><span data-stu-id="fce5a-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fce5a-142">Код запуска для приложения, размещенного в Internet Explorer не учитывает `<requiredRuntime>` элемента.</span><span class="sxs-lookup"><span data-stu-id="fce5a-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fce5a-143">Пример</span><span class="sxs-lookup"><span data-stu-id="fce5a-143">Example</span></span>  
 <span data-ttu-id="fce5a-144">Приведенный ниже показано, как указать версию среды выполнения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fce5a-144">The following example shows how to specify the runtime version in a configuration file.</span></span>  
  
```xml  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fce5a-145">См. также</span><span class="sxs-lookup"><span data-stu-id="fce5a-145">See Also</span></span>  
 [<span data-ttu-id="fce5a-146">Схема параметров запуска</span><span class="sxs-lookup"><span data-stu-id="fce5a-146">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="fce5a-147">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="fce5a-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="fce5a-148">\<PaveOver> Указание используемой версии среды выполнения</span><span class="sxs-lookup"><span data-stu-id="fce5a-148">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
