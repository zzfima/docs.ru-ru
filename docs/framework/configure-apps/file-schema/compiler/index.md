---
title: Схема параметров поставщиков языков и компиляторов
ms.date: 03/30/2017
helpviewer_keywords:
- configuration settings [.NET Framework], compilers
- compiler configuration elements, schema
- compiler configuration elements
- language providers
- compiler configuration settings, schema
- configuration schema [.NET Framework], compiler settings
- language providers, settings schema
- compiler configuration settings
ms.assetid: c020b139-8699-4f0d-9ac9-70d0c5b2a8c8
ms.openlocfilehash: 5b1f9684ad26d4a03769af287fc8b0c0c7c4cc1a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088685"
---
# <a name="compiler-and-language-provider-settings-schema"></a><span data-ttu-id="96430-102">Схема параметров поставщиков языков и компиляторов</span><span class="sxs-lookup"><span data-stu-id="96430-102">Compiler and Language Provider Settings Schema</span></span>
<span data-ttu-id="96430-103">Параметры поставщиков языков и компиляторов определяют элементы конфигурации компиляторов для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="96430-103">Compiler and language provider settings specify compiler configuration elements for available language providers.</span></span> <span data-ttu-id="96430-104">Каждый элемент конфигурации компилятора определяет имя типа поставщика кода, параметры компилятора, названия поддерживаемых языков и поддерживаемые расширения имен файлов.</span><span class="sxs-lookup"><span data-stu-id="96430-104">Each compiler configuration element specifies the code provider type name, compiler parameters, supported language names, and supported file extensions.</span></span>  
  
<span data-ttu-id="96430-105">В .NET Framework начальные параметры компилятора определены файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="96430-105">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="96430-106">Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="96430-106">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="96430-107">С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="96430-107">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
<span data-ttu-id="96430-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="96430-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="96430-109">&nbsp;&nbsp;[ **\<System. codedom >** ](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="96430-109">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>\
<span data-ttu-id="96430-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<компилятора**](compilers-element.md) ></span><span class="sxs-lookup"><span data-stu-id="96430-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)</span></span>\
<span data-ttu-id="96430-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[ **компилятора >** ](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="96430-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)</span></span>
  
|<span data-ttu-id="96430-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="96430-112">Element</span></span>|<span data-ttu-id="96430-113">Описание</span><span class="sxs-lookup"><span data-stu-id="96430-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96430-114">\<system.codedom></span><span class="sxs-lookup"><span data-stu-id="96430-114">\<system.codedom></span></span>](system-codedom-element.md)|<span data-ttu-id="96430-115">Задает параметры конфигурации компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="96430-115">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="96430-116">\<compilers></span><span class="sxs-lookup"><span data-stu-id="96430-116">\<compilers></span></span>](compilers-element.md)|<span data-ttu-id="96430-117">Контейнер для элементов конфигурации компилятора; содержит ноль элементов [\<compiler>](compiler-element.md) или несколько.</span><span class="sxs-lookup"><span data-stu-id="96430-117">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
|[<span data-ttu-id="96430-118">\<compiler></span><span class="sxs-lookup"><span data-stu-id="96430-118">\<compiler></span></span>](compiler-element.md)|<span data-ttu-id="96430-119">Задает атрибуты конфигурации компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="96430-119">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="96430-120">Пример</span><span class="sxs-lookup"><span data-stu-id="96430-120">Example</span></span>  
 <span data-ttu-id="96430-121">В приведенном ниже примере показан типичный элемент конфигурации компилятора.</span><span class="sxs-lookup"><span data-stu-id="96430-121">The following example illustrates a typical compiler configuration element.</span></span>  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler  
          language="c#;cs;csharp"  
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""  
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="96430-122">См. также</span><span class="sxs-lookup"><span data-stu-id="96430-122">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="96430-123">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="96430-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="96430-124">Элемент \<compiler></span><span class="sxs-lookup"><span data-stu-id="96430-124">\<compiler> Element</span></span>](compiler-element.md)
