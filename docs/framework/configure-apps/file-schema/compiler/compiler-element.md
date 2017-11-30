---
title: "&lt;Компилятор&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 8d2562bb37413cd07b4548bbf2bad0b6a9aedbc5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltcompilergt-element"></a><span data-ttu-id="4c577-102">&lt;Компилятор&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="4c577-102">&lt;compiler&gt; Element</span></span>
<span data-ttu-id="4c577-103">Задает атрибуты конфигурации компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="4c577-103">Specifies the compiler configuration attributes for a language provider.</span></span>  
  
 <span data-ttu-id="4c577-104">\<Элемент конфигурации ></span><span class="sxs-lookup"><span data-stu-id="4c577-104">\<configuration Element></span></span>  
<span data-ttu-id="4c577-105">\<System.CodeDom-элемент ></span><span class="sxs-lookup"><span data-stu-id="4c577-105">\<system.codedom Element></span></span>  
<span data-ttu-id="4c577-106">\<компиляторы элемент ></span><span class="sxs-lookup"><span data-stu-id="4c577-106">\<compilers Element></span></span>  
<span data-ttu-id="4c577-107">\<Компилятор > элемент</span><span class="sxs-lookup"><span data-stu-id="4c577-107">\<compiler> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c577-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c577-108">Syntax</span></span>  
  
