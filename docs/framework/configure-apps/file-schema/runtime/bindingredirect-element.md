---
title: <bindingRedirect> Элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect
helpviewer_keywords:
- <bindingRedirect> element
- container tags, <bindingRedirect> element
- bindingRedirect element
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
ms.openlocfilehash: dda99bb4b96efbdd274e24e7cd548e4ed4df8b66
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185917"
---
# <a name="bindingredirect-element"></a><span data-ttu-id="1ae22-102">\<bindingRedirect > элемент</span><span class="sxs-lookup"><span data-stu-id="1ae22-102">\<bindingRedirect> Element</span></span>
<span data-ttu-id="1ae22-103">Перенаправляет одну версию сборки на другую.</span><span class="sxs-lookup"><span data-stu-id="1ae22-103">Redirects one assembly version to another.</span></span>  
  
 <span data-ttu-id="1ae22-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1ae22-104">\<configuration></span></span>  
<span data-ttu-id="1ae22-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="1ae22-105">\<runtime></span></span>  
<span data-ttu-id="1ae22-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="1ae22-106">\<assemblyBinding></span></span>  
<span data-ttu-id="1ae22-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="1ae22-107">\<dependentAssembly></span></span>  
<span data-ttu-id="1ae22-108">\<bindingRedirect></span><span class="sxs-lookup"><span data-stu-id="1ae22-108">\<bindingRedirect></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ae22-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ae22-109">Syntax</span></span>  
  
```xml  
   <bindingRedirect    
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ae22-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1ae22-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1ae22-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1ae22-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ae22-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1ae22-112">Attributes</span></span>  
  
|<span data-ttu-id="1ae22-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1ae22-113">Attribute</span></span>|<span data-ttu-id="1ae22-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1ae22-114">Description</span></span>|  
|---------------|-----------------|  
|`oldVersion`|<span data-ttu-id="1ae22-115">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="1ae22-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="1ae22-116">Задает первоначально запрошенную версию сборки.</span><span class="sxs-lookup"><span data-stu-id="1ae22-116">Specifies the version of the assembly that was originally requested.</span></span> <span data-ttu-id="1ae22-117">Формат номера версии сборки *major.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="1ae22-117">The format of an assembly version number is *major.minor.build.revision*.</span></span> <span data-ttu-id="1ae22-118">Допустимые значения для каждой части этого номера версии — от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="1ae22-118">Valid values for each part of this version number are 0 to 65535.</span></span><br /><br /> <span data-ttu-id="1ae22-119">Диапазон версий можно также задать в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="1ae22-119">You can also specify a range of versions in the following format:</span></span><br /><br /> *<span data-ttu-id="1ae22-120">n.n.n.n - n.n.n.n</span><span class="sxs-lookup"><span data-stu-id="1ae22-120">n.n.n.n - n.n.n.n</span></span>*|  
|`newVersion`|<span data-ttu-id="1ae22-121">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="1ae22-121">Required attribute.</span></span><br /><br /> <span data-ttu-id="1ae22-122">Указывает номер версии сборки для использования вместо первоначально запрошенной версии в формате: *n.n.n.n*</span><span class="sxs-lookup"><span data-stu-id="1ae22-122">Specifies the version of the assembly to use instead of the originally requested version in the format: *n.n.n.n*</span></span><br /><br /> <span data-ttu-id="1ae22-123">Это значение может указывать более раннюю версию, чем `oldVersion`.</span><span class="sxs-lookup"><span data-stu-id="1ae22-123">This value can specify an earlier version than `oldVersion`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ae22-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1ae22-124">Child Elements</span></span>  
  
|<span data-ttu-id="1ae22-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="1ae22-125">Element</span></span>|<span data-ttu-id="1ae22-126">Описание</span><span class="sxs-lookup"><span data-stu-id="1ae22-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1ae22-127">Нет</span><span class="sxs-lookup"><span data-stu-id="1ae22-127">None</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="1ae22-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1ae22-128">Parent Elements</span></span>  
  
|<span data-ttu-id="1ae22-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="1ae22-129">Element</span></span>|<span data-ttu-id="1ae22-130">Описание</span><span class="sxs-lookup"><span data-stu-id="1ae22-130">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="1ae22-131">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="1ae22-131">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="1ae22-132">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1ae22-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="1ae22-133">Инкапсулирует политику привязки и расположение каждой сборки.</span><span class="sxs-lookup"><span data-stu-id="1ae22-133">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="1ae22-134">Для каждой сборки используется только один элемент dependentAssembly.</span><span class="sxs-lookup"><span data-stu-id="1ae22-134">Use one dependentAssembly element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="1ae22-135">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="1ae22-135">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ae22-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="1ae22-136">Remarks</span></span>  
 <span data-ttu-id="1ae22-137">При сборке приложения .NET Framework с использованием сборки со строгим именем приложение во время выполнения по умолчанию будет использовать эту версию сборки, даже если доступна новая версия.</span><span class="sxs-lookup"><span data-stu-id="1ae22-137">When you build a .NET Framework application against a strong-named assembly, the application uses that version of the assembly at run time by default, even if a new version is available.</span></span> <span data-ttu-id="1ae22-138">Однако приложение можно настроить для выполнения с новой версией сборки.</span><span class="sxs-lookup"><span data-stu-id="1ae22-138">However, you can configure the application to run against a newer version of the assembly.</span></span> <span data-ttu-id="1ae22-139">Дополнительные сведения о том, как среда выполнения использует эти файлы для определения нужной версии сборки для использования, см. в разделе [Обнаружение сборок в среде выполнения](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="1ae22-139">For details on how the runtime uses these files to determine which assembly version to use, see [How the Runtime Locates Assemblies](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="1ae22-140">Перенаправление нескольких версий сборок можно выполнить, включив в элемент `bindingRedirect` несколько элементов `dependentAssembly`.</span><span class="sxs-lookup"><span data-stu-id="1ae22-140">You can redirect more than one assembly version by including multiple `bindingRedirect` elements in a `dependentAssembly` element.</span></span> <span data-ttu-id="1ae22-141">Можно также выполнить перенаправление с более новой версии на более раннюю версию сборки.</span><span class="sxs-lookup"><span data-stu-id="1ae22-141">You can also redirect from a newer version to an older version of the assembly.</span></span>  
  
 <span data-ttu-id="1ae22-142">Для явного перенаправления привязки сборки в файле конфигурации приложения необходимо разрешение безопасности.</span><span class="sxs-lookup"><span data-stu-id="1ae22-142">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="1ae22-143">Это относится к перенаправлению как сборок платформы .NET Framework, так и сторонних сборок.</span><span class="sxs-lookup"><span data-stu-id="1ae22-143">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="1ae22-144">Разрешение, задав <xref:System.Security.Permissions.SecurityPermissionFlag> флаг <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="1ae22-144">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="1ae22-145">Дополнительные сведения см. в разделе [разрешение безопасности перенаправления привязки сборки](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="1ae22-145">For more information, see [Assembly Binding Redirection Security Permission](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ae22-146">Пример</span><span class="sxs-lookup"><span data-stu-id="1ae22-146">Example</span></span>  
 <span data-ttu-id="1ae22-147">В следующем примере показан способ перенаправления одной версии сборки на другую.</span><span class="sxs-lookup"><span data-stu-id="1ae22-147">The following example shows how to redirect one assembly version to another.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1ae22-148">См. также</span><span class="sxs-lookup"><span data-stu-id="1ae22-148">See also</span></span>

- [<span data-ttu-id="1ae22-149">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="1ae22-149">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="1ae22-150">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="1ae22-150">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="1ae22-151">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="1ae22-151">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
