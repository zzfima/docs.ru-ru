---
title: '&lt;codeBase&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
author: mcleblanc
ms.author: markl
ms.openlocfilehash: d7563d3a0ba545bfd8d1b80981fcce607d230873
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028228"
---
# <a name="ltcodebasegt-element"></a><span data-ttu-id="a4278-102">&lt;codeBase&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="a4278-102">&lt;codeBase&gt; Element</span></span>
<span data-ttu-id="a4278-103">Указывает, где среда CLR может найти сборку.</span><span class="sxs-lookup"><span data-stu-id="a4278-103">Specifies where the common language runtime can find an assembly.</span></span>  
  
 <span data-ttu-id="a4278-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a4278-104">\<configuration></span></span>  
<span data-ttu-id="a4278-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="a4278-105">\<runtime></span></span>  
<span data-ttu-id="a4278-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="a4278-106">\<assemblyBinding></span></span>  
<span data-ttu-id="a4278-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="a4278-107">\<dependentAssembly></span></span>  
<span data-ttu-id="a4278-108">\<codeBase ></span><span class="sxs-lookup"><span data-stu-id="a4278-108">\<codeBase></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4278-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4278-109">Syntax</span></span>  
  
```xml  
   <codeBase    
version="Assembly version"  
href="URL of assembly"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4278-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a4278-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a4278-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a4278-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4278-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a4278-112">Attributes</span></span>  
  
|<span data-ttu-id="a4278-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a4278-113">Attribute</span></span>|<span data-ttu-id="a4278-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a4278-114">Description</span></span>|  
|---------------|-----------------|  
|`href`|<span data-ttu-id="a4278-115">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a4278-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="a4278-116">Указывает URL-адрес, где среда выполнения может найти указанную версию сборки.</span><span class="sxs-lookup"><span data-stu-id="a4278-116">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|  
|`version`|<span data-ttu-id="a4278-117">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a4278-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="a4278-118">Указывает версию сборки, к которым применяется базы кода.</span><span class="sxs-lookup"><span data-stu-id="a4278-118">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="a4278-119">Формат номера версии сборки *major.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="a4278-119">The format of an assembly version number is *major.minor.build.revision*.</span></span>|  
  
## <a name="version-attribute"></a><span data-ttu-id="a4278-120">Атрибут версии</span><span class="sxs-lookup"><span data-stu-id="a4278-120">version Attribute</span></span>  
  
|<span data-ttu-id="a4278-121">Значение</span><span class="sxs-lookup"><span data-stu-id="a4278-121">Value</span></span>|<span data-ttu-id="a4278-122">Описание</span><span class="sxs-lookup"><span data-stu-id="a4278-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a4278-123">Допустимые значения для каждой части номера версии: от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="a4278-123">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="a4278-124">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="a4278-124">Not applicable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4278-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a4278-125">Child Elements</span></span>  
 <span data-ttu-id="a4278-126">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a4278-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4278-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a4278-127">Parent Elements</span></span>  
  
|<span data-ttu-id="a4278-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="a4278-128">Element</span></span>|<span data-ttu-id="a4278-129">Описание</span><span class="sxs-lookup"><span data-stu-id="a4278-129">Description</span></span>|  
|-------------|-----------------|  
|`buildproviders`|<span data-ttu-id="a4278-130">Определяет набор поставщиков построения, которые используются для компиляции пользовательских файлов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a4278-130">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="a4278-131">Можно использовать любое число поставщиков построения.</span><span class="sxs-lookup"><span data-stu-id="a4278-131">You can have any number of build providers.</span></span>|  
|`compilation`|<span data-ttu-id="a4278-132">Настраивает все параметры, используемые платформой ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a4278-132">Configures all the compilation settings that ASP.NET uses.</span></span>|  
|`configuration`|<span data-ttu-id="a4278-133">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a4278-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.web`|<span data-ttu-id="a4278-134">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a4278-134">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4278-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="a4278-135">Remarks</span></span>  
 <span data-ttu-id="a4278-136">Для среды выполнения для использования  **\<codeBase >** параметр в файле конфигурации компьютера или файле политики издателя, файл должен также перенаправление версии сборки.</span><span class="sxs-lookup"><span data-stu-id="a4278-136">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="a4278-137">Файлы конфигурации приложения может иметь параметр базы кода без перенаправления версии сборки.</span><span class="sxs-lookup"><span data-stu-id="a4278-137">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="a4278-138">Выяснив, какие версии сборки, среда выполнения применяется параметр базы кода из файла, который определяет версию.</span><span class="sxs-lookup"><span data-stu-id="a4278-138">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="a4278-139">Если база кода, среда выполняет поиск сборки обычным способом.</span><span class="sxs-lookup"><span data-stu-id="a4278-139">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>  
  
 <span data-ttu-id="a4278-140">Если сборка имеет строгое имя, параметр базы кода может быть в любом месте в локальной интрасети или в Интернете.</span><span class="sxs-lookup"><span data-stu-id="a4278-140">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="a4278-141">Если сборка является закрытой сборки, параметр базы кода должен быть путь относительно каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="a4278-141">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>  
  
 <span data-ttu-id="a4278-142">Для сборок без строгого имени, версия игнорируется, и загрузчик использует первое значение \<codebase > внутри \<dependentAssembly >.</span><span class="sxs-lookup"><span data-stu-id="a4278-142">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="a4278-143">Если имеется запись в файле конфигурации приложения, перенаправление привязки в другую сборку, перенаправление будет иметь приоритет, даже если версия сборки не соответствует запросу.</span><span class="sxs-lookup"><span data-stu-id="a4278-143">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesnt match the binding request.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4278-144">Пример</span><span class="sxs-lookup"><span data-stu-id="a4278-144">Example</span></span>  
 <span data-ttu-id="a4278-145">Приведенный ниже показано, как указать, где среда выполнения может найти сборку.</span><span class="sxs-lookup"><span data-stu-id="a4278-145">The following example shows how to specify where the runtime can find an assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4278-146">См. также</span><span class="sxs-lookup"><span data-stu-id="a4278-146">See Also</span></span>  
 [<span data-ttu-id="a4278-147">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="a4278-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="a4278-148">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="a4278-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="a4278-149">Указание расположения сборки</span><span class="sxs-lookup"><span data-stu-id="a4278-149">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
 [<span data-ttu-id="a4278-150">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="a4278-150">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
