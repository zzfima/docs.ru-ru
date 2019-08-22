---
title: Элемент <providerOption>
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
ms.openlocfilehash: 37f4d8c5eeacd82f8fc37179c478d026ca25f459
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664300"
---
# <a name="provideroption-element"></a><span data-ttu-id="b747a-102">\<Элемент > Провидероптион</span><span class="sxs-lookup"><span data-stu-id="b747a-102">\<providerOption> Element</span></span>
<span data-ttu-id="b747a-103">Указывает атрибуты версии компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="b747a-103">Specifies the compiler version attributes for a language provider.</span></span>  
  
 <span data-ttu-id="b747a-104">\<Элемент конфигурации ></span><span class="sxs-lookup"><span data-stu-id="b747a-104">\<configuration Element></span></span>  
<span data-ttu-id="b747a-105">\<Элемент System. CodeDom ></span><span class="sxs-lookup"><span data-stu-id="b747a-105">\<system.codedom Element></span></span>  
<span data-ttu-id="b747a-106">\<компилятор > элементов</span><span class="sxs-lookup"><span data-stu-id="b747a-106">\<compilers Element></span></span>  
<span data-ttu-id="b747a-107">\<Элемент > компилятора</span><span class="sxs-lookup"><span data-stu-id="b747a-107">\<compiler> Element</span></span>  
<span data-ttu-id="b747a-108">\<Элемент > Провидероптион</span><span class="sxs-lookup"><span data-stu-id="b747a-108">\<providerOption> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b747a-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b747a-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b747a-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b747a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b747a-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b747a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b747a-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b747a-112">Attributes</span></span>  
  
|<span data-ttu-id="b747a-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b747a-113">Attribute</span></span>|<span data-ttu-id="b747a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b747a-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="b747a-115">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b747a-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="b747a-116">Указывает имя параметра. Например, "Компилерверсион".</span><span class="sxs-lookup"><span data-stu-id="b747a-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="b747a-117">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b747a-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="b747a-118">Задает значение для параметра; Например, "v 3.5".</span><span class="sxs-lookup"><span data-stu-id="b747a-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b747a-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b747a-119">Child Elements</span></span>  
 <span data-ttu-id="b747a-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="b747a-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b747a-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b747a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b747a-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="b747a-122">Element</span></span>|<span data-ttu-id="b747a-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="b747a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b747a-124">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="b747a-124">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="b747a-125">Корневой элемент в любом файле конфигурации, который используется средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b747a-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="b747a-126">\<Элемент System. CodeDom ></span><span class="sxs-lookup"><span data-stu-id="b747a-126">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="b747a-127">Задает параметры конфигурации компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="b747a-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="b747a-128">\<Компиляторы > элемент</span><span class="sxs-lookup"><span data-stu-id="b747a-128">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="b747a-129">Контейнер для элементов конфигурации компилятора; содержит ноль или более `<compiler>` элементов.</span><span class="sxs-lookup"><span data-stu-id="b747a-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="b747a-130">Элемент \<compiler></span><span class="sxs-lookup"><span data-stu-id="b747a-130">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="b747a-131">Задает атрибуты конфигурации компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="b747a-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b747a-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="b747a-132">Remarks</span></span>  
 <span data-ttu-id="b747a-133">В .NET Framework версии 3,5 поставщики кода Code Document Object Model (CodeDOM) могут поддерживать параметры, зависящие от поставщика, с помощью `<providerOption>` элемента.</span><span class="sxs-lookup"><span data-stu-id="b747a-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="b747a-134">.NET Framework 3,5 включает обновленные сборки .NET Framework 2,0 и предоставляет новые сборки версии 3,5, содержащие новые типы.</span><span class="sxs-lookup"><span data-stu-id="b747a-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="b747a-135">Поставщики кода C# Microsoft и Visual Basic содержатся в сборках .NET Framework 2,0, но были обновлены для поддержки компиляторов версии 3,5.</span><span class="sxs-lookup"><span data-stu-id="b747a-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="b747a-136">По умолчанию обновленные поставщики кода создают код для компиляторов версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="b747a-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="b747a-137">С помощью `<providerOption>` элемента можно изменить целевую версию компилятора на 3,5.</span><span class="sxs-lookup"><span data-stu-id="b747a-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="b747a-138">Для этого укажите для атрибута значение "компилерверсион" `name` и "v 3.5". `value`</span><span class="sxs-lookup"><span data-stu-id="b747a-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="b747a-139">Перед номером версии необходимо указать строчную букву "v".</span><span class="sxs-lookup"><span data-stu-id="b747a-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="b747a-140">Глобальную спецификацию версии можно сделать, добавив `<providerOption>` элемент в .NET Framework 2,0 Machine. config или корневой файл Web. config.</span><span class="sxs-lookup"><span data-stu-id="b747a-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="b747a-141">Если вы обновляете версию компилятора по умолчанию до 3,5 в файле Machine. config, вы можете изменить ее обратно на 2,0 для каждого приложения, используя `<providerOption>` элемент в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b747a-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="b747a-142">Разработчики поставщика кода CodeDOM могут обрабатывать пользовательские параметры, предоставляя конструктор, принимающий `providerOptions` параметр типа. <xref:System.Collections.Generic.IDictionary%602></span><span class="sxs-lookup"><span data-stu-id="b747a-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b747a-143">Пример</span><span class="sxs-lookup"><span data-stu-id="b747a-143">Example</span></span>  
 <span data-ttu-id="b747a-144">В следующем примере показано, как указать, что должен использоваться поставщик C# кода версии 3,5.</span><span class="sxs-lookup"><span data-stu-id="b747a-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b747a-145">См. также</span><span class="sxs-lookup"><span data-stu-id="b747a-145">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="b747a-146">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="b747a-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b747a-147">\<Компиляторы > элемент</span><span class="sxs-lookup"><span data-stu-id="b747a-147">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="b747a-148">Указание полных имен типов</span><span class="sxs-lookup"><span data-stu-id="b747a-148">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="b747a-149">[Элемент компилятора для компиляторов для компиляции (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b747a-149">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
