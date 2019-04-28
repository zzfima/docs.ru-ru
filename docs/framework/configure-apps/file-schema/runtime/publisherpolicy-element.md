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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674081"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="f02b9-102">\<publisherPolicy > элемент</span><span class="sxs-lookup"><span data-stu-id="f02b9-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="f02b9-103">Указывает, применяет ли среда выполнения политику издателя.</span><span class="sxs-lookup"><span data-stu-id="f02b9-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
 <span data-ttu-id="f02b9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f02b9-104">\<configuration></span></span>  
<span data-ttu-id="f02b9-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="f02b9-105">\<runtime></span></span>  
<span data-ttu-id="f02b9-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="f02b9-106">\<assemblyBinding></span></span>  
<span data-ttu-id="f02b9-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="f02b9-107">\<dependentAssembly></span></span>  
<span data-ttu-id="f02b9-108">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="f02b9-108">\<publisherPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f02b9-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f02b9-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f02b9-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f02b9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f02b9-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f02b9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f02b9-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f02b9-112">Attributes</span></span>  
  
|<span data-ttu-id="f02b9-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f02b9-113">Attribute</span></span>|<span data-ttu-id="f02b9-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f02b9-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="f02b9-115">Указывает, следует ли применять политики издателя.</span><span class="sxs-lookup"><span data-stu-id="f02b9-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="f02b9-116">Применение атрибута</span><span class="sxs-lookup"><span data-stu-id="f02b9-116">apply Attribute</span></span>  
  
|<span data-ttu-id="f02b9-117">Значение</span><span class="sxs-lookup"><span data-stu-id="f02b9-117">Value</span></span>|<span data-ttu-id="f02b9-118">Описание</span><span class="sxs-lookup"><span data-stu-id="f02b9-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="f02b9-119">Политика издателя применяется.</span><span class="sxs-lookup"><span data-stu-id="f02b9-119">Applies publisher policy.</span></span> <span data-ttu-id="f02b9-120">Этот параметр используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f02b9-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="f02b9-121">Политика издателя не применяется.</span><span class="sxs-lookup"><span data-stu-id="f02b9-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f02b9-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f02b9-122">Child Elements</span></span>  
 <span data-ttu-id="f02b9-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f02b9-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f02b9-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f02b9-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f02b9-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="f02b9-125">Element</span></span>|<span data-ttu-id="f02b9-126">Описание</span><span class="sxs-lookup"><span data-stu-id="f02b9-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f02b9-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f02b9-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f02b9-128">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="f02b9-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f02b9-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="f02b9-129">Remarks</span></span>  
 <span data-ttu-id="f02b9-130">Когда разработчик компонентов выпускает новую версию сборки, поставщика можно включить политики издателя, чтобы приложения, использующие старую версию теперь использовать новую версию.</span><span class="sxs-lookup"><span data-stu-id="f02b9-130">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="f02b9-131">Чтобы указать, следует ли применять политику издателя для определенной сборки, поместите  **\<publisherPolicy >** элемент в  **\<dependentAssembly >** элемент.</span><span class="sxs-lookup"><span data-stu-id="f02b9-131">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="f02b9-132">По умолчанию **применить** атрибут **Да**.</span><span class="sxs-lookup"><span data-stu-id="f02b9-132">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="f02b9-133">Установка **применить** атрибут **не** переопределит все предыдущие **Да** параметры для сборки.</span><span class="sxs-lookup"><span data-stu-id="f02b9-133">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="f02b9-134">Требуется разрешение для приложения, чтобы явно игнорировать политику издателя с помощью [ \<исполняемым = «no» / >](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) элемент в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="f02b9-134">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="f02b9-135">Разрешение, задав <xref:System.Security.Permissions.SecurityPermissionFlag> флаг <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="f02b9-135">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="f02b9-136">Дополнительные сведения см. в разделе [разрешение безопасности перенаправления привязки сборки](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="f02b9-136">For more information, see [Assembly Binding Redirection Security Permission](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f02b9-137">Пример</span><span class="sxs-lookup"><span data-stu-id="f02b9-137">Example</span></span>  
 <span data-ttu-id="f02b9-138">В следующем примере производится отключение политики издателя для сборки, `myAssembly`.</span><span class="sxs-lookup"><span data-stu-id="f02b9-138">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f02b9-139">См. также</span><span class="sxs-lookup"><span data-stu-id="f02b9-139">See also</span></span>

- [<span data-ttu-id="f02b9-140">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="f02b9-140">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="f02b9-141">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="f02b9-141">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="f02b9-142">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="f02b9-142">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="f02b9-143">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="f02b9-143">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
