---
title: "&lt;codeBase&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c5b30f1dc3ccade3028c31c57ffdab521802f086
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltcodebasegt-element"></a><span data-ttu-id="70cc7-102">&lt;codeBase&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="70cc7-102">&lt;codeBase&gt; Element</span></span>
<span data-ttu-id="70cc7-103">Указывает, где общеязыковая среда выполнения может найти сборку.</span><span class="sxs-lookup"><span data-stu-id="70cc7-103">Specifies where the common language runtime can find an assembly.</span></span>  
  
 <span data-ttu-id="70cc7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="70cc7-104">\<configuration></span></span>  
<span data-ttu-id="70cc7-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="70cc7-105">\<runtime></span></span>  
<span data-ttu-id="70cc7-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="70cc7-106">\<assemblyBinding></span></span>  
<span data-ttu-id="70cc7-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="70cc7-107">\<dependentAssembly></span></span>  
<span data-ttu-id="70cc7-108">\<codeBase ></span><span class="sxs-lookup"><span data-stu-id="70cc7-108">\<codeBase></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70cc7-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70cc7-109">Syntax</span></span>  
  
```xml  
   <codeBase    
version="Assembly version"  
href="URL of assembly"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70cc7-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="70cc7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="70cc7-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="70cc7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70cc7-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="70cc7-112">Attributes</span></span>  
  
|<span data-ttu-id="70cc7-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="70cc7-113">Attribute</span></span>|<span data-ttu-id="70cc7-114">Описание</span><span class="sxs-lookup"><span data-stu-id="70cc7-114">Description</span></span>|  
|---------------|-----------------|  
|`href`|<span data-ttu-id="70cc7-115">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="70cc7-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="70cc7-116">Указывает URL-адрес, где среда выполнения может найти указанная версия сборки.</span><span class="sxs-lookup"><span data-stu-id="70cc7-116">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|  
|`version`|<span data-ttu-id="70cc7-117">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="70cc7-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="70cc7-118">Указывает версию сборки, которой применяется база кода.</span><span class="sxs-lookup"><span data-stu-id="70cc7-118">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="70cc7-119">Недопустимый формат номера версии сборки *major.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="70cc7-119">The format of an assembly version number is *major.minor.build.revision*.</span></span>|  
  
## <a name="version-attribute"></a><span data-ttu-id="70cc7-120">версия атрибут</span><span class="sxs-lookup"><span data-stu-id="70cc7-120">version Attribute</span></span>  
  
|<span data-ttu-id="70cc7-121">Значение</span><span class="sxs-lookup"><span data-stu-id="70cc7-121">Value</span></span>|<span data-ttu-id="70cc7-122">Описание</span><span class="sxs-lookup"><span data-stu-id="70cc7-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="70cc7-123">Допустимые значения для каждой части номера версии: от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="70cc7-123">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="70cc7-124">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="70cc7-124">Not applicable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70cc7-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="70cc7-125">Child Elements</span></span>  
 <span data-ttu-id="70cc7-126">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="70cc7-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70cc7-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="70cc7-127">Parent Elements</span></span>  
  
|<span data-ttu-id="70cc7-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="70cc7-128">Element</span></span>|<span data-ttu-id="70cc7-129">Описание</span><span class="sxs-lookup"><span data-stu-id="70cc7-129">Description</span></span>|  
|-------------|-----------------|  
|`buildproviders`|<span data-ttu-id="70cc7-130">Определяет набор поставщиков построения, которые используются для компиляции пользовательских файлов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="70cc7-130">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="70cc7-131">Можно использовать любое число поставщиков построения.</span><span class="sxs-lookup"><span data-stu-id="70cc7-131">You can have any number of build providers.</span></span>|  
|`compilation`|<span data-ttu-id="70cc7-132">Настраивает все параметры, используемые ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="70cc7-132">Configures all the compilation settings that ASP.NET uses.</span></span>|  
|`configuration`|<span data-ttu-id="70cc7-133">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="70cc7-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.web`|<span data-ttu-id="70cc7-134">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="70cc7-134">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70cc7-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="70cc7-135">Remarks</span></span>  
 <span data-ttu-id="70cc7-136">Для среды выполнения для использования  **\<codeBase >** параметр в файле конфигурации компьютера или файле политики издателя, файл должен также задавать перенаправление версии сборки.</span><span class="sxs-lookup"><span data-stu-id="70cc7-136">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="70cc7-137">Файлы конфигурации приложения может иметь параметр базы кода без перенаправления версии сборки.</span><span class="sxs-lookup"><span data-stu-id="70cc7-137">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="70cc7-138">После определения версии сборки для использования, среда выполнения применяется параметр базы кода из файла, который определяет версию.</span><span class="sxs-lookup"><span data-stu-id="70cc7-138">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="70cc7-139">Если база кода, среда выполнения проверяет наличие сборки обычным способом.</span><span class="sxs-lookup"><span data-stu-id="70cc7-139">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>  
  
 <span data-ttu-id="70cc7-140">Если сборка имеет строгое имя, параметр базы кода может быть в любом месте в локальной интрасети или в Интернете.</span><span class="sxs-lookup"><span data-stu-id="70cc7-140">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="70cc7-141">Если сборка является закрытой, параметр базы кода должен быть путь относительно каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="70cc7-141">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>  
  
 <span data-ttu-id="70cc7-142">Для сборки не указано строгое имя, версия игнорируется, и загрузчик использует первое значение \<codebase > внутри \<dependentAssembly >.</span><span class="sxs-lookup"><span data-stu-id="70cc7-142">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="70cc7-143">Если имеется запись в файле конфигурации приложения перенаправление привязки на другую сборку, перенаправление получает приоритет, даже если версия сборки не соответствует запросу привязки.</span><span class="sxs-lookup"><span data-stu-id="70cc7-143">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesnt match the binding request.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70cc7-144">Пример</span><span class="sxs-lookup"><span data-stu-id="70cc7-144">Example</span></span>  
 <span data-ttu-id="70cc7-145">Приведенный ниже показано, как указать расположение сборки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="70cc7-145">The following example shows how to specify where the runtime can find an assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="70cc7-146">См. также</span><span class="sxs-lookup"><span data-stu-id="70cc7-146">See Also</span></span>  
 [<span data-ttu-id="70cc7-147">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="70cc7-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="70cc7-148">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="70cc7-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="70cc7-149">Указание расположения сборки</span><span class="sxs-lookup"><span data-stu-id="70cc7-149">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
 [<span data-ttu-id="70cc7-150">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="70cc7-150">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
