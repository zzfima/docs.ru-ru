---
title: Элемент <publisherPolicy>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29932eb27bcd13876ea6982982e67341edb8e0de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076293"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="f2645-102">\<publisherPolicy > элемент</span><span class="sxs-lookup"><span data-stu-id="f2645-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="f2645-103">Указывает, применяет ли среда выполнения политику издателя.</span><span class="sxs-lookup"><span data-stu-id="f2645-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
 <span data-ttu-id="f2645-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f2645-104">\<configuration></span></span>  
<span data-ttu-id="f2645-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="f2645-105">\<runtime></span></span>  
<span data-ttu-id="f2645-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="f2645-106">\<assemblyBinding></span></span>  
<span data-ttu-id="f2645-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="f2645-107">\<dependentAssembly></span></span>  
<span data-ttu-id="f2645-108">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="f2645-108">\<publisherPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2645-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2645-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2645-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f2645-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f2645-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f2645-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2645-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f2645-112">Attributes</span></span>  
  
|<span data-ttu-id="f2645-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f2645-113">Attribute</span></span>|<span data-ttu-id="f2645-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f2645-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="f2645-115">Указывает, следует ли применять политики издателя.</span><span class="sxs-lookup"><span data-stu-id="f2645-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="f2645-116">Применение атрибута</span><span class="sxs-lookup"><span data-stu-id="f2645-116">apply Attribute</span></span>  
  
|<span data-ttu-id="f2645-117">Значение</span><span class="sxs-lookup"><span data-stu-id="f2645-117">Value</span></span>|<span data-ttu-id="f2645-118">Описание</span><span class="sxs-lookup"><span data-stu-id="f2645-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="f2645-119">Политика издателя применяется.</span><span class="sxs-lookup"><span data-stu-id="f2645-119">Applies publisher policy.</span></span> <span data-ttu-id="f2645-120">Этот параметр используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f2645-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="f2645-121">Политика издателя не применяется.</span><span class="sxs-lookup"><span data-stu-id="f2645-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2645-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f2645-122">Child Elements</span></span>  
 <span data-ttu-id="f2645-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f2645-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f2645-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f2645-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f2645-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="f2645-125">Element</span></span>|<span data-ttu-id="f2645-126">Описание</span><span class="sxs-lookup"><span data-stu-id="f2645-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f2645-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f2645-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f2645-128">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="f2645-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2645-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="f2645-129">Remarks</span></span>  
 <span data-ttu-id="f2645-130">Когда разработчик компонентов выпускает новую версию сборки, поставщика можно включить политики издателя, чтобы приложения, использующие старую версию теперь использовать новую версию.</span><span class="sxs-lookup"><span data-stu-id="f2645-130">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="f2645-131">Чтобы указать, следует ли применять политику издателя для определенной сборки, поместите  **\<publisherPolicy >** элемент в  **\<dependentAssembly >** элемент.</span><span class="sxs-lookup"><span data-stu-id="f2645-131">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="f2645-132">По умолчанию **применить** атрибут **Да**.</span><span class="sxs-lookup"><span data-stu-id="f2645-132">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="f2645-133">Установка **применить** атрибут **не** переопределит все предыдущие **Да** параметры для сборки.</span><span class="sxs-lookup"><span data-stu-id="f2645-133">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="f2645-134">Требуется разрешение для приложения, чтобы явно игнорировать политику издателя с помощью [ \<исполняемым = «no» / >](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) элемент в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="f2645-134">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="f2645-135">Разрешение, задав <xref:System.Security.Permissions.SecurityPermissionFlag> флаг <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="f2645-135">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="f2645-136">Дополнительные сведения см. в разделе [разрешение безопасности перенаправления привязки сборки](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="f2645-136">For more information, see [Assembly Binding Redirection Security Permission](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2645-137">Пример</span><span class="sxs-lookup"><span data-stu-id="f2645-137">Example</span></span>  
 <span data-ttu-id="f2645-138">В следующем примере производится отключение политики издателя для сборки, `myAssembly`.</span><span class="sxs-lookup"><span data-stu-id="f2645-138">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2645-139">См. также</span><span class="sxs-lookup"><span data-stu-id="f2645-139">See also</span></span>

- [<span data-ttu-id="f2645-140">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="f2645-140">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="f2645-141">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="f2645-141">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="f2645-142">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="f2645-142">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="f2645-143">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="f2645-143">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
