---
title: Элемент <compiler>
ms.date: 08/14/2018
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
ms.openlocfilehash: 46676f25597f85596598d6f67c98930971cb0447
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088054"
---
# <a name="compiler-element"></a><span data-ttu-id="f9026-102">\<>ного элемента компилятора</span><span class="sxs-lookup"><span data-stu-id="f9026-102">\<compiler> Element</span></span>

<span data-ttu-id="f9026-103">Задает атрибуты конфигурации компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="f9026-103">Specifies the compiler configuration attributes for a language provider.</span></span>

<span data-ttu-id="f9026-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f9026-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f9026-105">&nbsp;&nbsp;[ **\<System. codedom >** ](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="f9026-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>\
<span data-ttu-id="f9026-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<компилятора**](compilers-element.md) ></span><span class="sxs-lookup"><span data-stu-id="f9026-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)</span></span>\
<span data-ttu-id="f9026-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**компилятора >**</span><span class="sxs-lookup"><span data-stu-id="f9026-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compiler>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f9026-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9026-108">Syntax</span></span>

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f9026-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f9026-109">Attributes and Elements</span></span>

<span data-ttu-id="f9026-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f9026-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f9026-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f9026-111">Attributes</span></span>

|<span data-ttu-id="f9026-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f9026-112">Attribute</span></span>|<span data-ttu-id="f9026-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f9026-113">Description</span></span>|
|---------------|-----------------|
|`compilerOptions`|<span data-ttu-id="f9026-114">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f9026-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f9026-115">Задает дополнительные зависящие от компилятора аргументы для компиляции.</span><span class="sxs-lookup"><span data-stu-id="f9026-115">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="f9026-116">Значения для атрибута `compilerOptions`, как правило, перечислены в разделе параметров компилятора для компилятора.</span><span class="sxs-lookup"><span data-stu-id="f9026-116">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span>|
|`extension`|<span data-ttu-id="f9026-117">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f9026-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="f9026-118">Предоставляет разделенный точками с запятой список расширений имен файлов, используемых исходными файлами для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="f9026-118">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="f9026-119">Например, ". cs".</span><span class="sxs-lookup"><span data-stu-id="f9026-119">For example, ".cs".</span></span>|
|`language`|<span data-ttu-id="f9026-120">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f9026-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="f9026-121">Предоставляет разделенный точками с запятой список имен языков, поддерживаемых поставщиком языка.</span><span class="sxs-lookup"><span data-stu-id="f9026-121">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="f9026-122">Например, "c#; CS; CSharp".</span><span class="sxs-lookup"><span data-stu-id="f9026-122">For example, "c#;cs;csharp".</span></span>|
|`type`|<span data-ttu-id="f9026-123">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f9026-123">Required attribute.</span></span><br /><br /> <span data-ttu-id="f9026-124">Указывает имя типа поставщика языка, включая имя сборки, содержащей реализацию поставщика.</span><span class="sxs-lookup"><span data-stu-id="f9026-124">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="f9026-125">Имя типа должно соответствовать требованиям, определенным при [указании полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="f9026-125">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|
|`warningLevel`|<span data-ttu-id="f9026-126">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f9026-126">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f9026-127">Задает уровень предупреждений компилятора по умолчанию. Определяет уровень, на котором поставщик языка рассматривает предупреждения компиляции как ошибки.</span><span class="sxs-lookup"><span data-stu-id="f9026-127">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f9026-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f9026-128">Child Elements</span></span>

|<span data-ttu-id="f9026-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="f9026-129">Element</span></span>|<span data-ttu-id="f9026-130">Описание</span><span class="sxs-lookup"><span data-stu-id="f9026-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f9026-131">\<Провидероптион > элемент</span><span class="sxs-lookup"><span data-stu-id="f9026-131">\<providerOption> Element</span></span>](provideroption-element.md)|<span data-ttu-id="f9026-132">Указывает атрибуты версии компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="f9026-132">Specifies compiler version attributes for a language provider.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f9026-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f9026-133">Parent Elements</span></span>

|<span data-ttu-id="f9026-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="f9026-134">Element</span></span>|<span data-ttu-id="f9026-135">Описание</span><span class="sxs-lookup"><span data-stu-id="f9026-135">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f9026-136">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="f9026-136">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="f9026-137">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9026-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|[<span data-ttu-id="f9026-138">\<System. CodeDom > элемент</span><span class="sxs-lookup"><span data-stu-id="f9026-138">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="f9026-139">Задает параметры конфигурации компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="f9026-139">Specifies compiler configuration settings for available language providers.</span></span>|
|[<span data-ttu-id="f9026-140">\<компиляторы > элемент</span><span class="sxs-lookup"><span data-stu-id="f9026-140">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="f9026-141">Контейнер для элементов конфигурации компилятора; содержит ноль или более элементов `<compiler>`.</span><span class="sxs-lookup"><span data-stu-id="f9026-141">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f9026-142">Заметки</span><span class="sxs-lookup"><span data-stu-id="f9026-142">Remarks</span></span>

<span data-ttu-id="f9026-143">Каждый элемент `<compiler>` задает атрибуты конфигурации компилятора для конкретного поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="f9026-143">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="f9026-144">Поставщик расширяет класс <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> для конкретного языка; элемент `<compiler>` определяет параметры компилятора и генератора кода для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="f9026-144">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>

<span data-ttu-id="f9026-145">В .NET Framework начальные параметры компилятора определены файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f9026-145">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="f9026-146">Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="f9026-146">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="f9026-147">С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f9026-147">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>

<span data-ttu-id="f9026-148">Элементы компилятора в файле приложения или веб-конфигурации могут дополнять или переопределять параметры в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="f9026-148">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="f9026-149">Если для одного и того же имени языка или одного расширения файла настроено несколько реализаций поставщика, последняя конфигурация сопоставления переопределяет все предыдущие настроенные поставщики для этого имени языка или расширения файла.</span><span class="sxs-lookup"><span data-stu-id="f9026-149">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="f9026-150">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="f9026-150">Configuration File</span></span>

<span data-ttu-id="f9026-151">Этот элемент можно использовать в файле конфигурации компьютера и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="f9026-151">This element can be used in the machine configuration file and the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="f9026-152">Пример</span><span class="sxs-lookup"><span data-stu-id="f9026-152">Example</span></span>

<span data-ttu-id="f9026-153">В следующем примере показан типичный элемент конфигурации компилятора:</span><span class="sxs-lookup"><span data-stu-id="f9026-153">The following example illustrates a typical compiler configuration element:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f9026-154">См. также</span><span class="sxs-lookup"><span data-stu-id="f9026-154">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="f9026-155">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="f9026-155">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f9026-156">\<компиляторы > элемент</span><span class="sxs-lookup"><span data-stu-id="f9026-156">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="f9026-157">Указание полных имен типов</span><span class="sxs-lookup"><span data-stu-id="f9026-157">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="f9026-158">[Элемент компилятора для компиляторов для компиляции (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f9026-158">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
