---
title: Элемент <bindingRedirect>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect
helpviewer_keywords:
- <bindingRedirect> element
- container tags, <bindingRedirect> element
- bindingRedirect element
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
ms.openlocfilehash: d96585b397f75dcb9fac7e7fce93799cc95e7c6c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154300"
---
# <a name="bindingredirect-element"></a><span data-ttu-id="a5ca3-102">\<связывающаярепрямая> элемент</span><span class="sxs-lookup"><span data-stu-id="a5ca3-102">\<bindingRedirect> Element</span></span>
<span data-ttu-id="a5ca3-103">Перенаправляет одну версию сборки на другую.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-103">Redirects one assembly version to another.</span></span>  
  
<span data-ttu-id="a5ca3-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a5ca3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a5ca3-105">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="a5ca3-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="a5ca3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<сборкаОбязательная>**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="a5ca3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="a5ca3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<зависимаясборка>**](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="a5ca3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="a5ca3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<связывающаяРепрямая>**</span><span class="sxs-lookup"><span data-stu-id="a5ca3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bindingRedirect>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5ca3-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5ca3-109">Syntax</span></span>  
  
```xml  
   <bindingRedirect
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5ca3-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a5ca3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a5ca3-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5ca3-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a5ca3-112">Attributes</span></span>  
  
|<span data-ttu-id="a5ca3-113">attribute</span><span class="sxs-lookup"><span data-stu-id="a5ca3-113">Attribute</span></span>|<span data-ttu-id="a5ca3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a5ca3-114">Description</span></span>|  
|---------------|-----------------|  
|`oldVersion`|<span data-ttu-id="a5ca3-115">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="a5ca3-116">Задает первоначально запрошенную версию сборки.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-116">Specifies the version of the assembly that was originally requested.</span></span> <span data-ttu-id="a5ca3-117">Формат номера сборочной версии *major.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-117">The format of an assembly version number is *major.minor.build.revision*.</span></span> <span data-ttu-id="a5ca3-118">Допустимые значения для каждой части этого номера версии — от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-118">Valid values for each part of this version number are 0 to 65535.</span></span><br /><br /> <span data-ttu-id="a5ca3-119">Диапазон версий можно также задать в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="a5ca3-119">You can also specify a range of versions in the following format:</span></span><br /><br /> <span data-ttu-id="a5ca3-120">*n.n.n.n - n.n.n.n*</span><span class="sxs-lookup"><span data-stu-id="a5ca3-120">*n.n.n.n - n.n.n.n*</span></span>|  
|`newVersion`|<span data-ttu-id="a5ca3-121">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-121">Required attribute.</span></span><br /><br /> <span data-ttu-id="a5ca3-122">Определяет версию сборки для использования вместо первоначально запрошенной версии в формате: *n.n.n.n*</span><span class="sxs-lookup"><span data-stu-id="a5ca3-122">Specifies the version of the assembly to use instead of the originally requested version in the format: *n.n.n.n*</span></span><br /><br /> <span data-ttu-id="a5ca3-123">Это значение может указывать более раннюю версию, чем `oldVersion`.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-123">This value can specify an earlier version than `oldVersion`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5ca3-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a5ca3-124">Child Elements</span></span>  
  
|<span data-ttu-id="a5ca3-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="a5ca3-125">Element</span></span>|<span data-ttu-id="a5ca3-126">Описание</span><span class="sxs-lookup"><span data-stu-id="a5ca3-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a5ca3-127">None</span><span class="sxs-lookup"><span data-stu-id="a5ca3-127">None</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="a5ca3-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a5ca3-128">Parent Elements</span></span>  
  
|<span data-ttu-id="a5ca3-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="a5ca3-129">Element</span></span>|<span data-ttu-id="a5ca3-130">Описание</span><span class="sxs-lookup"><span data-stu-id="a5ca3-130">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="a5ca3-131">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-131">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="a5ca3-132">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="a5ca3-133">Инкапсулирует политику привязки и расположение каждой сборки.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-133">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="a5ca3-134">Для каждой сборки используется только один элемент dependentAssembly.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-134">Use one dependentAssembly element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="a5ca3-135">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-135">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5ca3-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="a5ca3-136">Remarks</span></span>  
 <span data-ttu-id="a5ca3-137">При сборке приложения .NET Framework с использованием сборки со строгим именем приложение во время выполнения по умолчанию будет использовать эту версию сборки, даже если доступна новая версия.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-137">When you build a .NET Framework application against a strong-named assembly, the application uses that version of the assembly at run time by default, even if a new version is available.</span></span> <span data-ttu-id="a5ca3-138">Однако приложение можно настроить для выполнения с новой версией сборки.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-138">However, you can configure the application to run against a newer version of the assembly.</span></span> <span data-ttu-id="a5ca3-139">Для получения подробной информации о том, как время выполнения [How the Runtime Locates Assemblies](../../../deployment/how-the-runtime-locates-assemblies.md)использует эти файлы, чтобы определить, какую сборочную версию использовать, см.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-139">For details on how the runtime uses these files to determine which assembly version to use, see [How the Runtime Locates Assemblies](../../../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="a5ca3-140">Перенаправление нескольких версий сборок можно выполнить, включив в элемент `bindingRedirect` несколько элементов `dependentAssembly`.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-140">You can redirect more than one assembly version by including multiple `bindingRedirect` elements in a `dependentAssembly` element.</span></span> <span data-ttu-id="a5ca3-141">Можно также выполнить перенаправление с более новой версии на более раннюю версию сборки.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-141">You can also redirect from a newer version to an older version of the assembly.</span></span>  
  
 <span data-ttu-id="a5ca3-142">Для явного перенаправления привязки сборки в файле конфигурации приложения необходимо разрешение безопасности.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-142">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="a5ca3-143">Это относится к перенаправлению как сборок платформы .NET Framework, так и сторонних сборок.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-143">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="a5ca3-144">Разрешение выдается путем <xref:System.Security.Permissions.SecurityPermissionFlag> установки <xref:System.Security.Permissions.SecurityPermission>флага на .</span><span class="sxs-lookup"><span data-stu-id="a5ca3-144">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="a5ca3-145">Для получения дополнительной [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md)информации см.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-145">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5ca3-146">Пример</span><span class="sxs-lookup"><span data-stu-id="a5ca3-146">Example</span></span>  
 <span data-ttu-id="a5ca3-147">В следующем примере показан способ перенаправления одной версии сборки на другую.</span><span class="sxs-lookup"><span data-stu-id="a5ca3-147">The following example shows how to redirect one assembly version to another.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a5ca3-148">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a5ca3-148">See also</span></span>

- [<span data-ttu-id="a5ca3-149">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a5ca3-149">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a5ca3-150">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="a5ca3-150">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a5ca3-151">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="a5ca3-151">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
