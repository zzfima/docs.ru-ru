---
title: Элемент <system.codedom>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: 2bbd81867b3c20d8ac16bdd79fcc9a3cc7bbb55c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659689"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="5394a-102">\<Элемент System. CodeDom ></span><span class="sxs-lookup"><span data-stu-id="5394a-102">\<system.codedom> Element</span></span>
<span data-ttu-id="5394a-103">Задает параметры конфигурации компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="5394a-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
 <span data-ttu-id="5394a-104">\<Элемент Configuration ></span><span class="sxs-lookup"><span data-stu-id="5394a-104">\<configuration> Element</span></span>  
<span data-ttu-id="5394a-105">\<Элемент System. CodeDom ></span><span class="sxs-lookup"><span data-stu-id="5394a-105">\<system.codedom> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5394a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5394a-106">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5394a-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5394a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="5394a-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5394a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5394a-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5394a-109">Attributes</span></span>  
 <span data-ttu-id="5394a-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="5394a-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5394a-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5394a-111">Child Elements</span></span>  
  
|<span data-ttu-id="5394a-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="5394a-112">Element</span></span>|<span data-ttu-id="5394a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5394a-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5394a-114">\<compilers></span><span class="sxs-lookup"><span data-stu-id="5394a-114">\<compilers></span></span>](compilers-element.md)|<span data-ttu-id="5394a-115">Контейнер для элементов конфигурации компилятора; содержит ноль элементов [\<compiler>](compiler-element.md) или несколько.</span><span class="sxs-lookup"><span data-stu-id="5394a-115">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5394a-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5394a-116">Parent Elements</span></span>  
  
|<span data-ttu-id="5394a-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="5394a-117">Element</span></span>|<span data-ttu-id="5394a-118">Описание</span><span class="sxs-lookup"><span data-stu-id="5394a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5394a-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5394a-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="5394a-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5394a-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5394a-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="5394a-121">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="5394a-122">.NET Framework версии 2,0</span><span class="sxs-lookup"><span data-stu-id="5394a-122">.NET Framework Version 2.0</span></span>  
 <span data-ttu-id="5394a-123"><xref:Microsoft.CSharp.CSharpCodeProvider> [ ЭлементSystem.CodeDom>содержитпараметрыконфигурациикомпиляторадляпоставщиковязыков,установленныхнакомпьютеревдополнениекпоставщикампоумолчанию,которыеустанавливаютсявместе\<](system-codedom-element.md) с .NET Framework, например и <xref:Microsoft.VisualBasic.VBCodeProvider>.</span><span class="sxs-lookup"><span data-stu-id="5394a-123">The [\<system.codedom>](system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="5394a-124">Компилятор > элемент содержит ноль или больше [ \<элементов > компилятора](compiler-element.md) . [ \<](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="5394a-124">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="5394a-125">Каждый элемент > компилятора задает атрибуты конфигурации компилятора для конкретного поставщика языка. [ \<](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="5394a-125">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="5394a-126">Разработчики и поставщики компиляторов могут добавлять параметры конфигурации в файл конфигурации компьютера (Machine. config) для новой <xref:System.CodeDom.Compiler.CodeDomProvider> реализации.</span><span class="sxs-lookup"><span data-stu-id="5394a-126">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="5394a-127"><xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> Используйте метод для программного перечисления поставщиков языка по умолчанию и поставщиков языков, определенных параметрами конфигурации компилятора на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5394a-127">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5394a-128">В .NET Framework версиях 1,0 и 1,1 поставщики языка по умолчанию, предоставляемые .NET Framework, определяются в [ \<элементе компиляторы >](compilers-element.md) .</span><span class="sxs-lookup"><span data-stu-id="5394a-128">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](compilers-element.md) element.</span></span> <span data-ttu-id="5394a-129">В .NET Framework версии 2,0 поставщики языка по умолчанию не определяются в [ \<>ном](compilers-element.md) элементе компиляторов, но их можно <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> перечислить с помощью метода.</span><span class="sxs-lookup"><span data-stu-id="5394a-129">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="5394a-130">.NET Framework версии 1,0 и 1,1</span><span class="sxs-lookup"><span data-stu-id="5394a-130">.NET Framework Versions 1.0 and 1.1</span></span>  
 <span data-ttu-id="5394a-131">Элемент [System. CodeDom > содержит параметры конфигурации компилятора для поставщиков языков на компьютере. \<](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="5394a-131">The [\<system.codedom>](system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="5394a-132">Компилятор > элемент содержит ноль или больше [ \<элементов > компилятора](compiler-element.md) . [ \<](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="5394a-132">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="5394a-133">Каждый элемент > компилятора задает атрибуты конфигурации компилятора для конкретного поставщика языка. [ \<](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="5394a-133">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="5394a-134">В .NET Framework начальные параметры компилятора определены файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5394a-134">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="5394a-135">Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="5394a-135">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="5394a-136">С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5394a-136">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="5394a-137">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="5394a-137">Configuration File</span></span>  
 <span data-ttu-id="5394a-138">Этот элемент можно использовать в файле конфигурации компьютера и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="5394a-138">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5394a-139">Пример</span><span class="sxs-lookup"><span data-stu-id="5394a-139">Example</span></span>  
 <span data-ttu-id="5394a-140">В следующем примере показана типичная конфигурация компилятора.</span><span class="sxs-lookup"><span data-stu-id="5394a-140">The following example illustrates a typical compiler configuration.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler   
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=1.0.5000.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions=""  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5394a-141">См. также</span><span class="sxs-lookup"><span data-stu-id="5394a-141">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="5394a-142">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="5394a-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="5394a-143">Схема параметров компилятора и поставщика языков</span><span class="sxs-lookup"><span data-stu-id="5394a-143">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5394a-144">Элемент \<compiler></span><span class="sxs-lookup"><span data-stu-id="5394a-144">\<compiler> Element</span></span>](compiler-element.md)
