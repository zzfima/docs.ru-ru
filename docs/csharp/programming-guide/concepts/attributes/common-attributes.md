---
title: Общие атрибуты (C#)
ms.date: 07/20/2015
ms.assetid: 785a0526-6c0e-4599-8c61-ccdc88dd9965
ms.openlocfilehash: 7988dad410c6e51869ec9d7e40d94e874443a5f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398385"
---
# <a name="common-attributes-c"></a><span data-ttu-id="aa97f-102">Общие атрибуты (C#)</span><span class="sxs-lookup"><span data-stu-id="aa97f-102">Common Attributes (C#)</span></span>
<span data-ttu-id="aa97f-103">В этом разделе описываются атрибуты, которые чаще всего используются в программах C#.</span><span class="sxs-lookup"><span data-stu-id="aa97f-103">This topic describes the attributes that are most commonly used in C# programs.</span></span>  
  
- [<span data-ttu-id="aa97f-104">Глобальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa97f-104">Global Attributes</span></span>](#Global)  
  
- [<span data-ttu-id="aa97f-105">Атрибут Obsolete</span><span class="sxs-lookup"><span data-stu-id="aa97f-105">Obsolete Attribute</span></span>](#Obsolete)  
  
- [<span data-ttu-id="aa97f-106">Атрибут Conditional</span><span class="sxs-lookup"><span data-stu-id="aa97f-106">Conditional Attribute</span></span>](#Conditional)  
  
- [<span data-ttu-id="aa97f-107">Информационные атрибуты вызывающего объекта</span><span class="sxs-lookup"><span data-stu-id="aa97f-107">Caller Info Attributes</span></span>](#CallerInfo)  
  
## <a name="Global"></a> <span data-ttu-id="aa97f-108">Глобальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa97f-108">Global Attributes</span></span>  
 <span data-ttu-id="aa97f-109">Большинство атрибутов применяется к определенным элементам языка, таким как классы или методы. Тем не менее некоторые атрибуты являются глобальными — они применяются ко всей сборке или модулю.</span><span class="sxs-lookup"><span data-stu-id="aa97f-109">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="aa97f-110">Например, атрибут <xref:System.Reflection.AssemblyVersionAttribute> можно использовать для встраивания сведений о версии в сборку, например следующим образом:</span><span class="sxs-lookup"><span data-stu-id="aa97f-110">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>  
  
```csharp  
[assembly: AssemblyVersion("1.0.0.0")]  
```  
  
 <span data-ttu-id="aa97f-111">Глобальные атрибуты отображаются в исходном коде после любых директив `using` верхнего уровня и перед всеми объявлениями типов, модулей или пространств имен.</span><span class="sxs-lookup"><span data-stu-id="aa97f-111">Global attributes appear in the source code after any top-level `using` directives and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="aa97f-112">Глобальные атрибуты могут содержаться в нескольких исходных файлах, однако эти файлы должны быть скомпилированы за один проход компиляции.</span><span class="sxs-lookup"><span data-stu-id="aa97f-112">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="aa97f-113">В проектах C# глобальные атрибуты помещаются в файл AssemblyInfo.cs.</span><span class="sxs-lookup"><span data-stu-id="aa97f-113">In C# projects, global attributes are put in the AssemblyInfo.cs file.</span></span>  
  
 <span data-ttu-id="aa97f-114">Атрибуты сборки — это значения, которые предоставляют сведения о сборке.</span><span class="sxs-lookup"><span data-stu-id="aa97f-114">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="aa97f-115">Они делятся на следующие категории:</span><span class="sxs-lookup"><span data-stu-id="aa97f-115">They fall into the following categories:</span></span>  
  
- <span data-ttu-id="aa97f-116">Атрибуты удостоверения сборки</span><span class="sxs-lookup"><span data-stu-id="aa97f-116">Assembly identity attributes</span></span>  
  
- <span data-ttu-id="aa97f-117">Информационные атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa97f-117">Informational attributes</span></span>  
  
- <span data-ttu-id="aa97f-118">Атрибуты манифеста сборки</span><span class="sxs-lookup"><span data-stu-id="aa97f-118">Assembly manifest attributes</span></span>  
  
### <a name="assembly-identity-attributes"></a><span data-ttu-id="aa97f-119">Атрибуты удостоверения сборки</span><span class="sxs-lookup"><span data-stu-id="aa97f-119">Assembly Identity Attributes</span></span>  
 <span data-ttu-id="aa97f-120">Три атрибута (со строгим именем, если оно применимо) определяют удостоверение сборки: имя, версию, язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="aa97f-120">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="aa97f-121">Эти атрибуты формируют полное имя сборки и являются обязательными при ссылке на нее в коде.</span><span class="sxs-lookup"><span data-stu-id="aa97f-121">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="aa97f-122">Атрибуты можно использовать для задания версии сборки и языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="aa97f-122">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="aa97f-123">Однако значение имени задается компилятором, в интегрированной среде разработки Visual Studio, в [диалоговом окне сведений о сборке](/visualstudio/ide/reference/assembly-information-dialog-box) или в компоновщике сборок (Al.exe) при создании сборки на основе файла, содержащего манифест сборки.</span><span class="sxs-lookup"><span data-stu-id="aa97f-123">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created, based on the file that contains the assembly manifest.</span></span> <span data-ttu-id="aa97f-124">Атрибут <xref:System.Reflection.AssemblyFlagsAttribute> указывает, могут ли сосуществовать несколько копий сборки.</span><span class="sxs-lookup"><span data-stu-id="aa97f-124">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>  
  
 <span data-ttu-id="aa97f-125">В следующей таблице приведены атрибуты удостоверения.</span><span class="sxs-lookup"><span data-stu-id="aa97f-125">The following table shows the identity attributes.</span></span>  
  
|<span data-ttu-id="aa97f-126">attribute</span><span class="sxs-lookup"><span data-stu-id="aa97f-126">Attribute</span></span>|<span data-ttu-id="aa97f-127">Назначение</span><span class="sxs-lookup"><span data-stu-id="aa97f-127">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyName>|<span data-ttu-id="aa97f-128">Полностью описывает удостоверение сборки.</span><span class="sxs-lookup"><span data-stu-id="aa97f-128">Fully describes the identity of an assembly.</span></span>|  
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="aa97f-129">Задает версию сборки.</span><span class="sxs-lookup"><span data-stu-id="aa97f-129">Specifies the version of an assembly.</span></span>|  
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="aa97f-130">Указывает, какой язык и региональные параметры поддерживает сборка.</span><span class="sxs-lookup"><span data-stu-id="aa97f-130">Specifies which culture the assembly supports.</span></span>|  
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="aa97f-131">Указывает, поддерживает ли сборка параллельное выполнение на одном компьютере, в одном процессе или в одном домене приложения.</span><span class="sxs-lookup"><span data-stu-id="aa97f-131">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|  
  
### <a name="informational-attributes"></a><span data-ttu-id="aa97f-132">Информационные атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa97f-132">Informational Attributes</span></span>  
 <span data-ttu-id="aa97f-133">Информационные атрибуты можно использовать для предоставления дополнительных сведений о компании или продукте в сборке.</span><span class="sxs-lookup"><span data-stu-id="aa97f-133">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="aa97f-134">В следующей таблице показаны информационные атрибуты, определенные в пространстве имен <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aa97f-134">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>  
  
|<span data-ttu-id="aa97f-135">attribute</span><span class="sxs-lookup"><span data-stu-id="aa97f-135">Attribute</span></span>|<span data-ttu-id="aa97f-136">Назначение</span><span class="sxs-lookup"><span data-stu-id="aa97f-136">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="aa97f-137">Определяет настраиваемый атрибут, задающий имя продукта для манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="aa97f-137">Defines a custom attribute that specifies a product name for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="aa97f-138">Определяет настраиваемый атрибут, задающий товарный знак для манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="aa97f-138">Defines a custom attribute that specifies a trademark for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="aa97f-139">Определяет настраиваемый атрибут, задающий информационную версию для манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="aa97f-139">Defines a custom attribute that specifies an informational version for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="aa97f-140">Определяет настраиваемый атрибут, задающий название организации для манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="aa97f-140">Defines a custom attribute that specifies a company name for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="aa97f-141">Определяет настраиваемый атрибут, задающий уведомление об авторских правах для манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="aa97f-141">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="aa97f-142">Дает компилятору указание использовать определенный номер версии для ресурса версии файла Win32.</span><span class="sxs-lookup"><span data-stu-id="aa97f-142">Instructs the compiler to use a specific version number for the Win32 file version resource.</span></span>|  
|<xref:System.CLSCompliantAttribute>|<span data-ttu-id="aa97f-143">Указывает, соответствует ли сборка спецификации CLS.</span><span class="sxs-lookup"><span data-stu-id="aa97f-143">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|  
  
### <a name="assembly-manifest-attributes"></a><span data-ttu-id="aa97f-144">Атрибуты манифеста сборки</span><span class="sxs-lookup"><span data-stu-id="aa97f-144">Assembly Manifest Attributes</span></span>  
 <span data-ttu-id="aa97f-145">Атрибуты манифеста сборки можно использовать для предоставления сведений в манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="aa97f-145">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="aa97f-146">К ним относится заголовок, описание, псевдоним по умолчанию и конфигурация.</span><span class="sxs-lookup"><span data-stu-id="aa97f-146">This includes title, description, default alias, and configuration.</span></span> <span data-ttu-id="aa97f-147">В следующей таблице показаны атрибуты манифеста сборки, определенные в пространстве имен <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aa97f-147">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>  
  
|<span data-ttu-id="aa97f-148">attribute</span><span class="sxs-lookup"><span data-stu-id="aa97f-148">Attribute</span></span>|<span data-ttu-id="aa97f-149">Назначение</span><span class="sxs-lookup"><span data-stu-id="aa97f-149">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="aa97f-150">Определяет настраиваемый атрибут, задающий название сборки для манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="aa97f-150">Defines a custom attribute that specifies an assembly title for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="aa97f-151">Определяет настраиваемый атрибут, задающий описание сборки для манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="aa97f-151">Defines a custom attribute that specifies an assembly description for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="aa97f-152">Определяет настраиваемый атрибут, задающий конфигурацию сборки для манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="aa97f-152">Defines a custom attribute that specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="aa97f-153">Определяет понятный псевдоним по умолчанию для манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="aa97f-153">Defines a friendly default alias for an assembly manifest</span></span>|  
  
## <a name="Obsolete"></a> <span data-ttu-id="aa97f-154">Атрибут Obsolete</span><span class="sxs-lookup"><span data-stu-id="aa97f-154">Obsolete Attribute</span></span>  
 <span data-ttu-id="aa97f-155">Атрибут `Obsolete` помечает сущность программы как нерекомендуемую для использования.</span><span class="sxs-lookup"><span data-stu-id="aa97f-155">The `Obsolete` attribute marks a program entity as one that is no longer recommended for use.</span></span> <span data-ttu-id="aa97f-156">Каждый случай использования сущности, помеченной как устаревшая, будет приводить к созданию предупреждения или сообщения об ошибке в зависимости от настройки атрибута.</span><span class="sxs-lookup"><span data-stu-id="aa97f-156">Each use of an entity marked obsolete will subsequently generate a warning or an error, depending on how the attribute is configured.</span></span> <span data-ttu-id="aa97f-157">Пример:</span><span class="sxs-lookup"><span data-stu-id="aa97f-157">For example:</span></span>  
  
```csharp  
[System.Obsolete("use class B")]  
class A  
{  
    public void Method() { }  
}  
class B  
{  
    [System.Obsolete("use NewMethod", true)]  
    public void OldMethod() { }  
    public void NewMethod() { }  
}  
```  
  
 <span data-ttu-id="aa97f-158">В этом примере атрибут `Obsolete` применяется к классу `A` и к методу `B.OldMethod`.</span><span class="sxs-lookup"><span data-stu-id="aa97f-158">In this example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="aa97f-159">Поскольку для второго аргумента конструктора атрибутов, примененного к `B.OldMethod`, задано значение `true`, этот метод будет вызывать ошибку компилятора, тогда как при использовании класса `A` будет просто создаваться предупреждение.</span><span class="sxs-lookup"><span data-stu-id="aa97f-159">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="aa97f-160">При этом вызов `B.NewMethod` не создает предупреждений или ошибок.</span><span class="sxs-lookup"><span data-stu-id="aa97f-160">Calling `B.NewMethod`, however, produces no warning or error.</span></span>  
  
 <span data-ttu-id="aa97f-161">Строка, предоставленная в качестве первого аргумента конструктору атрибута, будет отображаться как часть предупреждения или ошибки.</span><span class="sxs-lookup"><span data-stu-id="aa97f-161">The string provided as the first argument to attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="aa97f-162">Например, при использовании с предыдущими определениями следующий код создает два предупреждения и одну ошибку:</span><span class="sxs-lookup"><span data-stu-id="aa97f-162">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>  
  
```csharp  
// Generates 2 warnings:  
// A a = new A();  
  
// Generate no errors or warnings:  
B b = new B();  
b.NewMethod();  
  
// Generates an error, terminating compilation:  
// b.OldMethod();  
```  
  
 <span data-ttu-id="aa97f-163">Создается два предупреждения для класса `A`: одно для объявления ссылки на класс, а второе — для конструктора класса.</span><span class="sxs-lookup"><span data-stu-id="aa97f-163">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span>  
  
 <span data-ttu-id="aa97f-164">Атрибут `Obsolete` может использоваться без аргументов, однако рекомендуется включать пояснение о том, почему соответствующий элемент является устаревшим и что следует использовать вместо него.</span><span class="sxs-lookup"><span data-stu-id="aa97f-164">The `Obsolete` attribute can be used without arguments, but including an explanation of why the item is obsolete and what to use instead is recommended.</span></span>  
  
 <span data-ttu-id="aa97f-165">Атрибут `Obsolete` является атрибутом однократного использования и может применяться к любой сущности, допускающей использование атрибутов.</span><span class="sxs-lookup"><span data-stu-id="aa97f-165">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="aa97f-166">`Obsolete` является псевдонимом для <xref:System.ObsoleteAttribute>.</span><span class="sxs-lookup"><span data-stu-id="aa97f-166">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>  
  
## <a name="Conditional"></a> <span data-ttu-id="aa97f-167">Атрибут Conditional</span><span class="sxs-lookup"><span data-stu-id="aa97f-167">Conditional Attribute</span></span>  
 <span data-ttu-id="aa97f-168">Атрибут `Conditional` определяет зависимость выполнения метода от идентификатора предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="aa97f-168">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="aa97f-169">Атрибут `Conditional` является псевдонимом для <xref:System.Diagnostics.ConditionalAttribute> и может применяться к методу или классу атрибута.</span><span class="sxs-lookup"><span data-stu-id="aa97f-169">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>  
  
 <span data-ttu-id="aa97f-170">В этом примере атрибут `Conditional` применяется к методу для включения и отключения отображения диагностической информации для конкретной программы:</span><span class="sxs-lookup"><span data-stu-id="aa97f-170">In this example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>  
  
```csharp  
#define TRACE_ON  
using System;  
using System.Diagnostics;  
  
public class Trace  
{  
    [Conditional("TRACE_ON")]  
    public static void Msg(string msg)  
    {  
        Console.WriteLine(msg);  
    }  
}  
  
public class ProgramClass  
{  
    static void Main()  
    {  
        Trace.Msg("Now in Main...");  
        Console.WriteLine("Done.");  
    }  
}  
```  
  
 <span data-ttu-id="aa97f-171">Если идентификатор `TRACE_ON` не определен, выходные данные трассировки не отображаются.</span><span class="sxs-lookup"><span data-stu-id="aa97f-171">If the `TRACE_ON` identifier is not defined, no trace output will be displayed.</span></span>  
  
 <span data-ttu-id="aa97f-172">Атрибут `Conditional` часто используется с идентификатором `DEBUG` для включения функций трассировки и ведения журнала для отладочных сборок (но не сборок выпуска) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="aa97f-172">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, like this:</span></span>  
  
```csharp  
[Conditional("DEBUG")]  
static void DebugMethod()  
{  
}  
```  
  
 <span data-ttu-id="aa97f-173">Когда вызывается метод, помеченный как условный, наличие или отсутствие заданного символа предварительной обработки определяет, включается ли вызов или пропускается.</span><span class="sxs-lookup"><span data-stu-id="aa97f-173">When a method marked as conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="aa97f-174">Если этот символ определен, вызов включается; в противном случае вызов пропускается.</span><span class="sxs-lookup"><span data-stu-id="aa97f-174">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="aa97f-175">Использование атрибута `Conditional` — это более понятная, элегантная и менее подверженная ошибкам альтернатива вложению методов в блоки `#if…#endif`, например следующим образом:</span><span class="sxs-lookup"><span data-stu-id="aa97f-175">Using `Conditional` is a cleaner, more elegant, and less error-prone alternative to enclosing methods inside `#if…#endif` blocks, like this:</span></span>  
  
```csharp  
#if DEBUG  
    void ConditionalMethod()  
    {  
    }  
#endif  
```  
  
 <span data-ttu-id="aa97f-176">Условный метод должен быть методом в объявлении класса или структуры и не должен возвращать значение.</span><span class="sxs-lookup"><span data-stu-id="aa97f-176">A conditional method must be a method in a class or struct declaration and must not have a return value.</span></span>  
  
### <a name="using-multiple-identifiers"></a><span data-ttu-id="aa97f-177">Использование нескольких идентификаторов</span><span class="sxs-lookup"><span data-stu-id="aa97f-177">Using Multiple Identifiers</span></span>  
 <span data-ttu-id="aa97f-178">Если метод содержит несколько атрибутов `Conditional`, вызов метода включается, если определен хотя бы один из условных символов (другими словами, символы логически связаны с помощью оператора ИЛИ).</span><span class="sxs-lookup"><span data-stu-id="aa97f-178">If a method has multiple `Conditional` attributes, a call to the method is included if at least one of the conditional symbols is defined (in other words, the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="aa97f-179">В этом примере наличие `A` или `B` приведет к вызову метода:</span><span class="sxs-lookup"><span data-stu-id="aa97f-179">In this example, the presence of either `A` or `B` will result in a method call:</span></span>  
  
```csharp  
[Conditional("A"), Conditional("B")]  
static void DoIfAorB()  
{  
    // ...  
}  
```  
  
 <span data-ttu-id="aa97f-180">Для получения эффекта логического связывания символов с помощью оператора И можно определить последовательные условные методы.</span><span class="sxs-lookup"><span data-stu-id="aa97f-180">To achieve the effect of logically linking symbols by using the AND operator, you can define serial conditional methods.</span></span> <span data-ttu-id="aa97f-181">Например, второй метод ниже будет выполняться, только если определены `A` и `B`:</span><span class="sxs-lookup"><span data-stu-id="aa97f-181">For example, the second method below will execute only if both `A` and `B` are defined:</span></span>  
  
```csharp
[Conditional("A")]  
static void DoIfA()  
{  
    DoIfAandB();  
}  
  
[Conditional("B")]  
static void DoIfAandB()  
{  
    // Code to execute when both A and B are defined...  
}  
```  
  
### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="aa97f-182">Использование атрибута Conditional с классами атрибутов</span><span class="sxs-lookup"><span data-stu-id="aa97f-182">Using Conditional with Attribute Classes</span></span>  
 <span data-ttu-id="aa97f-183">Атрибут `Conditional` также может применяться к определению класса атрибута.</span><span class="sxs-lookup"><span data-stu-id="aa97f-183">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="aa97f-184">В этом примере настраиваемый атрибут `Documentation` добавит сведения в метаданные, только если задано значение DEBUG.</span><span class="sxs-lookup"><span data-stu-id="aa97f-184">In this example, the custom attribute `Documentation` will only add information to the metadata if DEBUG is defined.</span></span>  
  
```csharp  
[Conditional("DEBUG")]  
public class Documentation : System.Attribute  
{  
    string text;  
  
    public Documentation(string text)  
    {  
        this.text = text;  
    }  
}  
  
class SampleClass  
{  
    // This attribute will only be included if DEBUG is defined.  
    [Documentation("This method displays an integer.")]  
    static void DoWork(int i)  
    {  
        System.Console.WriteLine(i.ToString());  
    }  
}  
```  
  
## <a name="CallerInfo"></a> <span data-ttu-id="aa97f-185">Информационные атрибуты вызывающего объекта</span><span class="sxs-lookup"><span data-stu-id="aa97f-185">Caller Info Attributes</span></span>  
 <span data-ttu-id="aa97f-186">С помощью информационных атрибутов вызывающего объекта можно получить сведения о вызывающем объекте метода.</span><span class="sxs-lookup"><span data-stu-id="aa97f-186">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="aa97f-187">Можно получить путь к файлу исходного кода, номер строки в исходном коде и имя вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="aa97f-187">You can obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span>  
  
 <span data-ttu-id="aa97f-188">Для получения этих сведений используются атрибуты, которые применяются к необязательным параметрам.</span><span class="sxs-lookup"><span data-stu-id="aa97f-188">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="aa97f-189">Каждый необязательный параметр задает значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aa97f-189">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="aa97f-190">В следующей таблице перечислены информационные атрибуты вызывающего объекта, которые определены в пространстве имен <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="aa97f-190">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>  
  
|<span data-ttu-id="aa97f-191">attribute</span><span class="sxs-lookup"><span data-stu-id="aa97f-191">Attribute</span></span>|<span data-ttu-id="aa97f-192">Описание:</span><span class="sxs-lookup"><span data-stu-id="aa97f-192">Description</span></span>|<span data-ttu-id="aa97f-193">Type</span><span class="sxs-lookup"><span data-stu-id="aa97f-193">Type</span></span>|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="aa97f-194">Полный путь исходного файла, содержащего вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="aa97f-194">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="aa97f-195">Это путь во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="aa97f-195">This is the path at compile time.</span></span>|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="aa97f-196">Номер строки в исходном файле, из которого вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="aa97f-196">Line number in the source file from which the method is called.</span></span>|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="aa97f-197">Имя свойства или метода вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="aa97f-197">Method name or property name of the caller.</span></span> <span data-ttu-id="aa97f-198">Дополнительные сведения см. в разделе [Сведения о вызывающем объекте (C#)](../caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="aa97f-198">For more information, see [Caller Information (C#)](../caller-information.md).</span></span>|`String`|  
  
 <span data-ttu-id="aa97f-199">Дополнительные сведения об информационных атрибутах вызывающего объекта см. в разделе [Сведения о вызывающем объекте (C#)](../caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="aa97f-199">For more information about the Caller Info attributes, see [Caller Information (C#)](../caller-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa97f-200">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aa97f-200">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="aa97f-201">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="aa97f-201">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="aa97f-202">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa97f-202">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="aa97f-203">Отражение (C#)</span><span class="sxs-lookup"><span data-stu-id="aa97f-203">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="aa97f-204">Обращение к атрибутам с помощью отражения (C#)</span><span class="sxs-lookup"><span data-stu-id="aa97f-204">Accessing Attributes by Using Reflection (C#)</span></span>](./accessing-attributes-by-using-reflection.md)
