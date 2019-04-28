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
ms.openlocfilehash: 34753d538ff37ac4ae621f653d47ac92ac6749a0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705380"
---
# <a name="compiler-element"></a><span data-ttu-id="33c64-102">\<Компилятор > элемент</span><span class="sxs-lookup"><span data-stu-id="33c64-102">\<compiler> Element</span></span>

<span data-ttu-id="33c64-103">Задает атрибуты конфигурации компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="33c64-103">Specifies the compiler configuration attributes for a language provider.</span></span>

<span data-ttu-id="33c64-104">\<Элемент Configuration > \<элементу system.codedom > \<элемент compilers > \<компилятор > элемент</span><span class="sxs-lookup"><span data-stu-id="33c64-104">\<configuration Element> \<system.codedom Element> \<compilers Element> \<compiler> Element</span></span>

## <a name="syntax"></a><span data-ttu-id="33c64-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33c64-105">Syntax</span></span>

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="33c64-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="33c64-106">Attributes and Elements</span></span>

<span data-ttu-id="33c64-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="33c64-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="33c64-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="33c64-108">Attributes</span></span>

|<span data-ttu-id="33c64-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="33c64-109">Attribute</span></span>|<span data-ttu-id="33c64-110">Описание</span><span class="sxs-lookup"><span data-stu-id="33c64-110">Description</span></span>|
|---------------|-----------------|
|`compilerOptions`|<span data-ttu-id="33c64-111">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="33c64-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="33c64-112">Задает дополнительные аргументы компилятора для компиляции.</span><span class="sxs-lookup"><span data-stu-id="33c64-112">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="33c64-113">Значения для `compilerOptions` атрибут обычно перечислены в разделе параметров компилятора для компилятора.</span><span class="sxs-lookup"><span data-stu-id="33c64-113">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span>|
|`extension`|<span data-ttu-id="33c64-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="33c64-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="33c64-115">Предоставляет разделенный точками с запятой список расширений имен файлов, используемых исходных файлов для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="33c64-115">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="33c64-116">Например «.cs».</span><span class="sxs-lookup"><span data-stu-id="33c64-116">For example, ".cs".</span></span>|
|`language`|<span data-ttu-id="33c64-117">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="33c64-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="33c64-118">Предоставляет разделенный точками с запятой список имен языков, поддерживаемых поставщиком языка.</span><span class="sxs-lookup"><span data-stu-id="33c64-118">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="33c64-119">Например «c#; cs; csharp».</span><span class="sxs-lookup"><span data-stu-id="33c64-119">For example, "c#;cs;csharp".</span></span>|
|`type`|<span data-ttu-id="33c64-120">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="33c64-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="33c64-121">Указывает имя типа поставщика языка, включая имя сборки, содержащей реализацию поставщика.</span><span class="sxs-lookup"><span data-stu-id="33c64-121">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="33c64-122">Имя типа должны соответствовать требованиям, заданным в [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="33c64-122">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|
|`warningLevel`|<span data-ttu-id="33c64-123">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="33c64-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="33c64-124">Задает уровень предупреждений компилятора по умолчанию; Определяет уровень, на котором поставщик языка рассматривает предупреждения компиляции как ошибки.</span><span class="sxs-lookup"><span data-stu-id="33c64-124">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="33c64-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="33c64-125">Child Elements</span></span>

|<span data-ttu-id="33c64-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="33c64-126">Element</span></span>|<span data-ttu-id="33c64-127">Описание</span><span class="sxs-lookup"><span data-stu-id="33c64-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="33c64-128">\<providerOption > элемент</span><span class="sxs-lookup"><span data-stu-id="33c64-128">\<providerOption> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|<span data-ttu-id="33c64-129">Указывает атрибуты версии компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="33c64-129">Specifies compiler version attributes for a language provider.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="33c64-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="33c64-130">Parent Elements</span></span>

|<span data-ttu-id="33c64-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="33c64-131">Element</span></span>|<span data-ttu-id="33c64-132">Описание:</span><span class="sxs-lookup"><span data-stu-id="33c64-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="33c64-133">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="33c64-133">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="33c64-134">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="33c64-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|[<span data-ttu-id="33c64-135">\<System.CodeDom > элемент</span><span class="sxs-lookup"><span data-stu-id="33c64-135">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="33c64-136">Задает параметры конфигурации компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="33c64-136">Specifies compiler configuration settings for available language providers.</span></span>|
|[<span data-ttu-id="33c64-137">\<компиляторы > элемент</span><span class="sxs-lookup"><span data-stu-id="33c64-137">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="33c64-138">Контейнер для элементов конфигурации компилятора; содержит ноль или более `<compiler>` элементов.</span><span class="sxs-lookup"><span data-stu-id="33c64-138">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="33c64-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="33c64-139">Remarks</span></span>

<span data-ttu-id="33c64-140">Каждый `<compiler>` элемент задает атрибуты конфигурации компилятора для конкретного поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="33c64-140">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="33c64-141">Расширяет поставщика <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> класс для конкретного языка; `<compiler>` элемент определяет параметры генератора кода для поставщика языка и компилятора.</span><span class="sxs-lookup"><span data-stu-id="33c64-141">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>

<span data-ttu-id="33c64-142">В .NET Framework начальные параметры компилятора определены файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="33c64-142">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="33c64-143">Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="33c64-143">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="33c64-144">С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="33c64-144">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>

<span data-ttu-id="33c64-145">Элементы компилятора в приложение или файл веб-конфигурации можно дополнить или переопределить параметры в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="33c64-145">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="33c64-146">Если более чем одной реализации поставщика настроен для одного имени языка или расширения файла, последняя подходящая конфигурация переопределяет всех ранее настроенных поставщиков для этого языка имя или расширение.</span><span class="sxs-lookup"><span data-stu-id="33c64-146">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="33c64-147">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="33c64-147">Configuration File</span></span>

<span data-ttu-id="33c64-148">Этот элемент может использоваться в файле конфигурации компьютера и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="33c64-148">This element can be used in the machine configuration file and the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="33c64-149">Пример</span><span class="sxs-lookup"><span data-stu-id="33c64-149">Example</span></span>

<span data-ttu-id="33c64-150">Следующий пример иллюстрирует типичный элемент конфигурации компилятора:</span><span class="sxs-lookup"><span data-stu-id="33c64-150">The following example illustrates a typical compiler configuration element:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="33c64-151">См. также</span><span class="sxs-lookup"><span data-stu-id="33c64-151">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="33c64-152">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="33c64-152">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="33c64-153">\<компиляторы > элемент</span><span class="sxs-lookup"><span data-stu-id="33c64-153">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)
- [<span data-ttu-id="33c64-154">Указание полных имен типов</span><span class="sxs-lookup"><span data-stu-id="33c64-154">Specifying Fully Qualified Type Names</span></span>](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="33c64-155">[Элемент Compiler для компиляторов для compilation (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="33c64-155">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
