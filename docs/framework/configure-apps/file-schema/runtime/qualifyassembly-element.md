---
title: '&lt;qualifyAssembly&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d08cfbde82f74dcf88ddadd844854bdfeb403935
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltqualifyassemblygt-element"></a><span data-ttu-id="33f62-102">&lt;qualifyAssembly&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="33f62-102">&lt;qualifyAssembly&gt; Element</span></span>
<span data-ttu-id="33f62-103">Задает полное имя сборки, которая должна загружаться динамически в случае использования неполного имени.</span><span class="sxs-lookup"><span data-stu-id="33f62-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
 <span data-ttu-id="33f62-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="33f62-104">\<configuration></span></span>  
<span data-ttu-id="33f62-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="33f62-105">\<runtime></span></span>  
<span data-ttu-id="33f62-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="33f62-106">\<assemblyBinding></span></span>  
<span data-ttu-id="33f62-107">\<qualifyAssembly ></span><span class="sxs-lookup"><span data-stu-id="33f62-107">\<qualifyAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33f62-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33f62-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33f62-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="33f62-109">Attributes and Elements</span></span>  
 <span data-ttu-id="33f62-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="33f62-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33f62-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="33f62-111">Attributes</span></span>  
  
|<span data-ttu-id="33f62-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="33f62-112">Attribute</span></span>|<span data-ttu-id="33f62-113">Описание</span><span class="sxs-lookup"><span data-stu-id="33f62-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="33f62-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="33f62-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="33f62-115">Указывает частичное имя сборки, как оно отображается в коде.</span><span class="sxs-lookup"><span data-stu-id="33f62-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="33f62-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="33f62-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="33f62-117">Указывает полное имя сборки, как оно отображается в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="33f62-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33f62-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="33f62-118">Child Elements</span></span>  
 <span data-ttu-id="33f62-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="33f62-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33f62-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="33f62-120">Parent Elements</span></span>  
  
|<span data-ttu-id="33f62-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="33f62-121">Element</span></span>|<span data-ttu-id="33f62-122">Описание</span><span class="sxs-lookup"><span data-stu-id="33f62-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="33f62-123">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="33f62-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="33f62-124">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="33f62-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="33f62-125">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="33f62-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33f62-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="33f62-126">Remarks</span></span>  
 <span data-ttu-id="33f62-127">Вызов <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> метода с использованием частичных имен сборок средой CLR, следует искать сборки только в базовой папке приложения.</span><span class="sxs-lookup"><span data-stu-id="33f62-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="33f62-128">Используйте  **\<qualifyAssembly >** элемент в файле конфигурации приложения для предоставления полных сведений о сборке (имя, версию, маркер открытого ключа и языка и региональных параметров) и средой CLR для поиска для сборки в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="33f62-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="33f62-129">**FullName** атрибут должен включать четыре поля удостоверения сборки: имя, версию, маркер открытого ключа и языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="33f62-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="33f62-130">**PartialName** атрибут необходимо частично ссылку на сборку.</span><span class="sxs-lookup"><span data-stu-id="33f62-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="33f62-131">Необходимо указать по крайней мере текстовое имя сборки (наиболее распространенный случай), но можно также включить версию, маркер открытого ключа или язык и региональные параметры (или любое сочетание четырех, но не все четыре).</span><span class="sxs-lookup"><span data-stu-id="33f62-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="33f62-132">**PartialName** должно соответствовать имени, указанному в вызове.</span><span class="sxs-lookup"><span data-stu-id="33f62-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="33f62-133">Например, нельзя указать `"math"` как **partialName** атрибута в файл конфигурации и вызовите `Assembly.Load("math, Version=3.3.3.3")` в коде.</span><span class="sxs-lookup"><span data-stu-id="33f62-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33f62-134">Пример</span><span class="sxs-lookup"><span data-stu-id="33f62-134">Example</span></span>  
 <span data-ttu-id="33f62-135">В следующем примере производится логически вызов `Assembly.Load("math")` в `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span><span class="sxs-lookup"><span data-stu-id="33f62-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="33f62-136">См. также</span><span class="sxs-lookup"><span data-stu-id="33f62-136">See Also</span></span>  
 [<span data-ttu-id="33f62-137">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="33f62-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="33f62-138">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="33f62-138">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="33f62-139">NIB: Частичные ссылки на сборки</span><span class="sxs-lookup"><span data-stu-id="33f62-139">NIB: Partial Assembly References</span></span>](http://msdn.microsoft.com/library/ec90f07a-398c-4306-9401-0fc5ff9cb59f)
