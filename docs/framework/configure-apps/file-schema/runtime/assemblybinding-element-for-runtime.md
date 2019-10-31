---
title: Элемент <assemblyBinding> для <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
ms.openlocfilehash: c688353583f5e452950d63b7d02c48505b6ae999
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118134"
---
# <a name="assemblybinding-element-for-runtime"></a><span data-ttu-id="92723-102">\<элемент > assemblyBinding для среды выполнения \<</span><span class="sxs-lookup"><span data-stu-id="92723-102">\<assemblyBinding> Element for \<runtime></span></span>
<span data-ttu-id="92723-103">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="92723-103">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
<span data-ttu-id="92723-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="92723-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="92723-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="92723-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="92723-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<assemblyBinding >**</span><span class="sxs-lookup"><span data-stu-id="92723-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92723-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92723-107">Syntax</span></span>  
  
```xml  
      <assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92723-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="92723-108">Attributes and Elements</span></span>  
 <span data-ttu-id="92723-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="92723-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92723-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="92723-110">Attributes</span></span>  
  
|<span data-ttu-id="92723-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="92723-111">Attribute</span></span>|<span data-ttu-id="92723-112">Описание</span><span class="sxs-lookup"><span data-stu-id="92723-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="92723-113">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="92723-113">**xmlns**</span></span>|<span data-ttu-id="92723-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="92723-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="92723-115">Задает пространство имен XML, необходимое для привязки сборок.</span><span class="sxs-lookup"><span data-stu-id="92723-115">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="92723-116">Используйте строку urn:schemas-microsoft-com:asm.v1 в качестве значения.</span><span class="sxs-lookup"><span data-stu-id="92723-116">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="92723-117">**appliesTo**</span><span class="sxs-lookup"><span data-stu-id="92723-117">**appliesTo**</span></span>|<span data-ttu-id="92723-118">Задает версию среды выполнения, к которой применяется перенаправление сборки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="92723-118">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="92723-119">Этот необязательный атрибут содержит номер версии .NET Framework, к которой применяется перенаправление.</span><span class="sxs-lookup"><span data-stu-id="92723-119">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="92723-120">Если атрибут **appliesTo** не указан, элемент **\<assemblyBinding>** применяется ко всем версиям платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="92723-120">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="92723-121">Атрибут **appliesTo** появился в .NET Framework версии 1,1; он игнорируется .NET Framework версии 1,0.</span><span class="sxs-lookup"><span data-stu-id="92723-121">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="92723-122">Это означает, что при использовании платформы .NET Framework версии 1.0 применяются все элементы **\<assemblyBinding>** , даже если атрибут **appliesTo** задан.</span><span class="sxs-lookup"><span data-stu-id="92723-122">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="92723-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="92723-123">Child Elements</span></span>  
  
|<span data-ttu-id="92723-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="92723-124">Element</span></span>|<span data-ttu-id="92723-125">Описание</span><span class="sxs-lookup"><span data-stu-id="92723-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92723-126">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="92723-126">\<dependentAssembly></span></span>](dependentassembly-element.md)|<span data-ttu-id="92723-127">Инкапсулирует политику привязки и расположение сборки.</span><span class="sxs-lookup"><span data-stu-id="92723-127">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="92723-128">Используйте один **\<dependentAssembly >** тега для каждой сборки.</span><span class="sxs-lookup"><span data-stu-id="92723-128">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[<span data-ttu-id="92723-129">\<probing></span><span class="sxs-lookup"><span data-stu-id="92723-129">\<probing></span></span>](probing-element.md)|<span data-ttu-id="92723-130">Задает вложенные папки, в которых среда CLR выполняет поиск при загрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="92723-130">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[<span data-ttu-id="92723-131">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="92723-131">\<publisherPolicy></span></span>](publisherpolicy-element.md)|<span data-ttu-id="92723-132">Указывает, применяет ли среда выполнения политику издателя.</span><span class="sxs-lookup"><span data-stu-id="92723-132">Specifies whether the runtime applies publisher policy.</span></span>|  
|[<span data-ttu-id="92723-133">\<qualifyAssembly></span><span class="sxs-lookup"><span data-stu-id="92723-133">\<qualifyAssembly></span></span>](qualifyassembly-element.md)|<span data-ttu-id="92723-134">Задает полное имя сборки, которая должна загружаться динамически в случае использования неполного имени.</span><span class="sxs-lookup"><span data-stu-id="92723-134">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="92723-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="92723-135">Parent Elements</span></span>  
  
|<span data-ttu-id="92723-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="92723-136">Element</span></span>|<span data-ttu-id="92723-137">Описание</span><span class="sxs-lookup"><span data-stu-id="92723-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="92723-138">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="92723-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="92723-139">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="92723-139">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="92723-140">Пример</span><span class="sxs-lookup"><span data-stu-id="92723-140">Example</span></span>  
 <span data-ttu-id="92723-141">В следующем примере показан способ перенаправления одной версии сборки на другую и предоставлена база кода.</span><span class="sxs-lookup"><span data-stu-id="92723-141">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
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
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="92723-142">В следующем примере показано, как использовать атрибут **appliesTo** для перенаправления привязки .NET Framework сборки.</span><span class="sxs-lookup"><span data-stu-id="92723-142">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
```xml  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>   
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="92723-143">См. также</span><span class="sxs-lookup"><span data-stu-id="92723-143">See also</span></span>

- [<span data-ttu-id="92723-144">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="92723-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="92723-145">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="92723-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="92723-146">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="92723-146">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
