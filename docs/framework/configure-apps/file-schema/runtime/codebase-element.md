---
title: Элемент <codeBase>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
ms.openlocfilehash: b5825efcc613689e73fb56b6695fe7c75ff09136
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356615"
---
# <a name="codebase-element"></a><span data-ttu-id="170a4-102">\<codeBase > элемент</span><span class="sxs-lookup"><span data-stu-id="170a4-102">\<codeBase> Element</span></span>

<span data-ttu-id="170a4-103">Указывает, где среда CLR может найти сборку.</span><span class="sxs-lookup"><span data-stu-id="170a4-103">Specifies where the common language runtime can find an assembly.</span></span>

<span data-ttu-id="170a4-104">\<configuration> \<runtime> \<assemblyBinding> \<dependentAssembly> \<codeBase></span><span class="sxs-lookup"><span data-stu-id="170a4-104">\<configuration> \<runtime> \<assemblyBinding> \<dependentAssembly> \<codeBase></span></span>

## <a name="syntax"></a><span data-ttu-id="170a4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="170a4-105">Syntax</span></span>

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="170a4-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="170a4-106">Attributes and Elements</span></span>

<span data-ttu-id="170a4-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="170a4-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="170a4-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="170a4-108">Attributes</span></span>

|<span data-ttu-id="170a4-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="170a4-109">Attribute</span></span>|<span data-ttu-id="170a4-110">Описание</span><span class="sxs-lookup"><span data-stu-id="170a4-110">Description</span></span>|
|---------------|-----------------|
|`href`|<span data-ttu-id="170a4-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="170a4-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="170a4-112">Указывает URL-адрес, где среда выполнения может найти указанную версию сборки.</span><span class="sxs-lookup"><span data-stu-id="170a4-112">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|
|`version`|<span data-ttu-id="170a4-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="170a4-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="170a4-114">Указывает версию сборки, к которым применяется базы кода.</span><span class="sxs-lookup"><span data-stu-id="170a4-114">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="170a4-115">Формат номера версии сборки *major.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="170a4-115">The format of an assembly version number is *major.minor.build.revision*.</span></span>|

## <a name="version-attribute"></a><span data-ttu-id="170a4-116">Атрибут версии</span><span class="sxs-lookup"><span data-stu-id="170a4-116">version Attribute</span></span>

|<span data-ttu-id="170a4-117">Значение</span><span class="sxs-lookup"><span data-stu-id="170a4-117">Value</span></span>|<span data-ttu-id="170a4-118">Описание</span><span class="sxs-lookup"><span data-stu-id="170a4-118">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="170a4-119">Допустимые значения для каждой части номера версии: от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="170a4-119">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="170a4-120">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="170a4-120">Not applicable.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="170a4-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="170a4-121">Child Elements</span></span>

<span data-ttu-id="170a4-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="170a4-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="170a4-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="170a4-123">Parent Elements</span></span>

|<span data-ttu-id="170a4-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="170a4-124">Element</span></span>|<span data-ttu-id="170a4-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="170a4-125">Description</span></span>|
|-------------|-----------------|
|`buildproviders`|<span data-ttu-id="170a4-126">Определяет набор поставщиков построения, которые используются для компиляции пользовательских файлов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="170a4-126">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="170a4-127">Можно использовать любое число поставщиков построения.</span><span class="sxs-lookup"><span data-stu-id="170a4-127">You can have any number of build providers.</span></span>|
|`compilation`|<span data-ttu-id="170a4-128">Настраивает все параметры, используемые платформой ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="170a4-128">Configures all the compilation settings that ASP.NET uses.</span></span>|
|`configuration`|<span data-ttu-id="170a4-129">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="170a4-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`System.web`|<span data-ttu-id="170a4-130">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="170a4-130">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="170a4-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="170a4-131">Remarks</span></span>

<span data-ttu-id="170a4-132">Для среды выполнения для использования  **\<codeBase >** параметр в файле конфигурации компьютера или файле политики издателя, файл должен также перенаправление версии сборки.</span><span class="sxs-lookup"><span data-stu-id="170a4-132">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="170a4-133">Файлы конфигурации приложения может иметь параметр базы кода без перенаправления версии сборки.</span><span class="sxs-lookup"><span data-stu-id="170a4-133">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="170a4-134">Выяснив, какие версии сборки, среда выполнения применяется параметр базы кода из файла, который определяет версию.</span><span class="sxs-lookup"><span data-stu-id="170a4-134">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="170a4-135">Если база кода, среда выполняет поиск сборки обычным способом.</span><span class="sxs-lookup"><span data-stu-id="170a4-135">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>

<span data-ttu-id="170a4-136">Если сборка имеет строгое имя, параметр базы кода может быть в любом месте в локальной интрасети или в Интернете.</span><span class="sxs-lookup"><span data-stu-id="170a4-136">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="170a4-137">Если сборка является закрытой сборки, параметр базы кода должен быть путь относительно каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="170a4-137">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>

<span data-ttu-id="170a4-138">Для сборок без строгого имени, версия игнорируется, и загрузчик использует первое значение \<codebase > внутри \<dependentAssembly >.</span><span class="sxs-lookup"><span data-stu-id="170a4-138">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="170a4-139">Если имеется запись в файле конфигурации приложения, перенаправление привязки в другую сборку, перенаправление будет иметь приоритет, даже если версия сборки не соответствует запросу.</span><span class="sxs-lookup"><span data-stu-id="170a4-139">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesn't match the binding request.</span></span>

## <a name="example"></a><span data-ttu-id="170a4-140">Пример</span><span class="sxs-lookup"><span data-stu-id="170a4-140">Example</span></span>

<span data-ttu-id="170a4-141">Приведенный ниже показано, как указать, где среда выполнения может найти сборку.</span><span class="sxs-lookup"><span data-stu-id="170a4-141">The following example shows how to specify where the runtime can find an assembly.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="170a4-142">См. также</span><span class="sxs-lookup"><span data-stu-id="170a4-142">See also</span></span>

- [<span data-ttu-id="170a4-143">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="170a4-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="170a4-144">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="170a4-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="170a4-145">Указание расположения сборки</span><span class="sxs-lookup"><span data-stu-id="170a4-145">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)
- [<span data-ttu-id="170a4-146">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="170a4-146">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
