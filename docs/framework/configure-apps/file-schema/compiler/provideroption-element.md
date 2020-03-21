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
ms.openlocfilehash: c8ba5b9a0680f5e5102c13eb5bb0c1904a168c07
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155405"
---
# <a name="provideroption-element"></a><span data-ttu-id="578db-102">\<providerOption> Элемент</span><span class="sxs-lookup"><span data-stu-id="578db-102">\<providerOption> Element</span></span>
<span data-ttu-id="578db-103">Определяет атрибуты версии компилятора для поставщика языковых данных.</span><span class="sxs-lookup"><span data-stu-id="578db-103">Specifies the compiler version attributes for a language provider.</span></span>  

<span data-ttu-id="578db-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="578db-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="578db-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="578db-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>\
<span data-ttu-id="578db-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>составители**](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="578db-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)</span></span>\
<span data-ttu-id="578db-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<компилятор>**](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="578db-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)</span></span>\
<span data-ttu-id="578db-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**</span><span class="sxs-lookup"><span data-stu-id="578db-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**</span></span>

## <a name="syntax"></a><span data-ttu-id="578db-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="578db-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="578db-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="578db-110">Attributes and Elements</span></span>  
 <span data-ttu-id="578db-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="578db-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="578db-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="578db-112">Attributes</span></span>  
  
|<span data-ttu-id="578db-113">attribute</span><span class="sxs-lookup"><span data-stu-id="578db-113">Attribute</span></span>|<span data-ttu-id="578db-114">Описание</span><span class="sxs-lookup"><span data-stu-id="578db-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="578db-115">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="578db-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="578db-116">Упогоняет название опции; например, "CompilerVersion".</span><span class="sxs-lookup"><span data-stu-id="578db-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="578db-117">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="578db-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="578db-118">Упогоняет значение опциона; например, "v3.5".</span><span class="sxs-lookup"><span data-stu-id="578db-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="578db-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="578db-119">Child Elements</span></span>  
 <span data-ttu-id="578db-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="578db-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="578db-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="578db-121">Parent Elements</span></span>  
  
|<span data-ttu-id="578db-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="578db-122">Element</span></span>|<span data-ttu-id="578db-123">Описание</span><span class="sxs-lookup"><span data-stu-id="578db-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="578db-124">\<конфигурация> Элемент</span><span class="sxs-lookup"><span data-stu-id="578db-124">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="578db-125">Корневой элемент в любом файле конфигурации, который используется средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="578db-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="578db-126">\<system.codedom> Элемент</span><span class="sxs-lookup"><span data-stu-id="578db-126">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="578db-127">Задает параметры конфигурации компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="578db-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="578db-128">\<компиляторы> Элемент</span><span class="sxs-lookup"><span data-stu-id="578db-128">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="578db-129">Контейнер для элементов конфигурации компилятора; содержит ноль `<compiler>` или более элементов.</span><span class="sxs-lookup"><span data-stu-id="578db-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="578db-130">\<компилятор> Элемент</span><span class="sxs-lookup"><span data-stu-id="578db-130">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="578db-131">Задает атрибуты конфигурации компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="578db-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="578db-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="578db-132">Remarks</span></span>  
 <span data-ttu-id="578db-133">В версии .NET Framework 3.5 поставщики кода-объекта документа (CodeDOM) могут `<providerOption>` поддерживать определенные параметры поставщика с помощью элемента.</span><span class="sxs-lookup"><span data-stu-id="578db-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="578db-134">Рамочный 3.net Framework 3.5 включает в себя обновленные сборки .NET Framework 2.0 и предоставляет новую версию 3.5 сборок, содержащих новые типы.</span><span class="sxs-lookup"><span data-stu-id="578db-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="578db-135">Поставщики кода Microsoft C и Visual Basic содержатся в сборках .NET Framework 2.0, но были обновлены для поддержки компиляторов версии 3.5.</span><span class="sxs-lookup"><span data-stu-id="578db-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="578db-136">По умолчанию поставщики обновленного кода генерируют код для компиляторов версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="578db-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="578db-137">Элемент можно `<providerOption>` использовать для изменения целевой версии компилятора до 3.5.</span><span class="sxs-lookup"><span data-stu-id="578db-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="578db-138">Для этого укажите "CompilerVersion" `name` для атрибута и "v3.5" для атрибута. `value`</span><span class="sxs-lookup"><span data-stu-id="578db-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="578db-139">Вы должны предшествовать номеру версии с нижним случаем "v".</span><span class="sxs-lookup"><span data-stu-id="578db-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="578db-140">Вы можете сделать спецификацию `<providerOption>` версии глобальной, добавив элемент в .NET Framework 2.0 Machine.config или корневый файл Web.config.</span><span class="sxs-lookup"><span data-stu-id="578db-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="578db-141">Если вы обновите версию компилятора по умолчанию до 3.5 в файле Machine.config, вы можете изменить ее обратно до 2.0 на основе в расчете на одну заявку, используя `<providerOption>` элемент в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="578db-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="578db-142">Исполнители код-провайдеров CodeDOM могут обрабатывать пользовательские `providerOptions` параметры, <xref:System.Collections.Generic.IDictionary%602>предоставляя конструктору, который принимает параметр типа.</span><span class="sxs-lookup"><span data-stu-id="578db-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="578db-143">Пример</span><span class="sxs-lookup"><span data-stu-id="578db-143">Example</span></span>  
 <span data-ttu-id="578db-144">В следующем примере показано, как указать, что должна использоваться версия 3.5 поставщика кода С.</span><span class="sxs-lookup"><span data-stu-id="578db-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="578db-145">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="578db-145">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="578db-146">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="578db-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="578db-147">\<компиляторы> Элемент</span><span class="sxs-lookup"><span data-stu-id="578db-147">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="578db-148">Указание полных имен типов</span><span class="sxs-lookup"><span data-stu-id="578db-148">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="578db-149">[Элемент compiler для элемента compilers для элемента compilation (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="578db-149">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
