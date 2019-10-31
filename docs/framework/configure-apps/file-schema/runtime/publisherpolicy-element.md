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
ms.openlocfilehash: 89fa8a991cc7d0352eb0a13cdfd3a6063ea468e7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115846"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="f0297-102">\<Publisherpolicy Apply > элемент</span><span class="sxs-lookup"><span data-stu-id="f0297-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="f0297-103">Указывает, применяет ли среда выполнения политику издателя.</span><span class="sxs-lookup"><span data-stu-id="f0297-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
<span data-ttu-id="f0297-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f0297-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f0297-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="f0297-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="f0297-106">&nbsp; &nbsp; &nbsp; &nbsp;[ **\<assemblyBinding**](assemblybinding-element-for-runtime.md) > </span><span class="sxs-lookup"><span data-stu-id="f0297-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="f0297-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dependentAssembly >** ](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="f0297-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="f0297-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<publisherpolicy apply >**</span><span class="sxs-lookup"><span data-stu-id="f0297-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<publisherPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0297-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0297-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0297-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f0297-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f0297-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f0297-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0297-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f0297-112">Attributes</span></span>  
  
|<span data-ttu-id="f0297-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f0297-113">Attribute</span></span>|<span data-ttu-id="f0297-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f0297-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="f0297-115">Указывает, следует ли применять политику издателя.</span><span class="sxs-lookup"><span data-stu-id="f0297-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="f0297-116">применить атрибут</span><span class="sxs-lookup"><span data-stu-id="f0297-116">apply Attribute</span></span>  
  
|<span data-ttu-id="f0297-117">значения</span><span class="sxs-lookup"><span data-stu-id="f0297-117">Value</span></span>|<span data-ttu-id="f0297-118">Описание</span><span class="sxs-lookup"><span data-stu-id="f0297-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="f0297-119">Применяет политику издателя.</span><span class="sxs-lookup"><span data-stu-id="f0297-119">Applies publisher policy.</span></span> <span data-ttu-id="f0297-120">Этот параметр используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f0297-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="f0297-121">Политика издателя не применяется.</span><span class="sxs-lookup"><span data-stu-id="f0297-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0297-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f0297-122">Child Elements</span></span>  

<span data-ttu-id="f0297-123">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f0297-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f0297-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f0297-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f0297-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="f0297-125">Element</span></span>|<span data-ttu-id="f0297-126">Описание</span><span class="sxs-lookup"><span data-stu-id="f0297-126">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="f0297-127">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="f0297-127">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="f0297-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f0297-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="f0297-129">Инкапсулирует политику привязки и расположение каждой сборки.</span><span class="sxs-lookup"><span data-stu-id="f0297-129">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="f0297-130">Для каждой сборки используется один элемент `<dependentAssembly>`.</span><span class="sxs-lookup"><span data-stu-id="f0297-130">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="f0297-131">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="f0297-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0297-132">Заметки</span><span class="sxs-lookup"><span data-stu-id="f0297-132">Remarks</span></span>  
 <span data-ttu-id="f0297-133">Когда поставщик компонента выпускает новую версию сборки, поставщик может включить политику издателя, чтобы приложения, использующие старую версию, теперь использовали новую версию.</span><span class="sxs-lookup"><span data-stu-id="f0297-133">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="f0297-134">Чтобы указать, следует ли применять политику издателя для конкретной сборки, вставьте элемент **\<publisherpolicy apply >** в элемент **\<dependentAssembly >** .</span><span class="sxs-lookup"><span data-stu-id="f0297-134">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="f0297-135">Значение по умолчанию для атрибута **Apply** — **Да**.</span><span class="sxs-lookup"><span data-stu-id="f0297-135">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="f0297-136">Присвоение атрибуту **Apply** значения **No** переопределяет любые предыдущие параметры **Yes** для сборки.</span><span class="sxs-lookup"><span data-stu-id="f0297-136">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="f0297-137">Для приложения требуется явное игнорирование политики издателя с помощью элемента [\<publisherpolicy Apply Apply = "No"/>](publisherpolicy-element.md) в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="f0297-137">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="f0297-138">Разрешение предоставляется путем установки флага <xref:System.Security.Permissions.SecurityPermissionFlag> на <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="f0297-138">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="f0297-139">Дополнительные сведения см. в статье [разрешение безопасности перенаправления привязки сборок](../../assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="f0297-139">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0297-140">Пример</span><span class="sxs-lookup"><span data-stu-id="f0297-140">Example</span></span>  
 <span data-ttu-id="f0297-141">В следующем примере отключается политика издателя для сборки `myAssembly`.</span><span class="sxs-lookup"><span data-stu-id="f0297-141">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f0297-142">См. также</span><span class="sxs-lookup"><span data-stu-id="f0297-142">See also</span></span>

- [<span data-ttu-id="f0297-143">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="f0297-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f0297-144">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="f0297-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f0297-145">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="f0297-145">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="f0297-146">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="f0297-146">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
