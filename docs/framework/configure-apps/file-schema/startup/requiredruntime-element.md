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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 184547dd47e728f17f28105e74b2ca67c1436efc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749986"
---
# <a name="ltrequiredruntimegt-element"></a><span data-ttu-id="ffd89-102">&lt;requiredRuntime&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="ffd89-102">&lt;requiredRuntime&gt; Element</span></span>
<span data-ttu-id="ffd89-103">Указывает, что приложение поддерживает только версию 1.0 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ffd89-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="ffd89-104">Этот элемент устарел и больше не может использоваться.</span><span class="sxs-lookup"><span data-stu-id="ffd89-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="ffd89-105">[ `supportedRuntime` ](supportedruntime-element.md) Следует использовать элемент.</span><span class="sxs-lookup"><span data-stu-id="ffd89-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>
  
 <span data-ttu-id="ffd89-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ffd89-106">\<configuration></span></span>  
<span data-ttu-id="ffd89-107">\<При запуске ></span><span class="sxs-lookup"><span data-stu-id="ffd89-107">\<startup></span></span>  
<span data-ttu-id="ffd89-108">\<requiredRuntime ></span><span class="sxs-lookup"><span data-stu-id="ffd89-108">\<requiredRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffd89-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ffd89-109">Syntax</span></span>  
  
```xml  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ffd89-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ffd89-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ffd89-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ffd89-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ffd89-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ffd89-112">Attributes</span></span>  
  
|<span data-ttu-id="ffd89-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ffd89-113">Attribute</span></span>|<span data-ttu-id="ffd89-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ffd89-114">Description</span></span>|  
|---------------|-----------------|  
|`version`|<span data-ttu-id="ffd89-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ffd89-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ffd89-116">Строковое значение, указывающее версию платформы .NET Framework, поддерживаемую этим приложением.</span><span class="sxs-lookup"><span data-stu-id="ffd89-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="ffd89-117">Строковое значение должно соответствовать имени каталога, находятся в папке установки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ffd89-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="ffd89-118">Содержимое строкового значения не анализируется.</span><span class="sxs-lookup"><span data-stu-id="ffd89-118">The contents of the string value are not parsed.</span></span>|  
|`safemode`|<span data-ttu-id="ffd89-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ffd89-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ffd89-120">Указывает, является ли код запуска среды выполнения ищет в реестре для определения версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ffd89-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|  
  
## <a name="safemode-attribute"></a><span data-ttu-id="ffd89-121">безопасный режим атрибута</span><span class="sxs-lookup"><span data-stu-id="ffd89-121">safemode Attribute</span></span>  
  
|<span data-ttu-id="ffd89-122">Значение</span><span class="sxs-lookup"><span data-stu-id="ffd89-122">Value</span></span>|<span data-ttu-id="ffd89-123">Описание</span><span class="sxs-lookup"><span data-stu-id="ffd89-123">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="ffd89-124">Код запуска среды выполнения ищет в реестре.</span><span class="sxs-lookup"><span data-stu-id="ffd89-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="ffd89-125">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ffd89-125">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="ffd89-126">Код запуска среды выполнения не проверяет реестр.</span><span class="sxs-lookup"><span data-stu-id="ffd89-126">The runtime startup code does not look in the registry.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ffd89-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ffd89-127">Child Elements</span></span>  
 <span data-ttu-id="ffd89-128">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ffd89-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ffd89-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ffd89-129">Parent Elements</span></span>  
  
|<span data-ttu-id="ffd89-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="ffd89-130">Element</span></span>|<span data-ttu-id="ffd89-131">Описание</span><span class="sxs-lookup"><span data-stu-id="ffd89-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ffd89-132">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ffd89-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`startup`|<span data-ttu-id="ffd89-133">Содержит `<requiredRuntime>` элемента.</span><span class="sxs-lookup"><span data-stu-id="ffd89-133">Contains the `<requiredRuntime>` element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffd89-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="ffd89-134">Remarks</span></span>  
 <span data-ttu-id="ffd89-135">Приложения, созданные для поддержки только версии 1.0 среды выполнения, должны использовать `<requiredRuntime>` элемент.</span><span class="sxs-lookup"><span data-stu-id="ffd89-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="ffd89-136">Приложения, построенные с помощью версии 1.1 или более поздней версии среды выполнения должны использовать `<supportedRuntime>` элемент.</span><span class="sxs-lookup"><span data-stu-id="ffd89-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffd89-137">Если вы используете [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) для указания файла конфигурации, необходимо использовать `<requiredRuntime>` элемент для всех версий среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ffd89-137">If you use the [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="ffd89-138">`<supportedRuntime>` Элемент игнорируется при использовании [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="ffd89-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
 <span data-ttu-id="ffd89-139">`version` Строки атрибута должно соответствовать имени папки установки для данной версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ffd89-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="ffd89-140">Эта строка не интерпретируется.</span><span class="sxs-lookup"><span data-stu-id="ffd89-140">This string is not interpreted.</span></span> <span data-ttu-id="ffd89-141">Если код запуска среды выполнения не находит соответствующей папки, среда выполнения не загружается; код запуска отобразится сообщение об ошибке и завершает работу.</span><span class="sxs-lookup"><span data-stu-id="ffd89-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffd89-142">Код запуска для приложения, размещенного в Internet Explorer не учитывает `<requiredRuntime>` элемента.</span><span class="sxs-lookup"><span data-stu-id="ffd89-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffd89-143">Пример</span><span class="sxs-lookup"><span data-stu-id="ffd89-143">Example</span></span>  
 <span data-ttu-id="ffd89-144">Приведенный ниже показано, как указать версию среды выполнения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ffd89-144">The following example shows how to specify the runtime version in a configuration file.</span></span>  
  
```xml  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ffd89-145">См. также</span><span class="sxs-lookup"><span data-stu-id="ffd89-145">See Also</span></span>  
 [<span data-ttu-id="ffd89-146">Схема параметров запуска</span><span class="sxs-lookup"><span data-stu-id="ffd89-146">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="ffd89-147">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="ffd89-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="ffd89-148">\<PaveOver> Указание используемой версии среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ffd89-148">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
