---
title: Элемент <assemblyIdentity> для <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
ms.openlocfilehash: b026dafbde796bbd8726de56b532ed6710ba2290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154313"
---
# <a name="assemblyidentity-element-for-runtime"></a><span data-ttu-id="ac863-102">\<assemblyIdentity> \<Элемент для> времени выполнения</span><span class="sxs-lookup"><span data-stu-id="ac863-102">\<assemblyIdentity> Element for \<runtime></span></span>
<span data-ttu-id="ac863-103">Содержит идентифицирующую информацию о сборке.</span><span class="sxs-lookup"><span data-stu-id="ac863-103">Contains identifying information about the assembly.</span></span>  
  
<span data-ttu-id="ac863-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ac863-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ac863-105">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="ac863-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="ac863-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<сборкаОбязательная>**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="ac863-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="ac863-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<зависимаясборка>**](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="ac863-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="ac863-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<сборкаIdentityличная>**</span><span class="sxs-lookup"><span data-stu-id="ac863-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac863-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac863-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac863-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ac863-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ac863-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ac863-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac863-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ac863-112">Attributes</span></span>  
  
|<span data-ttu-id="ac863-113">attribute</span><span class="sxs-lookup"><span data-stu-id="ac863-113">Attribute</span></span>|<span data-ttu-id="ac863-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ac863-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="ac863-115">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ac863-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="ac863-116">Название сборки</span><span class="sxs-lookup"><span data-stu-id="ac863-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="ac863-117">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ac863-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ac863-118">Строка, опоменавававательства языка и страны/региона собрания.</span><span class="sxs-lookup"><span data-stu-id="ac863-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="ac863-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ac863-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ac863-120">Гексадецимическое значение, которое определяет сильное название сборки.</span><span class="sxs-lookup"><span data-stu-id="ac863-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="ac863-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ac863-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ac863-122">Одно из значений "x86", "amd64", "msil" или "ia64", определяющее архитектуру процессора для сборки, содержащей код для процессора.</span><span class="sxs-lookup"><span data-stu-id="ac863-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="ac863-123">Значения не чувствительны к случаям.</span><span class="sxs-lookup"><span data-stu-id="ac863-123">The values are not case-sensitive.</span></span> <span data-ttu-id="ac863-124">Если атрибуту присваивается `<assemblyIdentity>` какое-либо другое значение, весь элемент игнорируется.</span><span class="sxs-lookup"><span data-stu-id="ac863-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="ac863-125">См. раздел <xref:System.Reflection.ProcessorArchitecture>.</span><span class="sxs-lookup"><span data-stu-id="ac863-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="ac863-126">processorArchitecture Атрибут</span><span class="sxs-lookup"><span data-stu-id="ac863-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="ac863-127">Значение</span><span class="sxs-lookup"><span data-stu-id="ac863-127">Value</span></span>|<span data-ttu-id="ac863-128">Описание</span><span class="sxs-lookup"><span data-stu-id="ac863-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="ac863-129">AMD x86-64 только архитектура.</span><span class="sxs-lookup"><span data-stu-id="ac863-129">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="ac863-130">Только архитектура Intel Itanium.</span><span class="sxs-lookup"><span data-stu-id="ac863-130">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="ac863-131">Код нейтрален по отношению к процессору и разрядности слова.</span><span class="sxs-lookup"><span data-stu-id="ac863-131">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="ac863-132">32-разрядный процессор x86, как родной, так и в среде Windows на Windows (WOW) на 64-битной платформе.</span><span class="sxs-lookup"><span data-stu-id="ac863-132">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac863-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ac863-133">Child Elements</span></span>  
 <span data-ttu-id="ac863-134">Нет.</span><span class="sxs-lookup"><span data-stu-id="ac863-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac863-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ac863-135">Parent Elements</span></span>  
  
|<span data-ttu-id="ac863-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="ac863-136">Element</span></span>|<span data-ttu-id="ac863-137">Описание</span><span class="sxs-lookup"><span data-stu-id="ac863-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="ac863-138">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="ac863-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="ac863-139">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ac863-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="ac863-140">Инкапсулирует политику привязки и расположение каждой сборки.</span><span class="sxs-lookup"><span data-stu-id="ac863-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="ac863-141">Используйте `<dependentAssembly>` один элемент для каждой сборки.</span><span class="sxs-lookup"><span data-stu-id="ac863-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="ac863-142">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="ac863-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac863-143">Remarks</span><span class="sxs-lookup"><span data-stu-id="ac863-143">Remarks</span></span>  
 <span data-ttu-id="ac863-144">Каждый \*\* \<зависимый элементсборки>\*\* должен иметь одну \*\* \<сборкуIdentity>\*\* элемента ребенка.</span><span class="sxs-lookup"><span data-stu-id="ac863-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="ac863-145">При `processorArchitecture` наличии атрибута `<assemblyIdentity>` элемент применяется только к сборке с соответствующей архитектурой процессора.</span><span class="sxs-lookup"><span data-stu-id="ac863-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="ac863-146">Если `processorArchitecture` атрибут не присутствует, `<assemblyIdentity>` элемент может применяться к сборке с любой архитектурой процессора.</span><span class="sxs-lookup"><span data-stu-id="ac863-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="ac863-147">В следующем примере показан файл конфигурации для двух сборок с одинаковым именем, ориентированный на две разные две архитектуры процессора и версии которых не были синхронизированы. Когда приложение выполняется на платформе x86, первый `<assemblyIdentity>` элемент применяется, а другой игнорируется.</span><span class="sxs-lookup"><span data-stu-id="ac863-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="ac863-148">Если приложение выполняется на платформе, кроме x86 или ia64, оба игнорируются.</span><span class="sxs-lookup"><span data-stu-id="ac863-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="ac863-149">Если файл конфигурации `<assemblyIdentity>` содержит `processorArchitecture` элемент без атрибута и не содержит элемента, `processorArchitecture` который соответствует платформе, используется элемент без атрибута.</span><span class="sxs-lookup"><span data-stu-id="ac863-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac863-150">Пример</span><span class="sxs-lookup"><span data-stu-id="ac863-150">Example</span></span>  
 <span data-ttu-id="ac863-151">В следующем примере показано, как предоставить информацию о сборке.</span><span class="sxs-lookup"><span data-stu-id="ac863-151">The following example shows how to provide information about an assembly.</span></span>  
  
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
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac863-152">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ac863-152">See also</span></span>

- [<span data-ttu-id="ac863-153">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="ac863-153">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ac863-154">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="ac863-154">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ac863-155">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="ac863-155">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