```xml  
<compiler  
  language="languageName[;...;...]"  
  extension="fileExtension[;...;...]"  
  type="typeName, assemblyName"  
  warningLevel="number"  
  compilerOptions="option1 option2"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c577-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4c577-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4c577-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4c577-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c577-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4c577-111">Attributes</span></span>  
  
|<span data-ttu-id="4c577-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4c577-112">Attribute</span></span>|<span data-ttu-id="4c577-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4c577-113">Description</span></span>|  
|---------------|-----------------|  
|`compilerOptions`|<span data-ttu-id="4c577-114">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4c577-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4c577-115">Задает дополнительные аргументы компилятора для компиляции.</span><span class="sxs-lookup"><span data-stu-id="4c577-115">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="4c577-116">Значения для `compilerOptions` атрибут обычно отображаются в разделе параметры компилятора для компилятора.</span><span class="sxs-lookup"><span data-stu-id="4c577-116">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span> <span data-ttu-id="4c577-117">В документации по Visual Studio 2005 параметры для компилятора можно найти путем поиска «параметры компилятора» в индексе.</span><span class="sxs-lookup"><span data-stu-id="4c577-117">In the Visual Studio 2005 documentation, you can locate the options for the compiler by looking for "compiler options" in the index.</span></span>|  
|`extension`|<span data-ttu-id="4c577-118">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4c577-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="4c577-119">Предоставляет список разделенных точкой с запятой расширений имен файлов, используемых исходными файлами поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="4c577-119">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="4c577-120">Например «.cs».</span><span class="sxs-lookup"><span data-stu-id="4c577-120">For example, ".cs".</span></span>|  
|`language`|<span data-ttu-id="4c577-121">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4c577-121">Required attribute.</span></span><br /><br /> <span data-ttu-id="4c577-122">Предоставляет список разделенных точкой с запятой имен языков, поддерживаемых поставщиком языка.</span><span class="sxs-lookup"><span data-stu-id="4c577-122">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="4c577-123">Например «c#; cs; csharp».</span><span class="sxs-lookup"><span data-stu-id="4c577-123">For example, "c#;cs;csharp".</span></span>|  
|`type`|<span data-ttu-id="4c577-124">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4c577-124">Required attribute.</span></span><br /><br /> <span data-ttu-id="4c577-125">Указывает имя типа поставщика языка, включая имя сборки, содержащей реализацию этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="4c577-125">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="4c577-126">Имена типов должны отвечать требованиям, определенным в [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="4c577-126">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`warningLevel`|<span data-ttu-id="4c577-127">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4c577-127">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4c577-128">Задает уровень предупреждений компилятора по умолчанию; Определяет уровень, на котором поставщик языка рассматривает предупреждения компиляции как ошибки.</span><span class="sxs-lookup"><span data-stu-id="4c577-128">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c577-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4c577-129">Child Elements</span></span>  
  
|<span data-ttu-id="4c577-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="4c577-130">Element</span></span>|<span data-ttu-id="4c577-131">Описание</span><span class="sxs-lookup"><span data-stu-id="4c577-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c577-132">\<providerOption > элемент</span><span class="sxs-lookup"><span data-stu-id="4c577-132">\<providerOption> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|<span data-ttu-id="4c577-133">Задает атрибуты версии компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="4c577-133">Specifies compiler version attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4c577-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4c577-134">Parent Elements</span></span>  
  
|<span data-ttu-id="4c577-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="4c577-135">Element</span></span>|<span data-ttu-id="4c577-136">Описание</span><span class="sxs-lookup"><span data-stu-id="4c577-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c577-137">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="4c577-137">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="4c577-138">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4c577-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="4c577-139">\<System.CodeDom > элемент</span><span class="sxs-lookup"><span data-stu-id="4c577-139">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="4c577-140">Задает параметры конфигурации компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="4c577-140">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="4c577-141">\<компиляторы > элемент</span><span class="sxs-lookup"><span data-stu-id="4c577-141">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="4c577-142">Контейнер для элементов конфигурации компилятора; содержит ноль или более `<compiler>` элементов.</span><span class="sxs-lookup"><span data-stu-id="4c577-142">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c577-143">Примечания</span><span class="sxs-lookup"><span data-stu-id="4c577-143">Remarks</span></span>  
 <span data-ttu-id="4c577-144">Каждый `<compiler>` элемент задает атрибуты конфигурации компилятора для конкретного поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="4c577-144">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="4c577-145">Расширяет поставщика <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> класса для конкретного языка; `<compiler>` элемент определяет компилятора и генератора кода для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="4c577-145">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>  
  
 <span data-ttu-id="4c577-146">В .NET Framework начальные параметры компилятора определены файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4c577-146">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="4c577-147">Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="4c577-147">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="4c577-148">С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4c577-148">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
 <span data-ttu-id="4c577-149">Элементы компилятора в приложение или файл веб-конфигурации можно дополнить или переопределить параметры в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="4c577-149">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="4c577-150">Если для одного имени языка или расширения файла настроено более одной реализации поставщика, последняя подходящая конфигурация переопределяет всех ранее настроенных поставщиков для этого языка имя или расширение.</span><span class="sxs-lookup"><span data-stu-id="4c577-150">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="4c577-151">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="4c577-151">Configuration File</span></span>  
 <span data-ttu-id="4c577-152">Этот элемент может использоваться в файле конфигурации компьютера и файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="4c577-152">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c577-153">Пример</span><span class="sxs-lookup"><span data-stu-id="4c577-153">Example</span></span>  
 <span data-ttu-id="4c577-154">В приведенном ниже примере показан типичный элемент конфигурации компилятора.</span><span class="sxs-lookup"><span data-stu-id="4c577-154">The following example illustrates a typical compiler configuration element.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler  
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c577-155">См. также</span><span class="sxs-lookup"><span data-stu-id="4c577-155">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="4c577-156">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="4c577-156">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="4c577-157">\<компиляторы > элемент</span><span class="sxs-lookup"><span data-stu-id="4c577-157">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 [<span data-ttu-id="4c577-158">Указание полных имен типов</span><span class="sxs-lookup"><span data-stu-id="4c577-158">Specifying Fully Qualified Type Names</span></span>](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)  
 [<span data-ttu-id="4c577-159">Компилятор элемент для компиляторов для компиляции (схема параметров ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="4c577-159">compiler Element for compilers for compilation (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/en-us/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)
