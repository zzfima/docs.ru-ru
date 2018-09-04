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
ms.openlocfilehash: ac1e1f7bc36d8d2b12b99de2794bb0ba31ddbd7a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518651"
---
# <a name="ltrequiredruntimegt-element"></a><span data-ttu-id="cf5f9-102">&lt;requiredRuntime&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="cf5f9-102">&lt;requiredRuntime&gt; Element</span></span>
<span data-ttu-id="cf5f9-103">Указывает, что приложение поддерживает только версию 1.0 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="cf5f9-104">Этот элемент устарел и больше не используется.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="cf5f9-105">[ `supportedRuntime` ](supportedruntime-element.md) Элемента, которые должны использоваться вместо нее.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>
  
 <span data-ttu-id="cf5f9-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cf5f9-106">\<configuration></span></span>  
<span data-ttu-id="cf5f9-107">\<Startup ></span><span class="sxs-lookup"><span data-stu-id="cf5f9-107">\<startup></span></span>  
<span data-ttu-id="cf5f9-108">\<requiredRuntime ></span><span class="sxs-lookup"><span data-stu-id="cf5f9-108">\<requiredRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf5f9-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf5f9-109">Syntax</span></span>  
  
```xml  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf5f9-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cf5f9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cf5f9-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf5f9-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cf5f9-112">Attributes</span></span>  
  
|<span data-ttu-id="cf5f9-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cf5f9-113">Attribute</span></span>|<span data-ttu-id="cf5f9-114">Описание</span><span class="sxs-lookup"><span data-stu-id="cf5f9-114">Description</span></span>|  
|---------------|-----------------|  
|`version`|<span data-ttu-id="cf5f9-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="cf5f9-116">Строковое значение, указывающее версию платформы .NET Framework, которая поддерживается данным приложением.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="cf5f9-117">Строковое значение должно соответствовать имени каталога, найден в корневом каталоге установки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="cf5f9-118">Содержимое строкового значения не анализируется.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-118">The contents of the string value are not parsed.</span></span>|  
|`safemode`|<span data-ttu-id="cf5f9-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="cf5f9-120">Указывает, выполняет ли код запуска среды выполнения реестра для определения версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|  
  
## <a name="safemode-attribute"></a><span data-ttu-id="cf5f9-121">безопасный режим атрибут</span><span class="sxs-lookup"><span data-stu-id="cf5f9-121">safemode Attribute</span></span>  
  
|<span data-ttu-id="cf5f9-122">Значение</span><span class="sxs-lookup"><span data-stu-id="cf5f9-122">Value</span></span>|<span data-ttu-id="cf5f9-123">Описание</span><span class="sxs-lookup"><span data-stu-id="cf5f9-123">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="cf5f9-124">Код запуска среды выполнения ищет в реестре.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="cf5f9-125">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-125">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="cf5f9-126">Код запуска среды выполнения не выглядит в реестре.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-126">The runtime startup code does not look in the registry.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cf5f9-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cf5f9-127">Child Elements</span></span>  
 <span data-ttu-id="cf5f9-128">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cf5f9-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cf5f9-129">Parent Elements</span></span>  
  
|<span data-ttu-id="cf5f9-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="cf5f9-130">Element</span></span>|<span data-ttu-id="cf5f9-131">Описание</span><span class="sxs-lookup"><span data-stu-id="cf5f9-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cf5f9-132">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`startup`|<span data-ttu-id="cf5f9-133">Содержит `<requiredRuntime>` элемент.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-133">Contains the `<requiredRuntime>` element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf5f9-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="cf5f9-134">Remarks</span></span>  
 <span data-ttu-id="cf5f9-135">Приложения, созданные для поддержки только версии 1.0 среды выполнения, должны использовать `<requiredRuntime>` элемент.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="cf5f9-136">Приложения, созданные с помощью версии 1.1 или более поздней версии среды выполнения, должны использовать `<supportedRuntime>` элемент.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf5f9-137">Если вы используете [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) функции для указания файла конфигурации, необходимо использовать `<requiredRuntime>` элемент для всех версий среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-137">If you use the [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="cf5f9-138">`<supportedRuntime>` Элемент учитывается при использовании [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="cf5f9-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
 <span data-ttu-id="cf5f9-139">`version` Строки атрибута должно соответствовать имени папки установки для указанной версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="cf5f9-140">Эта строка не интерпретируется.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-140">This string is not interpreted.</span></span> <span data-ttu-id="cf5f9-141">Если код запуска среды выполнения не находит соответствующей папки, среда выполнения не загружается; код запуска, отобразится сообщение об ошибке и завершает работу.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf5f9-142">Код запуска для приложения, размещенного в Microsoft Internet Explorer не учитывает `<requiredRuntime>` элемент.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf5f9-143">Пример</span><span class="sxs-lookup"><span data-stu-id="cf5f9-143">Example</span></span>  
 <span data-ttu-id="cf5f9-144">Приведенный ниже показано, как указать версию среды выполнения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cf5f9-144">The following example shows how to specify the runtime version in a configuration file.</span></span>  
  
```xml  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf5f9-145">См. также</span><span class="sxs-lookup"><span data-stu-id="cf5f9-145">See Also</span></span>  
 [<span data-ttu-id="cf5f9-146">Схема параметров запуска</span><span class="sxs-lookup"><span data-stu-id="cf5f9-146">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="cf5f9-147">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="cf5f9-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="cf5f9-148">\<PaveOver> Указание используемой версии среды выполнения</span><span class="sxs-lookup"><span data-stu-id="cf5f9-148">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](https://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
