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
ms.openlocfilehash: 40a3c84e1deed4d215383670176623a6a79ac41d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155392"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="13bfe-102">\<system.codedom> Элемент</span><span class="sxs-lookup"><span data-stu-id="13bfe-102">\<system.codedom> Element</span></span>
<span data-ttu-id="13bfe-103">Задает параметры конфигурации компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="13bfe-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
[<span data-ttu-id="13bfe-104">**\<конфигурация>**</span><span class="sxs-lookup"><span data-stu-id="13bfe-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="13bfe-105">&nbsp;&nbsp;**\<system.codedom>**</span><span class="sxs-lookup"><span data-stu-id="13bfe-105">&nbsp;&nbsp;**\<system.codedom>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13bfe-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13bfe-106">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13bfe-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="13bfe-107">Attributes and Elements</span></span>  
 <span data-ttu-id="13bfe-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="13bfe-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13bfe-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="13bfe-109">Attributes</span></span>  
 <span data-ttu-id="13bfe-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="13bfe-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="13bfe-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="13bfe-111">Child Elements</span></span>  
  
|<span data-ttu-id="13bfe-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="13bfe-112">Element</span></span>|<span data-ttu-id="13bfe-113">Описание</span><span class="sxs-lookup"><span data-stu-id="13bfe-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13bfe-114">\<>составители</span><span class="sxs-lookup"><span data-stu-id="13bfe-114">\<compilers></span></span>](compilers-element.md)|<span data-ttu-id="13bfe-115">Контейнер для элементов конфигурации компилятора; содержит ноль или более [ \<элементов компил>ятора.](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="13bfe-115">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="13bfe-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="13bfe-116">Parent Elements</span></span>  
  
|<span data-ttu-id="13bfe-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="13bfe-117">Element</span></span>|<span data-ttu-id="13bfe-118">Описание</span><span class="sxs-lookup"><span data-stu-id="13bfe-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13bfe-119">\<конфигурация></span><span class="sxs-lookup"><span data-stu-id="13bfe-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="13bfe-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="13bfe-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13bfe-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="13bfe-121">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="13bfe-122">Рамочная версия .NET 2.0</span><span class="sxs-lookup"><span data-stu-id="13bfe-122">.NET Framework Version 2.0</span></span>  
 <span data-ttu-id="13bfe-123">Элемент [ \<system.codedom>](system-codedom-element.md) содержит настройки конфигурации компилятора для языковых провайдеров, установленных на компьютере <xref:Microsoft.CSharp.CSharpCodeProvider> в <xref:Microsoft.VisualBasic.VBCodeProvider>дополнение к поставщикам по умолчанию, которые установлены с помощью рамочной системы .NET, таких как и .</span><span class="sxs-lookup"><span data-stu-id="13bfe-123">The [\<system.codedom>](system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="13bfe-124">[ \<Компиляторы>](compilers-element.md) элемента содержат ноль или более [ \<элементов компилятора>.](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="13bfe-124">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="13bfe-125">Каждый [ \<компилятор>](compiler-element.md) элемент определяет атрибуты конфигурации компилятора для определенного поставщика языков.</span><span class="sxs-lookup"><span data-stu-id="13bfe-125">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="13bfe-126">Разработчики и поставщики компилятов могут добавлять настройки конфигурации <xref:System.CodeDom.Compiler.CodeDomProvider> в файл конфигурации машины (Machine.config) для новой реализации.</span><span class="sxs-lookup"><span data-stu-id="13bfe-126">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="13bfe-127">Используйте <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> метод для программного перечисления как поставщиков языков по умолчанию, так и поставщиков языков, определенных настройками конфигурации компилятора на компьютере.</span><span class="sxs-lookup"><span data-stu-id="13bfe-127">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13bfe-128">В версиях .NET Framework 1.0 и 1.1 поставщики языков по умолчанию, поставляемые рамочной системой .NET, идентифицируются в [ \<компиляторах>](compilers-element.md) элементе.</span><span class="sxs-lookup"><span data-stu-id="13bfe-128">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](compilers-element.md) element.</span></span> <span data-ttu-id="13bfe-129">В версии 2.0.NET Framework поставщики языков по умолчанию не идентифицируются в [ \<компиляторах>](compilers-element.md) элементом, но могут быть перечислены с помощью метода. <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A></span><span class="sxs-lookup"><span data-stu-id="13bfe-129">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="13bfe-130">Рамочные версии .NET 1.0 и 1.1</span><span class="sxs-lookup"><span data-stu-id="13bfe-130">.NET Framework Versions 1.0 and 1.1</span></span>  
 <span data-ttu-id="13bfe-131">Элемент [ \<system.codedom>](system-codedom-element.md) содержит настройки конфигурации компилятора для языковых провайдеров на компьютере.</span><span class="sxs-lookup"><span data-stu-id="13bfe-131">The [\<system.codedom>](system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="13bfe-132">[ \<Компиляторы>](compilers-element.md) элемента содержат ноль или более [ \<элементов компилятора>.](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="13bfe-132">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="13bfe-133">Каждый [ \<компилятор>](compiler-element.md) элемент определяет атрибуты конфигурации компилятора для определенного поставщика языков.</span><span class="sxs-lookup"><span data-stu-id="13bfe-133">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="13bfe-134">В .NET Framework начальные параметры компилятора определены файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="13bfe-134">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="13bfe-135">Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="13bfe-135">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="13bfe-136">С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="13bfe-136">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="13bfe-137">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="13bfe-137">Configuration File</span></span>  
 <span data-ttu-id="13bfe-138">Этот элемент можно использовать в файле конфигурации машины и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="13bfe-138">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13bfe-139">Пример</span><span class="sxs-lookup"><span data-stu-id="13bfe-139">Example</span></span>  
 <span data-ttu-id="13bfe-140">Следующий пример иллюстрирует типичную конфигурацию компилятора.</span><span class="sxs-lookup"><span data-stu-id="13bfe-140">The following example illustrates a typical compiler configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="13bfe-141">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="13bfe-141">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="13bfe-142">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="13bfe-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="13bfe-143">Схема настройки компилятора и языкового провайдера</span><span class="sxs-lookup"><span data-stu-id="13bfe-143">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="13bfe-144">\<компилятор> Элемент</span><span class="sxs-lookup"><span data-stu-id="13bfe-144">\<compiler> Element</span></span>](compiler-element.md)
