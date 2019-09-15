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
ms.openlocfilehash: 475b7df55ed509157c1da0aeb8f979de238c72b5
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971891"
---
# <a name="codebase-element"></a><span data-ttu-id="41c5e-102">\<Элемент codeBase ></span><span class="sxs-lookup"><span data-stu-id="41c5e-102">\<codeBase> Element</span></span>

<span data-ttu-id="41c5e-103">Указывает, где среда CLR может найти сборку.</span><span class="sxs-lookup"><span data-stu-id="41c5e-103">Specifies where the common language runtime can find an assembly.</span></span>

<span data-ttu-id="41c5e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="41c5e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="41c5e-105">&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="41c5e-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="41c5e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="41c5e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="41c5e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dependentAssembly >** ](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="41c5e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="41c5e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<База кода >**</span><span class="sxs-lookup"><span data-stu-id="41c5e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<codeBase>**</span></span>

## <a name="syntax"></a><span data-ttu-id="41c5e-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41c5e-109">Syntax</span></span>

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="41c5e-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="41c5e-110">Attributes and Elements</span></span>

<span data-ttu-id="41c5e-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="41c5e-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="41c5e-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="41c5e-112">Attributes</span></span>

|<span data-ttu-id="41c5e-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="41c5e-113">Attribute</span></span>|<span data-ttu-id="41c5e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="41c5e-114">Description</span></span>|
|---------------|-----------------|
|`href`|<span data-ttu-id="41c5e-115">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="41c5e-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="41c5e-116">Указывает URL-адрес, по которому среда выполнения может найти указанную версию сборки.</span><span class="sxs-lookup"><span data-stu-id="41c5e-116">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|
|`version`|<span data-ttu-id="41c5e-117">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="41c5e-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="41c5e-118">Указывает версию сборки, к которой применяется база кода.</span><span class="sxs-lookup"><span data-stu-id="41c5e-118">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="41c5e-119">Номер версии сборки имеет формат *основной. дополнительный. сборка. Редакция*.</span><span class="sxs-lookup"><span data-stu-id="41c5e-119">The format of an assembly version number is *major.minor.build.revision*.</span></span>|

## <a name="version-attribute"></a><span data-ttu-id="41c5e-120">Атрибут версии</span><span class="sxs-lookup"><span data-stu-id="41c5e-120">version Attribute</span></span>

|<span data-ttu-id="41c5e-121">Значение</span><span class="sxs-lookup"><span data-stu-id="41c5e-121">Value</span></span>|<span data-ttu-id="41c5e-122">Описание</span><span class="sxs-lookup"><span data-stu-id="41c5e-122">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="41c5e-123">Допустимые значения для каждой части номера версии — от 0 до 65535.</span><span class="sxs-lookup"><span data-stu-id="41c5e-123">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="41c5e-124">Не применяется</span><span class="sxs-lookup"><span data-stu-id="41c5e-124">Not applicable.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="41c5e-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="41c5e-125">Child Elements</span></span>

<span data-ttu-id="41c5e-126">Нет.</span><span class="sxs-lookup"><span data-stu-id="41c5e-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="41c5e-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="41c5e-127">Parent Elements</span></span>

|<span data-ttu-id="41c5e-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="41c5e-128">Element</span></span>|<span data-ttu-id="41c5e-129">Описание</span><span class="sxs-lookup"><span data-stu-id="41c5e-129">Description</span></span>|
|-------------|-----------------|
|`buildproviders`|<span data-ttu-id="41c5e-130">Определяет набор поставщиков построения, которые используются для компиляции пользовательских файлов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="41c5e-130">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="41c5e-131">Можно использовать любое число поставщиков построения.</span><span class="sxs-lookup"><span data-stu-id="41c5e-131">You can have any number of build providers.</span></span>|
|`compilation`|<span data-ttu-id="41c5e-132">Настраивает все параметры компиляции, используемые ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="41c5e-132">Configures all the compilation settings that ASP.NET uses.</span></span>|
|`configuration`|<span data-ttu-id="41c5e-133">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="41c5e-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`System.web`|<span data-ttu-id="41c5e-134">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="41c5e-134">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="41c5e-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="41c5e-135">Remarks</span></span>

<span data-ttu-id="41c5e-136">Чтобы среда выполнения использовала  **\<параметр базы кода >** в файле конфигурации компьютера или файле политики издателя, файл должен также перенаправлять версию сборки.</span><span class="sxs-lookup"><span data-stu-id="41c5e-136">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="41c5e-137">Файлы конфигурации приложения могут иметь параметр базы кода без перенаправления версии сборки.</span><span class="sxs-lookup"><span data-stu-id="41c5e-137">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="41c5e-138">После определения используемой версии сборки среда выполнения применяет параметр базы кода из файла, определяющего версию.</span><span class="sxs-lookup"><span data-stu-id="41c5e-138">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="41c5e-139">Если база кода не указана, среда выполнения проверяет наличие сборки обычным способом.</span><span class="sxs-lookup"><span data-stu-id="41c5e-139">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>

<span data-ttu-id="41c5e-140">Если сборка имеет строгое имя, параметр базы кода может находиться в любом месте локальной интрасети или в Интернете.</span><span class="sxs-lookup"><span data-stu-id="41c5e-140">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="41c5e-141">Если сборка является закрытой, параметр базы кода должен быть путем относительно каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="41c5e-141">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>

<span data-ttu-id="41c5e-142">Для сборок без строгого имени версия игнорируется, а загрузчик использует первый внешний вид \<базы кода > в \<dependentAssembly >.</span><span class="sxs-lookup"><span data-stu-id="41c5e-142">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="41c5e-143">Если в файле конфигурации приложения имеется запись, которая перенаправляет привязку к другой сборке, перенаправление будет иметь приоритет, даже если версия сборки не соответствует запросу привязки.</span><span class="sxs-lookup"><span data-stu-id="41c5e-143">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesn't match the binding request.</span></span>

## <a name="example"></a><span data-ttu-id="41c5e-144">Пример</span><span class="sxs-lookup"><span data-stu-id="41c5e-144">Example</span></span>

<span data-ttu-id="41c5e-145">В следующем примере показано, как указать, где среда выполнения может найти сборку.</span><span class="sxs-lookup"><span data-stu-id="41c5e-145">The following example shows how to specify where the runtime can find an assembly.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="41c5e-146">См. также</span><span class="sxs-lookup"><span data-stu-id="41c5e-146">See also</span></span>

- [<span data-ttu-id="41c5e-147">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="41c5e-147">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="41c5e-148">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="41c5e-148">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="41c5e-149">Укажите расположение сборки</span><span class="sxs-lookup"><span data-stu-id="41c5e-149">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="41c5e-150">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="41c5e-150">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
