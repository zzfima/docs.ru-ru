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
ms.openlocfilehash: 815e1c26a328d986f91992a1e67e438a563ffea6
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663889"
---
# <a name="assemblyidentity-element-for-runtime"></a><span data-ttu-id="275e5-102">\<элемент assemblyIdentity > для \<> среды выполнения</span><span class="sxs-lookup"><span data-stu-id="275e5-102">\<assemblyIdentity> Element for \<runtime></span></span>
<span data-ttu-id="275e5-103">Содержит идентифицирующие сведения о сборке.</span><span class="sxs-lookup"><span data-stu-id="275e5-103">Contains identifying information about the assembly.</span></span>  
  
 <span data-ttu-id="275e5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="275e5-104">\<configuration></span></span>  
<span data-ttu-id="275e5-105">\<> среды выполнения</span><span class="sxs-lookup"><span data-stu-id="275e5-105">\<runtime></span></span>  
<span data-ttu-id="275e5-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="275e5-106">\<assemblyBinding></span></span>  
<span data-ttu-id="275e5-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="275e5-107">\<dependentAssembly></span></span>  
<span data-ttu-id="275e5-108">\<assemblyIdentity ></span><span class="sxs-lookup"><span data-stu-id="275e5-108">\<assemblyIdentity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="275e5-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="275e5-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="275e5-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="275e5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="275e5-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="275e5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="275e5-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="275e5-112">Attributes</span></span>  
  
|<span data-ttu-id="275e5-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="275e5-113">Attribute</span></span>|<span data-ttu-id="275e5-114">Описание</span><span class="sxs-lookup"><span data-stu-id="275e5-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="275e5-115">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="275e5-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="275e5-116">Имя сборки</span><span class="sxs-lookup"><span data-stu-id="275e5-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="275e5-117">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="275e5-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="275e5-118">Строка, указывающая язык и страну или регион сборки.</span><span class="sxs-lookup"><span data-stu-id="275e5-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="275e5-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="275e5-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="275e5-120">Шестнадцатеричное значение, указывающее строгое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="275e5-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="275e5-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="275e5-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="275e5-122">Одно из значений "x86", "amd64", "MSIL" или "ia64", определяющее архитектуру процессора для сборки, содержащей код, зависящий от процессора.</span><span class="sxs-lookup"><span data-stu-id="275e5-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="275e5-123">В значениях регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="275e5-123">The values are not case-sensitive.</span></span> <span data-ttu-id="275e5-124">Если атрибуту присвоено любое другое значение, весь `<assemblyIdentity>` элемент игнорируется.</span><span class="sxs-lookup"><span data-stu-id="275e5-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="275e5-125">См. раздел <xref:System.Reflection.ProcessorArchitecture>.</span><span class="sxs-lookup"><span data-stu-id="275e5-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="275e5-126">Атрибут processorArchitecture</span><span class="sxs-lookup"><span data-stu-id="275e5-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="275e5-127">Значение</span><span class="sxs-lookup"><span data-stu-id="275e5-127">Value</span></span>|<span data-ttu-id="275e5-128">Описание</span><span class="sxs-lookup"><span data-stu-id="275e5-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="275e5-129">Только архитектура AMD x86-64.</span><span class="sxs-lookup"><span data-stu-id="275e5-129">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="275e5-130">Только архитектура Intel Itanium.</span><span class="sxs-lookup"><span data-stu-id="275e5-130">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="275e5-131">Не зависит от процессора и разрядов на каждое слово.</span><span class="sxs-lookup"><span data-stu-id="275e5-131">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="275e5-132">32-разрядный процессор x86, либо собственный, либо в среде Windows on Windows (WOW) на 64-разрядной платформе.</span><span class="sxs-lookup"><span data-stu-id="275e5-132">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="275e5-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="275e5-133">Child Elements</span></span>  
 <span data-ttu-id="275e5-134">Нет.</span><span class="sxs-lookup"><span data-stu-id="275e5-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="275e5-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="275e5-135">Parent Elements</span></span>  
  
|<span data-ttu-id="275e5-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="275e5-136">Element</span></span>|<span data-ttu-id="275e5-137">Описание</span><span class="sxs-lookup"><span data-stu-id="275e5-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="275e5-138">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="275e5-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="275e5-139">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="275e5-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="275e5-140">Инкапсулирует политику привязки и расположение каждой сборки.</span><span class="sxs-lookup"><span data-stu-id="275e5-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="275e5-141">Для каждой `<dependentAssembly>` сборки используется один элемент.</span><span class="sxs-lookup"><span data-stu-id="275e5-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="275e5-142">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="275e5-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="275e5-143">Примечания</span><span class="sxs-lookup"><span data-stu-id="275e5-143">Remarks</span></span>  
 <span data-ttu-id="275e5-144">**Каждый\<элемент dependentAssembly >** должен иметь один  **\<** дочерний элемент assemblyIdentity >.</span><span class="sxs-lookup"><span data-stu-id="275e5-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="275e5-145">Если атрибут имеется `<assemblyIdentity>` , элемент применяется только к сборке с соответствующей архитектурой процессора. `processorArchitecture`</span><span class="sxs-lookup"><span data-stu-id="275e5-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="275e5-146">Если атрибут отсутствует `<assemblyIdentity>` , элемент может применяться к сборке с любой архитектурой процессора. `processorArchitecture`</span><span class="sxs-lookup"><span data-stu-id="275e5-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="275e5-147">В следующем примере показан файл конфигурации для двух сборок с одинаковым именем, предназначенных для двух разных архитектур процессора, чьи версии не поддерживали синхронизацию. При выполнении приложения на платформе x86 первый `<assemblyIdentity>` элемент применяется, а другой игнорируется.</span><span class="sxs-lookup"><span data-stu-id="275e5-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="275e5-148">Если приложение выполняется на платформе, отличной от x86 или ia64, то оба они игнорируются.</span><span class="sxs-lookup"><span data-stu-id="275e5-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
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
  
 <span data-ttu-id="275e5-149">Если файл конфигурации содержит `<assemblyIdentity>` элемент `processorArchitecture` без атрибута и не содержит элемент, соответствующий платформе `processorArchitecture` , то используется элемент без атрибута.</span><span class="sxs-lookup"><span data-stu-id="275e5-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="275e5-150">Пример</span><span class="sxs-lookup"><span data-stu-id="275e5-150">Example</span></span>  
 <span data-ttu-id="275e5-151">В следующем примере показано, как предоставить сведения о сборке.</span><span class="sxs-lookup"><span data-stu-id="275e5-151">The following example shows how to provide information about an assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="275e5-152">См. также</span><span class="sxs-lookup"><span data-stu-id="275e5-152">See also</span></span>

- [<span data-ttu-id="275e5-153">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="275e5-153">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="275e5-154">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="275e5-154">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="275e5-155">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="275e5-155">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
