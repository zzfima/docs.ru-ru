---
title: "&lt;publisherPolicy&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d5f629dd347f63c8fb8e624c475bfb0ecf658f41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltpublisherpolicygt-element"></a><span data-ttu-id="22cb5-102">&lt;publisherPolicy&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="22cb5-102">&lt;publisherPolicy&gt; Element</span></span>
<span data-ttu-id="22cb5-103">Указывает, применяет ли среда выполнения политику издателя.</span><span class="sxs-lookup"><span data-stu-id="22cb5-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
 <span data-ttu-id="22cb5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="22cb5-104">\<configuration></span></span>  
<span data-ttu-id="22cb5-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="22cb5-105">\<runtime></span></span>  
<span data-ttu-id="22cb5-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="22cb5-106">\<assemblyBinding></span></span>  
<span data-ttu-id="22cb5-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="22cb5-107">\<dependentAssembly></span></span>  
<span data-ttu-id="22cb5-108">\<publisherPolicy ></span><span class="sxs-lookup"><span data-stu-id="22cb5-108">\<publisherPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22cb5-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22cb5-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22cb5-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="22cb5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="22cb5-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="22cb5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22cb5-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="22cb5-112">Attributes</span></span>  
  
|<span data-ttu-id="22cb5-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="22cb5-113">Attribute</span></span>|<span data-ttu-id="22cb5-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="22cb5-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="22cb5-115">Указывает, будет ли применяться политика издателя.</span><span class="sxs-lookup"><span data-stu-id="22cb5-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="22cb5-116">Применение атрибута</span><span class="sxs-lookup"><span data-stu-id="22cb5-116">apply Attribute</span></span>  
  
|<span data-ttu-id="22cb5-117">Значение</span><span class="sxs-lookup"><span data-stu-id="22cb5-117">Value</span></span>|<span data-ttu-id="22cb5-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="22cb5-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="22cb5-119">Применяет политику издателя.</span><span class="sxs-lookup"><span data-stu-id="22cb5-119">Applies publisher policy.</span></span> <span data-ttu-id="22cb5-120">Этот параметр используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="22cb5-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="22cb5-121">Политика издателя не применяется.</span><span class="sxs-lookup"><span data-stu-id="22cb5-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22cb5-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="22cb5-122">Child Elements</span></span>  
 <span data-ttu-id="22cb5-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="22cb5-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22cb5-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="22cb5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="22cb5-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="22cb5-125">Element</span></span>|<span data-ttu-id="22cb5-126">Описание</span><span class="sxs-lookup"><span data-stu-id="22cb5-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="22cb5-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22cb5-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="22cb5-128">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="22cb5-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22cb5-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="22cb5-129">Remarks</span></span>  
 <span data-ttu-id="22cb5-130">Если разработчик компонентов выпускает новую версию сборки, поставщика могут включать политики издателя, приложения, использующие старую версию, теперь будут использовать новую версию.</span><span class="sxs-lookup"><span data-stu-id="22cb5-130">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="22cb5-131">Чтобы указать, будет ли применяться политика издателя для определенной сборки, поместите  **\<publisherPolicy >** элемент в  **\<dependentAssembly >** элемента.</span><span class="sxs-lookup"><span data-stu-id="22cb5-131">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="22cb5-132">Значение по умолчанию для **применить** атрибут **Да**.</span><span class="sxs-lookup"><span data-stu-id="22cb5-132">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="22cb5-133">Установка **применить** атрибут **не** переопределит все предыдущие **Да** параметры для сборки.</span><span class="sxs-lookup"><span data-stu-id="22cb5-133">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="22cb5-134">Требуется разрешение для приложения, чтобы явно игнорировать политику издателя с помощью [ \<исполняемым = «no» / >](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="22cb5-134">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="22cb5-135">Разрешение можно получить, установив <xref:System.Security.Permissions.SecurityPermissionFlag> флаг <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="22cb5-135">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="22cb5-136">Дополнительные сведения см. в разделе [разрешение безопасности перенаправления привязки сборок](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="22cb5-136">For more information, see [Assembly Binding Redirection Security Permission](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="22cb5-137">Пример</span><span class="sxs-lookup"><span data-stu-id="22cb5-137">Example</span></span>  
 <span data-ttu-id="22cb5-138">В следующем примере производится отключение политики издателя для сборки, `myAssembly`.</span><span class="sxs-lookup"><span data-stu-id="22cb5-138">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="22cb5-139">См. также</span><span class="sxs-lookup"><span data-stu-id="22cb5-139">See Also</span></span>  
 [<span data-ttu-id="22cb5-140">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="22cb5-140">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="22cb5-141">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="22cb5-141">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="22cb5-142">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="22cb5-142">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="22cb5-143">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="22cb5-143">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
