---
title: '&lt;providerOption&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 75cc2003a88cc7be467b9062c37b6b5d9eb82f53
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43877980"
---
# <a name="ltprovideroptiongt-element"></a><span data-ttu-id="09ddc-102">&lt;providerOption&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="09ddc-102">&lt;providerOption&gt; Element</span></span>
<span data-ttu-id="09ddc-103">Задает атрибуты версии компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="09ddc-103">Specifies the compiler version attributes for a language provider.</span></span>  
  
 <span data-ttu-id="09ddc-104">\<Элемент Configuration ></span><span class="sxs-lookup"><span data-stu-id="09ddc-104">\<configuration Element></span></span>  
<span data-ttu-id="09ddc-105">\<Элемент System.CodeDom ></span><span class="sxs-lookup"><span data-stu-id="09ddc-105">\<system.codedom Element></span></span>  
<span data-ttu-id="09ddc-106">\<Элемент compilers ></span><span class="sxs-lookup"><span data-stu-id="09ddc-106">\<compilers Element></span></span>  
<span data-ttu-id="09ddc-107">\<Компилятор > элемент</span><span class="sxs-lookup"><span data-stu-id="09ddc-107">\<compiler> Element</span></span>  
<span data-ttu-id="09ddc-108">\<providerOption > элемент</span><span class="sxs-lookup"><span data-stu-id="09ddc-108">\<providerOption> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09ddc-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09ddc-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09ddc-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="09ddc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="09ddc-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="09ddc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09ddc-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="09ddc-112">Attributes</span></span>  
  
|<span data-ttu-id="09ddc-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="09ddc-113">Attribute</span></span>|<span data-ttu-id="09ddc-114">Описание</span><span class="sxs-lookup"><span data-stu-id="09ddc-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="09ddc-115">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="09ddc-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="09ddc-116">Задает имя параметра; Например, «CompilerVersion».</span><span class="sxs-lookup"><span data-stu-id="09ddc-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="09ddc-117">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="09ddc-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="09ddc-118">Указывает значение для параметра; Например «v3.5».</span><span class="sxs-lookup"><span data-stu-id="09ddc-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09ddc-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="09ddc-119">Child Elements</span></span>  
 <span data-ttu-id="09ddc-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="09ddc-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="09ddc-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="09ddc-121">Parent Elements</span></span>  
  
|<span data-ttu-id="09ddc-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="09ddc-122">Element</span></span>|<span data-ttu-id="09ddc-123">Описание</span><span class="sxs-lookup"><span data-stu-id="09ddc-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09ddc-124">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="09ddc-124">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="09ddc-125">Корневой элемент в любом файле конфигурации, который используется средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="09ddc-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="09ddc-126">\<System.CodeDom > элемент</span><span class="sxs-lookup"><span data-stu-id="09ddc-126">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="09ddc-127">Задает параметры конфигурации компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="09ddc-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="09ddc-128">\<компиляторы > элемент</span><span class="sxs-lookup"><span data-stu-id="09ddc-128">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="09ddc-129">Контейнер для элементов конфигурации компилятора; содержит ноль или более `<compiler>` элементов.</span><span class="sxs-lookup"><span data-stu-id="09ddc-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="09ddc-130">Элемент \<compiler></span><span class="sxs-lookup"><span data-stu-id="09ddc-130">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="09ddc-131">Задает атрибуты конфигурации компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="09ddc-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09ddc-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="09ddc-132">Remarks</span></span>  
 <span data-ttu-id="09ddc-133">В .NET Framework версии 3.5, поставщики код объектной модели документов кода (CodeDOM) могут поддерживать параметры поставщика с помощью `<providerOption>` элемент.</span><span class="sxs-lookup"><span data-stu-id="09ddc-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="09ddc-134">.NET Framework 3.5, включает обновленные сборки .NET Framework 2.0 и предоставляет новые сборки версии 3.5, которые содержат новые типы.</span><span class="sxs-lookup"><span data-stu-id="09ddc-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="09ddc-135">Поставщики кода Microsoft C# и Visual Basic, находятся в сборках .NET Framework 2.0, но были обновлены для поддержки компиляторы версии 3.5.</span><span class="sxs-lookup"><span data-stu-id="09ddc-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="09ddc-136">По умолчанию поставщики обновленный код создания кода для компиляторов версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="09ddc-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="09ddc-137">Можно использовать `<providerOption>` элемент для изменения целевой версии компилятора 3.5.</span><span class="sxs-lookup"><span data-stu-id="09ddc-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="09ddc-138">Чтобы сделать это, укажите «Версию компилятора» для `name` атрибут и «v3.5» для `value` атрибута.</span><span class="sxs-lookup"><span data-stu-id="09ddc-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="09ddc-139">Должен предшествовать номер версии с прописной буквы «v».</span><span class="sxs-lookup"><span data-stu-id="09ddc-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="09ddc-140">Спецификация версии можно сделать глобальным путем добавления `<providerOption>` элемент в .NET Framework 2.0 Machine.config или корневом файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="09ddc-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="09ddc-141">Если вы не обновите версию компилятора по умолчанию 3.5 в файле Machine.config, можно изменить его обратно в 2.0 на основе каждого приложения с помощью `<providerOption>` элемент в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="09ddc-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="09ddc-142">Реализации поставщика кода codeDOM может обрабатывать настраиваемых параметров, предоставляя конструктор, принимающий `providerOptions` параметр типа <xref:System.Collections.Generic.IDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="09ddc-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09ddc-143">Пример</span><span class="sxs-lookup"><span data-stu-id="09ddc-143">Example</span></span>  
 <span data-ttu-id="09ddc-144">Ниже приведен пример, как указать, следует использовать поставщика кода C# версии 3.5.</span><span class="sxs-lookup"><span data-stu-id="09ddc-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="09ddc-145">См. также</span><span class="sxs-lookup"><span data-stu-id="09ddc-145">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="09ddc-146">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="09ddc-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="09ddc-147">\<компиляторы > элемент</span><span class="sxs-lookup"><span data-stu-id="09ddc-147">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 [<span data-ttu-id="09ddc-148">Указание полных имен типов</span><span class="sxs-lookup"><span data-stu-id="09ddc-148">Specifying Fully Qualified Type Names</span></span>](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)  
 [<span data-ttu-id="09ddc-149">Элемент Compiler для компиляторов для compilation (схема параметров ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="09ddc-149">compiler Element for compilers for compilation (ASP.NET Settings Schema)</span></span>](https://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)
