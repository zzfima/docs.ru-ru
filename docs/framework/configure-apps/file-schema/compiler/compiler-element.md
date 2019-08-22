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
ms.openlocfilehash: 80eea3373e2f4b7e45ebeb31dd6552ea02c109e1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659735"
---
# <a name="compiler-element"></a><span data-ttu-id="e04f6-102">\<Элемент > компилятора</span><span class="sxs-lookup"><span data-stu-id="e04f6-102">\<compiler> Element</span></span>

<span data-ttu-id="e04f6-103">Задает атрибуты конфигурации компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="e04f6-103">Specifies the compiler configuration attributes for a language provider.</span></span>

<span data-ttu-id="e04f6-104">\<Элемент Configuration > \<элемент System. CodeDom > \<элемент компиляторы > \<>ного элемента компилятора</span><span class="sxs-lookup"><span data-stu-id="e04f6-104">\<configuration Element> \<system.codedom Element> \<compilers Element> \<compiler> Element</span></span>

## <a name="syntax"></a><span data-ttu-id="e04f6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e04f6-105">Syntax</span></span>

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e04f6-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e04f6-106">Attributes and Elements</span></span>

<span data-ttu-id="e04f6-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e04f6-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e04f6-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e04f6-108">Attributes</span></span>

|<span data-ttu-id="e04f6-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e04f6-109">Attribute</span></span>|<span data-ttu-id="e04f6-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e04f6-110">Description</span></span>|
|---------------|-----------------|
|`compilerOptions`|<span data-ttu-id="e04f6-111">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e04f6-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e04f6-112">Задает дополнительные зависящие от компилятора аргументы для компиляции.</span><span class="sxs-lookup"><span data-stu-id="e04f6-112">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="e04f6-113">Значения для `compilerOptions` атрибута обычно перечислены в разделе параметров компилятора для компилятора.</span><span class="sxs-lookup"><span data-stu-id="e04f6-113">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span>|
|`extension`|<span data-ttu-id="e04f6-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e04f6-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="e04f6-115">Предоставляет разделенный точками с запятой список расширений имен файлов, используемых исходными файлами для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="e04f6-115">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="e04f6-116">Например, ". cs".</span><span class="sxs-lookup"><span data-stu-id="e04f6-116">For example, ".cs".</span></span>|
|`language`|<span data-ttu-id="e04f6-117">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e04f6-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="e04f6-118">Предоставляет разделенный точками с запятой список имен языков, поддерживаемых поставщиком языка.</span><span class="sxs-lookup"><span data-stu-id="e04f6-118">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="e04f6-119">Например, "c#; CS; CSharp".</span><span class="sxs-lookup"><span data-stu-id="e04f6-119">For example, "c#;cs;csharp".</span></span>|
|`type`|<span data-ttu-id="e04f6-120">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e04f6-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="e04f6-121">Указывает имя типа поставщика языка, включая имя сборки, содержащей реализацию поставщика.</span><span class="sxs-lookup"><span data-stu-id="e04f6-121">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="e04f6-122">Имя типа должно соответствовать требованиям, определенным при [указании полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="e04f6-122">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|
|`warningLevel`|<span data-ttu-id="e04f6-123">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e04f6-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e04f6-124">Задает уровень предупреждений компилятора по умолчанию. Определяет уровень, на котором поставщик языка рассматривает предупреждения компиляции как ошибки.</span><span class="sxs-lookup"><span data-stu-id="e04f6-124">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e04f6-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e04f6-125">Child Elements</span></span>

|<span data-ttu-id="e04f6-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="e04f6-126">Element</span></span>|<span data-ttu-id="e04f6-127">Описание</span><span class="sxs-lookup"><span data-stu-id="e04f6-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e04f6-128">\<Элемент > Провидероптион</span><span class="sxs-lookup"><span data-stu-id="e04f6-128">\<providerOption> Element</span></span>](provideroption-element.md)|<span data-ttu-id="e04f6-129">Указывает атрибуты версии компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="e04f6-129">Specifies compiler version attributes for a language provider.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e04f6-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e04f6-130">Parent Elements</span></span>

|<span data-ttu-id="e04f6-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="e04f6-131">Element</span></span>|<span data-ttu-id="e04f6-132">Описание:</span><span class="sxs-lookup"><span data-stu-id="e04f6-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e04f6-133">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="e04f6-133">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="e04f6-134">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e04f6-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|[<span data-ttu-id="e04f6-135">\<Элемент System. CodeDom ></span><span class="sxs-lookup"><span data-stu-id="e04f6-135">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="e04f6-136">Задает параметры конфигурации компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="e04f6-136">Specifies compiler configuration settings for available language providers.</span></span>|
|[<span data-ttu-id="e04f6-137">\<Компиляторы > элемент</span><span class="sxs-lookup"><span data-stu-id="e04f6-137">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="e04f6-138">Контейнер для элементов конфигурации компилятора; содержит ноль или более `<compiler>` элементов.</span><span class="sxs-lookup"><span data-stu-id="e04f6-138">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e04f6-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="e04f6-139">Remarks</span></span>

<span data-ttu-id="e04f6-140">Каждый `<compiler>` элемент задает атрибуты конфигурации компилятора для конкретного поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="e04f6-140">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="e04f6-141">Поставщик расширяет <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> класс для конкретного языка `<compiler>` ; элемент определяет параметры компилятора и генератора кода для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="e04f6-141">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>

<span data-ttu-id="e04f6-142">В .NET Framework начальные параметры компилятора определены файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e04f6-142">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="e04f6-143">Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="e04f6-143">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="e04f6-144">С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e04f6-144">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>

<span data-ttu-id="e04f6-145">Элементы компилятора в файле приложения или веб-конфигурации могут дополнять или переопределять параметры в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="e04f6-145">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="e04f6-146">Если для одного и того же имени языка или одного расширения файла настроено несколько реализаций поставщика, последняя конфигурация сопоставления переопределяет все предыдущие настроенные поставщики для этого имени языка или расширения файла.</span><span class="sxs-lookup"><span data-stu-id="e04f6-146">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="e04f6-147">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="e04f6-147">Configuration File</span></span>

<span data-ttu-id="e04f6-148">Этот элемент можно использовать в файле конфигурации компьютера и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="e04f6-148">This element can be used in the machine configuration file and the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="e04f6-149">Пример</span><span class="sxs-lookup"><span data-stu-id="e04f6-149">Example</span></span>

<span data-ttu-id="e04f6-150">В следующем примере показан типичный элемент конфигурации компилятора:</span><span class="sxs-lookup"><span data-stu-id="e04f6-150">The following example illustrates a typical compiler configuration element:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e04f6-151">См. также</span><span class="sxs-lookup"><span data-stu-id="e04f6-151">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="e04f6-152">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e04f6-152">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e04f6-153">\<Компиляторы > элемент</span><span class="sxs-lookup"><span data-stu-id="e04f6-153">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="e04f6-154">Указание полных имен типов</span><span class="sxs-lookup"><span data-stu-id="e04f6-154">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="e04f6-155">[Элемент компилятора для компиляторов для компиляции (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e04f6-155">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
