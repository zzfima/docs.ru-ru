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
ms.openlocfilehash: 7c8f8744d3ef1ca30eb05a4c8c3290d8a514714b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663516"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="7e043-102">\<Элемент > Publisherpolicy Apply</span><span class="sxs-lookup"><span data-stu-id="7e043-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="7e043-103">Указывает, применяет ли среда выполнения политику издателя.</span><span class="sxs-lookup"><span data-stu-id="7e043-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
 <span data-ttu-id="7e043-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7e043-104">\<configuration></span></span>  
<span data-ttu-id="7e043-105">\<> среды выполнения</span><span class="sxs-lookup"><span data-stu-id="7e043-105">\<runtime></span></span>  
<span data-ttu-id="7e043-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="7e043-106">\<assemblyBinding></span></span>  
<span data-ttu-id="7e043-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="7e043-107">\<dependentAssembly></span></span>  
<span data-ttu-id="7e043-108">\<Publisherpolicy Apply ></span><span class="sxs-lookup"><span data-stu-id="7e043-108">\<publisherPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e043-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e043-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e043-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7e043-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7e043-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7e043-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e043-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7e043-112">Attributes</span></span>  
  
|<span data-ttu-id="7e043-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7e043-113">Attribute</span></span>|<span data-ttu-id="7e043-114">Описание</span><span class="sxs-lookup"><span data-stu-id="7e043-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="7e043-115">Указывает, следует ли применять политику издателя.</span><span class="sxs-lookup"><span data-stu-id="7e043-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="7e043-116">применить атрибут</span><span class="sxs-lookup"><span data-stu-id="7e043-116">apply Attribute</span></span>  
  
|<span data-ttu-id="7e043-117">Значение</span><span class="sxs-lookup"><span data-stu-id="7e043-117">Value</span></span>|<span data-ttu-id="7e043-118">Описание</span><span class="sxs-lookup"><span data-stu-id="7e043-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="7e043-119">Применяет политику издателя.</span><span class="sxs-lookup"><span data-stu-id="7e043-119">Applies publisher policy.</span></span> <span data-ttu-id="7e043-120">Этот параметр используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7e043-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="7e043-121">Политика издателя не применяется.</span><span class="sxs-lookup"><span data-stu-id="7e043-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e043-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7e043-122">Child Elements</span></span>  
 <span data-ttu-id="7e043-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="7e043-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e043-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7e043-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7e043-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="7e043-125">Element</span></span>|<span data-ttu-id="7e043-126">Описание</span><span class="sxs-lookup"><span data-stu-id="7e043-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7e043-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7e043-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7e043-128">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="7e043-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e043-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="7e043-129">Remarks</span></span>  
 <span data-ttu-id="7e043-130">Когда поставщик компонента выпускает новую версию сборки, поставщик может включить политику издателя, чтобы приложения, использующие старую версию, теперь использовали новую версию.</span><span class="sxs-lookup"><span data-stu-id="7e043-130">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="7e043-131">Чтобы указать, следует ли применять политику издателя для конкретной сборки, вставьте  **\<элемент publisherpolicy Apply >** в  **\<элемент dependentAssembly >** .</span><span class="sxs-lookup"><span data-stu-id="7e043-131">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="7e043-132">Значение по умолчанию для атрибута **Apply** — **Да**.</span><span class="sxs-lookup"><span data-stu-id="7e043-132">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="7e043-133">Присвоение атрибуту **Apply** значения **No** переопределяет любые предыдущие параметры **Yes** для сборки.</span><span class="sxs-lookup"><span data-stu-id="7e043-133">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="7e043-134">Для приложения требуется явное игнорирование политики издателя с помощью [ \<элемента publisherpolicy Apply Apply = "No"/>](publisherpolicy-element.md) в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="7e043-134">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="7e043-135">Разрешение предоставляется путем установки <xref:System.Security.Permissions.SecurityPermissionFlag> флага <xref:System.Security.Permissions.SecurityPermission>для.</span><span class="sxs-lookup"><span data-stu-id="7e043-135">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="7e043-136">Дополнительные сведения см. в статье [разрешение безопасности перенаправления привязки сборок](../../assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="7e043-136">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e043-137">Пример</span><span class="sxs-lookup"><span data-stu-id="7e043-137">Example</span></span>  
 <span data-ttu-id="7e043-138">В следующем примере отключается политика издателя для сборки `myAssembly`.</span><span class="sxs-lookup"><span data-stu-id="7e043-138">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7e043-139">См. также</span><span class="sxs-lookup"><span data-stu-id="7e043-139">See also</span></span>

- [<span data-ttu-id="7e043-140">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="7e043-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7e043-141">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="7e043-141">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7e043-142">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="7e043-142">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="7e043-143">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="7e043-143">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
