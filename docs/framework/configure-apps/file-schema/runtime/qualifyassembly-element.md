---
title: Элемент <qualifyAssembly>
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
ms.openlocfilehash: 6a4741c6a4745bdba00fdb525b39b70d0b15e005
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704860"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="17f85-102">\<qualifyAssembly > элемент</span><span class="sxs-lookup"><span data-stu-id="17f85-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="17f85-103">Задает полное имя сборки, которая должна загружаться динамически в случае использования неполного имени.</span><span class="sxs-lookup"><span data-stu-id="17f85-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
 <span data-ttu-id="17f85-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="17f85-104">\<configuration></span></span>  
<span data-ttu-id="17f85-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="17f85-105">\<runtime></span></span>  
<span data-ttu-id="17f85-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="17f85-106">\<assemblyBinding></span></span>  
<span data-ttu-id="17f85-107">\<qualifyAssembly ></span><span class="sxs-lookup"><span data-stu-id="17f85-107">\<qualifyAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17f85-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="17f85-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17f85-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="17f85-109">Attributes and Elements</span></span>  
 <span data-ttu-id="17f85-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="17f85-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17f85-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="17f85-111">Attributes</span></span>  
  
|<span data-ttu-id="17f85-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="17f85-112">Attribute</span></span>|<span data-ttu-id="17f85-113">Описание</span><span class="sxs-lookup"><span data-stu-id="17f85-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="17f85-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="17f85-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="17f85-115">Задает имя частичной сборки, как оно отображается в коде.</span><span class="sxs-lookup"><span data-stu-id="17f85-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="17f85-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="17f85-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="17f85-117">Указывает полное имя сборки, как оно отображается в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="17f85-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17f85-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="17f85-118">Child Elements</span></span>  
 <span data-ttu-id="17f85-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="17f85-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="17f85-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="17f85-120">Parent Elements</span></span>  
  
|<span data-ttu-id="17f85-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="17f85-121">Element</span></span>|<span data-ttu-id="17f85-122">Описание</span><span class="sxs-lookup"><span data-stu-id="17f85-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="17f85-123">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="17f85-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="17f85-124">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="17f85-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="17f85-125">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="17f85-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17f85-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="17f85-126">Remarks</span></span>  
 <span data-ttu-id="17f85-127">Вызов <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> среда CLR для поиска сборки только в базовой папке приложения вызывает метод, с помощью частичных имен сборок.</span><span class="sxs-lookup"><span data-stu-id="17f85-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="17f85-128">Используйте  **\<qualifyAssembly >** элемент в файле конфигурации приложения для предоставления полных сведений о сборке (имя, версию, токен открытого ключа и язык и региональные параметры) и привести к среда CLR для поиска для сборки в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="17f85-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="17f85-129">**FullName** атрибут должен содержать четыре поля удостоверение сборки: имя, версия, токен открытого ключа и языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="17f85-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="17f85-130">**PartialName** атрибут частично необходимо сослаться на сборку.</span><span class="sxs-lookup"><span data-stu-id="17f85-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="17f85-131">Необходимо указать по крайней мере текстовое имя сборки (наиболее распространенный случай), но можно также включить версия, токен открытого ключа, или язык и региональные параметры (или любое сочетание четырех, но не все четыре).</span><span class="sxs-lookup"><span data-stu-id="17f85-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="17f85-132">**PartialName** должно соответствовать имени, указанному в вызове.</span><span class="sxs-lookup"><span data-stu-id="17f85-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="17f85-133">Например, нельзя указать `"math"` как **partialName** атрибута в файл конфигурации и вызвать `Assembly.Load("math, Version=3.3.3.3")` в коде.</span><span class="sxs-lookup"><span data-stu-id="17f85-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17f85-134">Пример</span><span class="sxs-lookup"><span data-stu-id="17f85-134">Example</span></span>  
 <span data-ttu-id="17f85-135">В следующем примере производится логически вызов `Assembly.Load("math")` в `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span><span class="sxs-lookup"><span data-stu-id="17f85-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="17f85-136">См. также</span><span class="sxs-lookup"><span data-stu-id="17f85-136">See also</span></span>

- [<span data-ttu-id="17f85-137">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="17f85-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="17f85-138">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="17f85-138">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="17f85-139">[Частичные ссылки на сборки](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="17f85-139">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
