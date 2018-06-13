---
title: '&lt;dependentAssembly&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#dependentAssembly
helpviewer_keywords:
- container tags, <dependentAssembly> element
- dependentAssembly element
- <dependentAssembly> element
ms.assetid: 14e95627-dd79-4b82-ac85-e682aa3a31d8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54036baee6fc2d7af49e818a1c112dec8eac80aa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744916"
---
# <a name="ltdependentassemblygt-element"></a><span data-ttu-id="377dd-102">&lt;dependentAssembly&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="377dd-102">&lt;dependentAssembly&gt; Element</span></span>
<span data-ttu-id="377dd-103">Инкапсулирует политику привязки и расположение каждой сборки.</span><span class="sxs-lookup"><span data-stu-id="377dd-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="377dd-104">Используйте один `dependentAssembly` элемент для каждой сборки.</span><span class="sxs-lookup"><span data-stu-id="377dd-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
 <span data-ttu-id="377dd-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="377dd-105">\<configuration></span></span>  
<span data-ttu-id="377dd-106">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="377dd-106">\<runtime></span></span>  
<span data-ttu-id="377dd-107">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="377dd-107">\<assemblyBinding></span></span>  
<span data-ttu-id="377dd-108">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="377dd-108">\<dependentAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="377dd-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="377dd-109">Syntax</span></span>  
  
```xml  
<dependentAssembly>   
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="377dd-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="377dd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="377dd-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="377dd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="377dd-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="377dd-112">Attributes</span></span>  
 <span data-ttu-id="377dd-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="377dd-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="377dd-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="377dd-114">Child Elements</span></span>  
  
|<span data-ttu-id="377dd-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="377dd-115">Element</span></span>|<span data-ttu-id="377dd-116">Описание</span><span class="sxs-lookup"><span data-stu-id="377dd-116">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="377dd-117">Содержит идентификационные сведения о сборке.</span><span class="sxs-lookup"><span data-stu-id="377dd-117">Contains identifying information about the assembly.</span></span> <span data-ttu-id="377dd-118">Этот элемент должен быть включен в каждом `dependentAssembly` элемента.</span><span class="sxs-lookup"><span data-stu-id="377dd-118">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="377dd-119">Указывает, где среда выполнения можно найти общей сборки, если он не установлен на компьютере.</span><span class="sxs-lookup"><span data-stu-id="377dd-119">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="377dd-120">Перенаправляет одну версию сборки на другую.</span><span class="sxs-lookup"><span data-stu-id="377dd-120">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="377dd-121">Указывает, применяется ли среда выполнения политику издателя для этой сборки.</span><span class="sxs-lookup"><span data-stu-id="377dd-121">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="377dd-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="377dd-122">Parent Elements</span></span>  
  
|<span data-ttu-id="377dd-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="377dd-123">Element</span></span>|<span data-ttu-id="377dd-124">Описание</span><span class="sxs-lookup"><span data-stu-id="377dd-124">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="377dd-125">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="377dd-125">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="377dd-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="377dd-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="377dd-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="377dd-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="377dd-128">Пример</span><span class="sxs-lookup"><span data-stu-id="377dd-128">Example</span></span>  
 <span data-ttu-id="377dd-129">В следующем примере показано, как для инкапсуляции данных для двух сборок.</span><span class="sxs-lookup"><span data-stu-id="377dd-129">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="mySecondAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for mySecondAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="377dd-130">См. также</span><span class="sxs-lookup"><span data-stu-id="377dd-130">See Also</span></span>  
 [<span data-ttu-id="377dd-131">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="377dd-131">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="377dd-132">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="377dd-132">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="377dd-133">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="377dd-133">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
