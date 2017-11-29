---
title: "&lt;bindingRedirect&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect
helpviewer_keywords:
- <bindingRedirect> element
- container tags, <bindingRedirect> element
- bindingRedirect element
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3bc8abc019ddb271c8c1246b280be754585bfd61
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltbindingredirectgt-element"></a><span data-ttu-id="8e930-102">&lt;bindingRedirect&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="8e930-102">&lt;bindingRedirect&gt; Element</span></span>
<span data-ttu-id="8e930-103">Перенаправляет одну версию сборки на другую.</span><span class="sxs-lookup"><span data-stu-id="8e930-103">Redirects one assembly version to another.</span></span>  
  
 <span data-ttu-id="8e930-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8e930-104">\<configuration></span></span>  
<span data-ttu-id="8e930-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="8e930-105">\<runtime></span></span>  
<span data-ttu-id="8e930-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="8e930-106">\<assemblyBinding></span></span>  
<span data-ttu-id="8e930-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="8e930-107">\<dependentAssembly></span></span>  
<span data-ttu-id="8e930-108">\<bindingRedirect ></span><span class="sxs-lookup"><span data-stu-id="8e930-108">\<bindingRedirect></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e930-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e930-109">Syntax</span></span>  
  
```xml  
   <bindingRedirect    
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e930-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8e930-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8e930-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8e930-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e930-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8e930-112">Attributes</span></span>  
  
|<span data-ttu-id="8e930-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8e930-113">Attribute</span></span>|<span data-ttu-id="8e930-114">Описание</span><span class="sxs-lookup"><span data-stu-id="8e930-114">Description</span></span>|  
|---------------|-----------------|  
|`oldVersion`|<span data-ttu-id="8e930-115">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="8e930-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="8e930-116">Задает первоначально запрошенную версию сборки.</span><span class="sxs-lookup"><span data-stu-id="8e930-116">Specifies the version of the assembly that was originally requested.</span></span> <span data-ttu-id="8e930-117">Недопустимый формат номера версии сборки *major.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="8e930-117">The format of an assembly version number is *major.minor.build.revision*.</span></span> <span data-ttu-id="8e930-118">Допустимые значения для каждой части этого номера версии — от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="8e930-118">Valid values for each part of this version number are 0 to 65535.</span></span><br /><br /> <span data-ttu-id="8e930-119">Диапазон версий можно также задать в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="8e930-119">You can also specify a range of versions in the following format:</span></span><br /><br /> <span data-ttu-id="8e930-120">*n.n.n.n - n.n.n.n*</span><span class="sxs-lookup"><span data-stu-id="8e930-120">*n.n.n.n - n.n.n.n*</span></span>|  
|`newVersion`|<span data-ttu-id="8e930-121">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="8e930-121">Required attribute.</span></span><br /><br /> <span data-ttu-id="8e930-122">Указывает версию сборки для использования вместо первоначально запрошенной версии в формате: *n.n.n.n*</span><span class="sxs-lookup"><span data-stu-id="8e930-122">Specifies the version of the assembly to use instead of the originally requested version in the format: *n.n.n.n*</span></span><br /><br /> <span data-ttu-id="8e930-123">Это значение может указывать более раннюю версию, чем `oldVersion`.</span><span class="sxs-lookup"><span data-stu-id="8e930-123">This value can specify an earlier version than `oldVersion`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e930-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8e930-124">Child Elements</span></span>  
  
|<span data-ttu-id="8e930-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="8e930-125">Element</span></span>|<span data-ttu-id="8e930-126">Описание</span><span class="sxs-lookup"><span data-stu-id="8e930-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e930-127">Нет</span><span class="sxs-lookup"><span data-stu-id="8e930-127">None</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="8e930-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8e930-128">Parent Elements</span></span>  
  
|<span data-ttu-id="8e930-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="8e930-129">Element</span></span>|<span data-ttu-id="8e930-130">Описание</span><span class="sxs-lookup"><span data-stu-id="8e930-130">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="8e930-131">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="8e930-131">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="8e930-132">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8e930-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="8e930-133">Инкапсулирует политику привязки и расположение каждой сборки.</span><span class="sxs-lookup"><span data-stu-id="8e930-133">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="8e930-134">Для каждой сборки используется только один элемент dependentAssembly.</span><span class="sxs-lookup"><span data-stu-id="8e930-134">Use one dependentAssembly element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="8e930-135">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="8e930-135">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e930-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="8e930-136">Remarks</span></span>  
 <span data-ttu-id="8e930-137">При сборке приложения .NET Framework с использованием сборки со строгим именем приложение во время выполнения по умолчанию будет использовать эту версию сборки, даже если доступна новая версия.</span><span class="sxs-lookup"><span data-stu-id="8e930-137">When you build a .NET Framework application against a strong-named assembly, the application uses that version of the assembly at run time by default, even if a new version is available.</span></span> <span data-ttu-id="8e930-138">Однако приложение можно настроить для выполнения с новой версией сборки.</span><span class="sxs-lookup"><span data-stu-id="8e930-138">However, you can configure the application to run against a newer version of the assembly.</span></span> <span data-ttu-id="8e930-139">Сведения о том, как среда выполнения использует эти файлы для определения нужной версии сборки для использования в разделе [как среда выполнения находит сборки](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="8e930-139">For details on how the runtime uses these files to determine which assembly version to use, see [How the Runtime Locates Assemblies](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="8e930-140">Перенаправление нескольких версий сборок можно выполнить, включив в элемент `bindingRedirect` несколько элементов `dependentAssembly`.</span><span class="sxs-lookup"><span data-stu-id="8e930-140">You can redirect more than one assembly version by including multiple `bindingRedirect` elements in a `dependentAssembly` element.</span></span> <span data-ttu-id="8e930-141">Можно также выполнить перенаправление с более новой версии на более раннюю версию сборки.</span><span class="sxs-lookup"><span data-stu-id="8e930-141">You can also redirect from a newer version to an older version of the assembly.</span></span>  
  
 <span data-ttu-id="8e930-142">Для явного перенаправления привязки сборки в файле конфигурации приложения необходимо разрешение безопасности.</span><span class="sxs-lookup"><span data-stu-id="8e930-142">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="8e930-143">Это относится к перенаправлению как сборок платформы .NET Framework, так и сторонних сборок.</span><span class="sxs-lookup"><span data-stu-id="8e930-143">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="8e930-144">Разрешение можно получить, установив <xref:System.Security.Permissions.SecurityPermissionFlag> флаг <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="8e930-144">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="8e930-145">Дополнительные сведения см. в разделе [разрешение безопасности перенаправления привязки сборок](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="8e930-145">For more information, see [Assembly Binding Redirection Security Permission](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e930-146">Пример</span><span class="sxs-lookup"><span data-stu-id="8e930-146">Example</span></span>  
 <span data-ttu-id="8e930-147">В следующем примере показан способ перенаправления одной версии сборки на другую.</span><span class="sxs-lookup"><span data-stu-id="8e930-147">The following example shows how to redirect one assembly version to another.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8e930-148">См. также</span><span class="sxs-lookup"><span data-stu-id="8e930-148">See Also</span></span>  
 [<span data-ttu-id="8e930-149">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="8e930-149">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="8e930-150">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="8e930-150">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="8e930-151">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="8e930-151">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
