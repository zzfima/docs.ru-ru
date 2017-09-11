---
title: "Общие атрибуты (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9adb5cb378701c8d06a3fa28bad44dc857026b5a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="common-attributes-visual-basic"></a><span data-ttu-id="f3bb6-102">Общие атрибуты (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3bb6-102">Common Attributes (Visual Basic)</span></span>
<span data-ttu-id="f3bb6-103">В этом разделе описываются атрибуты, которые чаще всего используются в программах Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-103">This topic describes the attributes that are most commonly used in Visual Basic programs.</span></span>  
  
-   [<span data-ttu-id="f3bb6-104">Глобальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="f3bb6-104">Global Attributes</span></span>](#Global)  
  
-   [<span data-ttu-id="f3bb6-105">Устаревший атрибут</span><span class="sxs-lookup"><span data-stu-id="f3bb6-105">Obsolete Attribute</span></span>](#Obsolete)  
  
-   [<span data-ttu-id="f3bb6-106">Условный атрибут</span><span class="sxs-lookup"><span data-stu-id="f3bb6-106">Conditional Attribute</span></span>](#Conditional)  
  
-   [<span data-ttu-id="f3bb6-107">Информационные атрибуты вызывающего</span><span class="sxs-lookup"><span data-stu-id="f3bb6-107">Caller Info Attributes</span></span>](#CallerInfo)  
  
-   [<span data-ttu-id="f3bb6-108">Атрибуты Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3bb6-108">Visual Basic Attributes</span></span>](#VB)  
  
##  <span data-ttu-id="f3bb6-109"><a name="Global"></a>Глобальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="f3bb6-109"><a name="Global"></a> Global Attributes</span></span>  
 <span data-ttu-id="f3bb6-110">Большинство атрибутов применяется к определенным элементам языка, такие как классы или методы; Тем не менее, некоторые атрибуты являются глобальными — они применяются для всей сборки или модуля.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-110">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="f3bb6-111">Например <xref:System.Reflection.AssemblyVersionAttribute>атрибут может использоваться для встраивания сведений о версии в сборку, следующим образом:</xref:System.Reflection.AssemblyVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-111">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>  
  
```vb  
<Assembly: AssemblyVersion("1.0.0.0")>  
```  
  
 <span data-ttu-id="f3bb6-112">Глобальные атрибуты отображаются в исходном коде после любых верхнего уровня`Imports` инструкций и перед всеми объявлениями типов, модуль или пространство имен.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-112">Global attributes appear in the source code after any top-level`Imports` statements and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="f3bb6-113">Глобальные атрибуты могут появляться в нескольких исходных файлов, но файлы должны быть скомпилированы за один проход компиляции.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-113">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="f3bb6-114">Для проектов Visual Basic глобальных атрибутов обычно помещаются в файле AssemblyInfo.vb (файл создается автоматически при создании проекта в Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="f3bb6-114">For Visual Basic projects, global attributes are generally put in the AssemblyInfo.vb file (the file is created automatically when you create a project in Visual Studio).</span></span>  
  
 <span data-ttu-id="f3bb6-115">Атрибуты сборки — это значения, которые предоставляют сведения о сборке.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-115">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="f3bb6-116">Они делятся на следующие категории:</span><span class="sxs-lookup"><span data-stu-id="f3bb6-116">They fall into the following categories:</span></span>  
  
-   <span data-ttu-id="f3bb6-117">Атрибуты удостоверения сборки.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-117">Assembly identity attributes</span></span>  
  
-   <span data-ttu-id="f3bb6-118">Информационные атрибуты</span><span class="sxs-lookup"><span data-stu-id="f3bb6-118">Informational attributes</span></span>  
  
-   <span data-ttu-id="f3bb6-119">Атрибуты манифеста сборки</span><span class="sxs-lookup"><span data-stu-id="f3bb6-119">Assembly manifest attributes</span></span>  
  
### <a name="assembly-identity-attributes"></a><span data-ttu-id="f3bb6-120">Атрибуты удостоверения сборки</span><span class="sxs-lookup"><span data-stu-id="f3bb6-120">Assembly Identity Attributes</span></span>  
 <span data-ttu-id="f3bb6-121">Удостоверение сборки определяют три атрибута (со строгим именем, если применимо): имя, версию и язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-121">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="f3bb6-122">Эти атрибуты формируют полное имя сборки и являются обязательными при создании ссылки в коде.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-122">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="f3bb6-123">Можно задать язык и региональные параметры с помощью атрибутов и версии сборки.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-123">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="f3bb6-124">Однако значение имени задается компилятором, в СРЕДЕ Visual Studio [диалоговое окно сведений о сборке](https://docs.microsoft.com/visualstudio/ide/reference/assembly-information-dialog-box), или компоновщик сборок (Al.exe) при создании сборки на основе файла, содержащего манифест сборки.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-124">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created, based on the file that contains the assembly manifest.</span></span> <span data-ttu-id="f3bb6-125"><xref:System.Reflection.AssemblyFlagsAttribute>Атрибут указывает, могут ли сосуществовать несколько копий сборки.</xref:System.Reflection.AssemblyFlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-125">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>  
  
 <span data-ttu-id="f3bb6-126">Ниже приведены атрибуты удостоверения.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-126">The following table shows the identity attributes.</span></span>  
  
|<span data-ttu-id="f3bb6-127">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f3bb6-127">Attribute</span></span>|<span data-ttu-id="f3bb6-128">Цель</span><span class="sxs-lookup"><span data-stu-id="f3bb6-128">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="f3bb6-129"><xref:System.Reflection.AssemblyName></xref:System.Reflection.AssemblyName></span><span class="sxs-lookup"><span data-stu-id="f3bb6-129"><xref:System.Reflection.AssemblyName></span></span>|<span data-ttu-id="f3bb6-130">Полностью описывает удостоверение сборки.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-130">Fully describes the identity of an assembly.</span></span>|  
|<span data-ttu-id="f3bb6-131"><xref:System.Reflection.AssemblyVersionAttribute></xref:System.Reflection.AssemblyVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-131"><xref:System.Reflection.AssemblyVersionAttribute></span></span>|<span data-ttu-id="f3bb6-132">Указывает версию сборки.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-132">Specifies the version of an assembly.</span></span>|  
|<span data-ttu-id="f3bb6-133"><xref:System.Reflection.AssemblyCultureAttribute></xref:System.Reflection.AssemblyCultureAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-133"><xref:System.Reflection.AssemblyCultureAttribute></span></span>|<span data-ttu-id="f3bb6-134">Указывает, какой язык и региональные параметры поддерживает сборка.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-134">Specifies which culture the assembly supports.</span></span>|  
|<span data-ttu-id="f3bb6-135"><xref:System.Reflection.AssemblyFlagsAttribute></xref:System.Reflection.AssemblyFlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-135"><xref:System.Reflection.AssemblyFlagsAttribute></span></span>|<span data-ttu-id="f3bb6-136">Указывает, поддерживает ли сборка side-by-side выполнения на одном компьютере, в том же процессе или в том же домене приложения.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-136">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|  
  
### <a name="informational-attributes"></a><span data-ttu-id="f3bb6-137">Информационные атрибуты</span><span class="sxs-lookup"><span data-stu-id="f3bb6-137">Informational Attributes</span></span>  
 <span data-ttu-id="f3bb6-138">Информационные атрибуты можно использовать для предоставления дополнительных сведений о компании или продукте в сборке.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-138">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="f3bb6-139">В следующей таблице показаны информационные атрибуты, определенные в <xref:System.Reflection?displayProperty=fullName>имен.</xref:System.Reflection?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f3bb6-139">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=fullName> namespace.</span></span>  
  
|<span data-ttu-id="f3bb6-140">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f3bb6-140">Attribute</span></span>|<span data-ttu-id="f3bb6-141">Цель</span><span class="sxs-lookup"><span data-stu-id="f3bb6-141">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="f3bb6-142"><xref:System.Reflection.AssemblyProductAttribute></xref:System.Reflection.AssemblyProductAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-142"><xref:System.Reflection.AssemblyProductAttribute></span></span>|<span data-ttu-id="f3bb6-143">Определяет пользовательский атрибут, который указывает название продукта для манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-143">Defines a custom attribute that specifies a product name for an assembly manifest.</span></span>|  
|<span data-ttu-id="f3bb6-144"><xref:System.Reflection.AssemblyTrademarkAttribute></xref:System.Reflection.AssemblyTrademarkAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-144"><xref:System.Reflection.AssemblyTrademarkAttribute></span></span>|<span data-ttu-id="f3bb6-145">Определяет пользовательский атрибут товарного знака для манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-145">Defines a custom attribute that specifies a trademark for an assembly manifest.</span></span>|  
|<span data-ttu-id="f3bb6-146"><xref:System.Reflection.AssemblyInformationalVersionAttribute></xref:System.Reflection.AssemblyInformationalVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-146"><xref:System.Reflection.AssemblyInformationalVersionAttribute></span></span>|<span data-ttu-id="f3bb6-147">Определяет пользовательский атрибут версии для манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-147">Defines a custom attribute that specifies an informational version for an assembly manifest.</span></span>|  
|<span data-ttu-id="f3bb6-148"><xref:System.Reflection.AssemblyCompanyAttribute></xref:System.Reflection.AssemblyCompanyAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-148"><xref:System.Reflection.AssemblyCompanyAttribute></span></span>|<span data-ttu-id="f3bb6-149">Определяет пользовательский атрибут, который указывает название компании для манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-149">Defines a custom attribute that specifies a company name for an assembly manifest.</span></span>|  
|<span data-ttu-id="f3bb6-150"><xref:System.Reflection.AssemblyCopyrightAttribute></xref:System.Reflection.AssemblyCopyrightAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-150"><xref:System.Reflection.AssemblyCopyrightAttribute></span></span>|<span data-ttu-id="f3bb6-151">Определяет пользовательский атрибут авторских прав для манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-151">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|  
|<span data-ttu-id="f3bb6-152"><xref:System.Reflection.AssemblyFileVersionAttribute></xref:System.Reflection.AssemblyFileVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-152"><xref:System.Reflection.AssemblyFileVersionAttribute></span></span>|<span data-ttu-id="f3bb6-153">Указывает компилятору использовать определенный номер версии для ресурса версии файла Win32.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-153">Instructs the compiler to use a specific version number for the Win32 file version resource.</span></span>|  
|<span data-ttu-id="f3bb6-154"><xref:System.CLSCompliantAttribute></xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-154"><xref:System.CLSCompliantAttribute></span></span>|<span data-ttu-id="f3bb6-155">Указывает, является ли сборка совместимым с общей спецификацией (CLS).</span><span class="sxs-lookup"><span data-stu-id="f3bb6-155">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|  
  
### <a name="assembly-manifest-attributes"></a><span data-ttu-id="f3bb6-156">Атрибуты манифеста сборки</span><span class="sxs-lookup"><span data-stu-id="f3bb6-156">Assembly Manifest Attributes</span></span>  
 <span data-ttu-id="f3bb6-157">Атрибуты манифеста сборки можно использовать для предоставления сведений в манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-157">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="f3bb6-158">Это включает в себя заголовок, описание, псевдоним по умолчанию и конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-158">This includes title, description, default alias, and configuration.</span></span> <span data-ttu-id="f3bb6-159">В следующей таблице представлены атрибуты манифеста сборки определены в <xref:System.Reflection?displayProperty=fullName>имен.</xref:System.Reflection?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f3bb6-159">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=fullName> namespace.</span></span>  
  
|<span data-ttu-id="f3bb6-160">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f3bb6-160">Attribute</span></span>|<span data-ttu-id="f3bb6-161">Цель</span><span class="sxs-lookup"><span data-stu-id="f3bb6-161">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="f3bb6-162"><xref:System.Reflection.AssemblyTitleAttribute></xref:System.Reflection.AssemblyTitleAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-162"><xref:System.Reflection.AssemblyTitleAttribute></span></span>|<span data-ttu-id="f3bb6-163">Определяет пользовательский атрибут названия сборки для манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-163">Defines a custom attribute that specifies an assembly title for an assembly manifest.</span></span>|  
|<span data-ttu-id="f3bb6-164"><xref:System.Reflection.AssemblyDescriptionAttribute></xref:System.Reflection.AssemblyDescriptionAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-164"><xref:System.Reflection.AssemblyDescriptionAttribute></span></span>|<span data-ttu-id="f3bb6-165">Определяет пользовательский атрибут описания сборки для манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-165">Defines a custom attribute that specifies an assembly description for an assembly manifest.</span></span>|  
|<span data-ttu-id="f3bb6-166"><xref:System.Reflection.AssemblyConfigurationAttribute></xref:System.Reflection.AssemblyConfigurationAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-166"><xref:System.Reflection.AssemblyConfigurationAttribute></span></span>|<span data-ttu-id="f3bb6-167">Определяет пользовательский атрибут, который описывает конфигурацию сборки (например, распространение или отладку) для манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-167">Defines a custom attribute that specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|  
|<span data-ttu-id="f3bb6-168"><xref:System.Reflection.AssemblyDefaultAliasAttribute></xref:System.Reflection.AssemblyDefaultAliasAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-168"><xref:System.Reflection.AssemblyDefaultAliasAttribute></span></span>|<span data-ttu-id="f3bb6-169">Определяет понятный псевдоним по умолчанию для манифеста сборки</span><span class="sxs-lookup"><span data-stu-id="f3bb6-169">Defines a friendly default alias for an assembly manifest</span></span>|  
  
##  <span data-ttu-id="f3bb6-170"><a name="Obsolete"></a>Устаревший атрибут</span><span class="sxs-lookup"><span data-stu-id="f3bb6-170"><a name="Obsolete"></a> Obsolete Attribute</span></span>  
 <span data-ttu-id="f3bb6-171">`Obsolete` Помечает сущности программы, не рекомендуется использовать.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-171">The `Obsolete` attribute marks a program entity as one that is no longer recommended for use.</span></span> <span data-ttu-id="f3bb6-172">Каждый случай использования сущности, отмеченной устаревшей постоянно генерирует предупреждение или сообщение об ошибке, в зависимости от настройки атрибута.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-172">Each use of an entity marked obsolete will subsequently generate a warning or an error, depending on how the attribute is configured.</span></span> <span data-ttu-id="f3bb6-173">Например:</span><span class="sxs-lookup"><span data-stu-id="f3bb6-173">For example:</span></span>  
  
```vb  
<System.Obsolete("use class B")>   
Class A  
    Sub Method()  
    End Sub  
End Class  
  
Class B  
    <System.Obsolete("use NewMethod", True)>   
    Sub OldMethod()  
    End Sub  
  
    Sub NewMethod()  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="f3bb6-174">В этом примере `Obsolete` атрибут применяется к классу `A` и метод `B.OldMethod`.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-174">In this example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="f3bb6-175">Так как второй аргумент конструктора атрибута, применить к `B.OldMethod` задано значение `true`, этот метод будет приводить к ошибке компилятора, а с помощью класса `A` будет просто создают предупреждения.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-175">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="f3bb6-176">Вызов `B.NewMethod`, тем не менее, создает предупреждение или ошибка.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-176">Calling `B.NewMethod`, however, produces no warning or error.</span></span>  
  
 <span data-ttu-id="f3bb6-177">Строка, предоставленная в качестве первого аргумента конструктору атрибута будет отображаться как часть предупреждения или ошибки.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-177">The string provided as the first argument to attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="f3bb6-178">Например при использовании с предыдущими определениями следующий код генерирует два предупреждения и одну ошибку:</span><span class="sxs-lookup"><span data-stu-id="f3bb6-178">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>  
  
```vb  
' Generates 2 warnings:  
' Dim a As New A  
' Generate no errors or warnings:  
  
Dim b As New B  
b.NewMethod()  
  
' Generates an error, terminating compilation:  
' b.OldMethod()  
```  
  
 <span data-ttu-id="f3bb6-179">Два предупреждения для класса `A` создаются: один для объявления ссылки на класс и один для конструктора класса.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-179">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span>  
  
 <span data-ttu-id="f3bb6-180">`Obsolete` Атрибут может использоваться без аргументов, но включать пояснение, почему соответствующий элемент является устаревшим и что следует использовать вместо него рекомендуется использовать.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-180">The `Obsolete` attribute can be used without arguments, but including an explanation of why the item is obsolete and what to use instead is recommended.</span></span>  
  
 <span data-ttu-id="f3bb6-181">`Obsolete` Атрибут является атрибутом однократного использования и может применяться к любой сущности, допускающей использование атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-181">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="f3bb6-182">`Obsolete`является псевдонимом для <xref:System.ObsoleteAttribute>.</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-182">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>  
  
##  <span data-ttu-id="f3bb6-183"><a name="Conditional"></a>Условный атрибут</span><span class="sxs-lookup"><span data-stu-id="f3bb6-183"><a name="Conditional"></a> Conditional Attribute</span></span>  
 <span data-ttu-id="f3bb6-184">`Conditional` Атрибут делает выполнение метода зависимым от идентификатора предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-184">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="f3bb6-185">`Conditional` Атрибута является псевдонимом для <xref:System.Diagnostics.ConditionalAttribute>и может применяться к методу или атрибут класса</xref:System.Diagnostics.ConditionalAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-185">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>  
  
 <span data-ttu-id="f3bb6-186">В этом примере `Conditional` применяется к методу для включения и отключения отображения диагностической информации для конкретной программы:</span><span class="sxs-lookup"><span data-stu-id="f3bb6-186">In this example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>  
  
```vb  
#Const TRACE_ON = True  
Imports System  
Imports System.Diagnostics  
Module TestConditionalAttribute  
    Public Class Trace  
        <Conditional("TRACE_ON")>   
        Public Shared Sub Msg(ByVal msg As String)  
            Console.WriteLine(msg)  
        End Sub  
  
    End Class  
  
    Sub Main()  
        Trace.Msg("Now in Main...")  
        Console.WriteLine("Done.")  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="f3bb6-187">Если `TRACE_ON` идентификатор не определен, отображаются выходные данные трассировки.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-187">If the `TRACE_ON` identifier is not defined, no trace output will be displayed.</span></span>  
  
 <span data-ttu-id="f3bb6-188">`Conditional` Атрибут часто используется с `DEBUG` идентификатор для включения трассировки и функции ведения журнала для построения отладки, но не в построениях выпуска, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f3bb6-188">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, like this:</span></span>  
  
```vb  
<Conditional("DEBUG")>   
Shared Sub DebugMethod()  
  
End Sub  
```  
  
 <span data-ttu-id="f3bb6-189">Когда вызывается метод, помеченный как условный, наличие или отсутствие заданного символа предварительной обработки определяет, включен ли вызов или опущен.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-189">When a method marked as conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="f3bb6-190">Если этот символ определен, вызов включается; в противном случае — вызов опускается.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-190">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="f3bb6-191">С помощью `Conditional` представляет собой более понятную, элегантную и менее подверженную ошибкам альтернативу вложению методов в `#if…#endif` блоки, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f3bb6-191">Using `Conditional` is a cleaner, more elegant, and less error-prone alternative to enclosing methods inside `#if…#endif` blocks, like this:</span></span>  
  
```vb  
#If DEBUG Then  
    Sub ConditionalMethod()  
    End Sub  
#End If  
```  
  
 <span data-ttu-id="f3bb6-192">Условный метод должен быть методом в объявлении класса или структуры и не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-192">A conditional method must be a method in a class or struct declaration and must not have a return value.</span></span>  
  
### <a name="using-multiple-identifiers"></a><span data-ttu-id="f3bb6-193">Использование нескольких идентификаторов</span><span class="sxs-lookup"><span data-stu-id="f3bb6-193">Using Multiple Identifiers</span></span>  
 <span data-ttu-id="f3bb6-194">Если метод имеет несколько `Conditional` атрибутов, вызов метода включается, если определен хотя бы один из условных символов (другими словами, символы логически связаны оператором OR).</span><span class="sxs-lookup"><span data-stu-id="f3bb6-194">If a method has multiple `Conditional` attributes, a call to the method is included if at least one of the conditional symbols is defined (in other words, the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="f3bb6-195">В этом примере на наличие `A` или `B` приведет к вызову метода:</span><span class="sxs-lookup"><span data-stu-id="f3bb6-195">In this example, the presence of either `A` or `B` will result in a method call:</span></span>  
  
```vb  
<Conditional("A"), Conditional("B")>   
Shared Sub DoIfAorB()  
  
End Sub  
```  
  
 <span data-ttu-id="f3bb6-196">Для получения эффекта логического связывания символов оператором AND, можно задать последовательные условные методы.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-196">To achieve the effect of logically linking symbols by using the AND operator, you can define serial conditional methods.</span></span> <span data-ttu-id="f3bb6-197">Например, второй метод, приведенный ниже будет выполняться, только если оба `A` и `B` определены:</span><span class="sxs-lookup"><span data-stu-id="f3bb6-197">For example, the second method below will execute only if both `A` and `B` are defined:</span></span>  
  
```vb  
<Conditional("A")>   
Shared Sub DoIfA()  
    DoIfAandB()  
End Sub  
  
<Conditional("B")>   
Shared Sub DoIfAandB()  
    ' Code to execute when both A and B are defined...  
End Sub  
```  
  
### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="f3bb6-198">С помощью условного с классами атрибутов</span><span class="sxs-lookup"><span data-stu-id="f3bb6-198">Using Conditional with Attribute Classes</span></span>  
 <span data-ttu-id="f3bb6-199">`Conditional` Атрибут также может применяться к определению класса атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-199">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="f3bb6-200">В этом примере пользовательский атрибут `Documentation` только добавляет сведения в метаданные, если задано значение DEBUG.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-200">In this example, the custom attribute `Documentation` will only add information to the metadata if DEBUG is defined.</span></span>  
  
```vb  
<Conditional("DEBUG")>   
Public Class Documentation  
    Inherits System.Attribute  
    Private text As String  
    Sub New(ByVal doc_text As String)  
        text = doc_text  
    End Sub  
End Class  
  
Class SampleClass  
    ' This attribute will only be included if DEBUG is defined.  
    <Documentation("This method displays an integer.")>   
    Shared Sub DoWork(ByVal i As Integer)  
        System.Console.WriteLine(i)  
    End Sub  
End Class  
```  
  
##  <span data-ttu-id="f3bb6-201"><a name="CallerInfo"></a>Информационные атрибуты вызывающего</span><span class="sxs-lookup"><span data-stu-id="f3bb6-201"><a name="CallerInfo"></a> Caller Info Attributes</span></span>  
 <span data-ttu-id="f3bb6-202">С помощью информационных атрибутов вызывающего объекта можно получить сведения о вызывающем объекте метода.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-202">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="f3bb6-203">Можно получить путь к файлу исходного кода, номер строки в исходном коде и имя члена, вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-203">You can obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span>  
  
 <span data-ttu-id="f3bb6-204">Чтобы получить сведения о вызывающем члена, используйте атрибуты, которые применяются к необязательным параметрам.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-204">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="f3bb6-205">Каждый дополнительный параметр задает значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-205">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="f3bb6-206">В следующей таблице перечислены информационные атрибуты вызывающего объекта, определенные в <xref:System.Runtime.CompilerServices?displayProperty=fullName>пространство имен:</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f3bb6-206">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace:</span></span>  
  
|<span data-ttu-id="f3bb6-207">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f3bb6-207">Attribute</span></span>|<span data-ttu-id="f3bb6-208">Описание</span><span class="sxs-lookup"><span data-stu-id="f3bb6-208">Description</span></span>|<span data-ttu-id="f3bb6-209">Тип</span><span class="sxs-lookup"><span data-stu-id="f3bb6-209">Type</span></span>|  
|---|---|---|  
|<span data-ttu-id="f3bb6-210"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-210"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span></span>|<span data-ttu-id="f3bb6-211">Полный путь исходного файла, содержащего вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-211">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="f3bb6-212">Это путь во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-212">This is the path at compile time.</span></span>|`String`|  
|<span data-ttu-id="f3bb6-213"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-213"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span></span>|<span data-ttu-id="f3bb6-214">Номер строки в исходном файле, из которого вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-214">Line number in the source file from which the method is called.</span></span>|`Integer`|  
|<span data-ttu-id="f3bb6-215"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-215"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span></span>|<span data-ttu-id="f3bb6-216">Имя метода или свойства вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-216">Method name or property name of the caller.</span></span> <span data-ttu-id="f3bb6-217">Дополнительные сведения см. в разделе [сведения о вызывающем (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="f3bb6-217">For more information, see [Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).</span></span>|`String`|  
  
 <span data-ttu-id="f3bb6-218">Дополнительные сведения о информационные атрибуты вызывающего объекта, в разделе [сведения о вызывающем (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="f3bb6-218">For more information about the Caller Info attributes, see [Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).</span></span>  
  
##  <span data-ttu-id="f3bb6-219"><a name="VB"></a>Атрибуты Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3bb6-219"><a name="VB"></a> Visual Basic Attributes</span></span>  
 <span data-ttu-id="f3bb6-220">В следующей таблице перечислены атрибуты, относящиеся к Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-220">The following table lists the attributes that are specific to Visual Basic.</span></span>  
  
|<span data-ttu-id="f3bb6-221">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f3bb6-221">Attribute</span></span>|<span data-ttu-id="f3bb6-222">Цель</span><span class="sxs-lookup"><span data-stu-id="f3bb6-222">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="f3bb6-223"><xref:Microsoft.VisualBasic.ComClassAttribute></xref:Microsoft.VisualBasic.ComClassAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-223"><xref:Microsoft.VisualBasic.ComClassAttribute></span></span>|<span data-ttu-id="f3bb6-224">Указывает компилятору на то, что класс должен быть предоставлен как COM-объект.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-224">Indicates to the compiler that the class should be exposed as a COM object.</span></span>|  
|<span data-ttu-id="f3bb6-225"><xref:Microsoft.VisualBasic.HideModuleNameAttribute></xref:Microsoft.VisualBasic.HideModuleNameAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-225"><xref:Microsoft.VisualBasic.HideModuleNameAttribute></span></span>|<span data-ttu-id="f3bb6-226">Позволяет членам модуля должен осуществляться с использованием только квалификации, необходимой для модуля.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-226">Allows module members to be accessed using only the qualification needed for the module.</span></span>|  
|<span data-ttu-id="f3bb6-227"><xref:Microsoft.VisualBasic.VBFixedStringAttribute></xref:Microsoft.VisualBasic.VBFixedStringAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-227"><xref:Microsoft.VisualBasic.VBFixedStringAttribute></span></span>|<span data-ttu-id="f3bb6-228">Указывает размер строки фиксированной длины в структуре для использования с файлом входных и выходных данных функции.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-228">Specifies the size of a fixed-length string in a structure for use with file input and output functions.</span></span>|  
|<span data-ttu-id="f3bb6-229"><xref:Microsoft.VisualBasic.VBFixedArrayAttribute></xref:Microsoft.VisualBasic.VBFixedArrayAttribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-229"><xref:Microsoft.VisualBasic.VBFixedArrayAttribute></span></span>|<span data-ttu-id="f3bb6-230">Указывает размер фиксированного массива в структуре для использования с файлом входных и выходных данных функции.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-230">Specifies the size of a fixed array in a structure for use with file input and output functions.</span></span>|  
  
### <a name="comclassattribute"></a><span data-ttu-id="f3bb6-231">COMClassAttribute</span><span class="sxs-lookup"><span data-stu-id="f3bb6-231">COMClassAttribute</span></span>  
 <span data-ttu-id="f3bb6-232">Использование `COMClassAttribute` для упрощения процесса создания COM-компонентов с помощью Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-232">Use `COMClassAttribute` to simplify the process of creating COM components from Visual Basic.</span></span> <span data-ttu-id="f3bb6-233">COM-объекты существенно отличаются от сборок .NET Framework и не `COMClassAttribute`, необходимо выполнить ряд действий для создания объекта COM с помощью Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-233">COM objects are considerably different from .NET Framework assemblies, and without `COMClassAttribute`, you need to follow a number of steps to generate a COM object from Visual Basic.</span></span> <span data-ttu-id="f3bb6-234">Для классов, помеченных атрибутом `COMClassAttribute`, компилятор выполняет большинство этих шагов автоматически.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-234">For classes marked with `COMClassAttribute`, the compiler performs many of these steps automatically.</span></span>  
  
### <a name="hidemodulenameattribute"></a><span data-ttu-id="f3bb6-235">HideModuleNameAttribute</span><span class="sxs-lookup"><span data-stu-id="f3bb6-235">HideModuleNameAttribute</span></span>  
 <span data-ttu-id="f3bb6-236">Использование `HideModuleNameAttribute` позволяет членам модуля, к которым осуществляется с использованием только квалификации, необходимой для модуля.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-236">Use `HideModuleNameAttribute` to allow module members to be accessed by using only the qualification needed for the module.</span></span>  
  
### <a name="vbfixedstringattribute"></a><span data-ttu-id="f3bb6-237">VBFixedStringAttribute</span><span class="sxs-lookup"><span data-stu-id="f3bb6-237">VBFixedStringAttribute</span></span>  
 <span data-ttu-id="f3bb6-238">Используйте `VBFixedStringAttribute` для принудительного Visual Basic для создания строки фиксированной длины.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-238">Use `VBFixedStringAttribute` to force Visual Basic to create a fixed-length string.</span></span> <span data-ttu-id="f3bb6-239">Строки имеют переменную длину по умолчанию, и этот атрибут полезен при хранении строк для файлов.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-239">Strings are of variable length by default, and this attribute is useful when storing strings to files.</span></span> <span data-ttu-id="f3bb6-240">Следующий код демонстрирует это:</span><span class="sxs-lookup"><span data-stu-id="f3bb6-240">The following code demonstrates this:</span></span>  
  
```vb  
Structure Worker  
    ' The runtime uses VBFixedString to determine   
    ' if the field should be written out as a fixed size.  
    <VBFixedString(10)> Public LastName As String  
    <VBFixedString(7)> Public Title As String  
    <VBFixedString(2)> Public Rank As String  
End Structure  
```  
  
### <a name="vbfixedarrayattribute"></a><span data-ttu-id="f3bb6-241">VBFixedArrayAttribute</span><span class="sxs-lookup"><span data-stu-id="f3bb6-241">VBFixedArrayAttribute</span></span>  
 <span data-ttu-id="f3bb6-242">Используйте `VBFixedArrayAttribute` Чтобы объявить массивы фиксированного размера.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-242">Use `VBFixedArrayAttribute` to declare arrays that are fixed in size.</span></span> <span data-ttu-id="f3bb6-243">Как Visual Basic строки массивы имеют переменную длину по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-243">Like Visual Basic strings, arrays are of variable length by default.</span></span> <span data-ttu-id="f3bb6-244">Этот атрибут полезен при сериализации или записи данных в файлы.</span><span class="sxs-lookup"><span data-stu-id="f3bb6-244">This attribute is useful when serializing or writing data to files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3bb6-245">См. также</span><span class="sxs-lookup"><span data-stu-id="f3bb6-245">See Also</span></span>  
 <span data-ttu-id="f3bb6-246"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="f3bb6-246"><xref:System.Reflection></span></span>   
 <span data-ttu-id="f3bb6-247"><xref:System.Attribute></xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="f3bb6-247"><xref:System.Attribute></span></span>   
<span data-ttu-id="f3bb6-248"> [Руководство по программированию на Visual Basic](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f3bb6-248"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="f3bb6-249"> [Атрибуты](https://msdn.microsoft.com/library/5x6cd29c) </span><span class="sxs-lookup"><span data-stu-id="f3bb6-249"> [Attributes](https://msdn.microsoft.com/library/5x6cd29c) </span></span>  
<span data-ttu-id="f3bb6-250"> [Отражение (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="f3bb6-250"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="f3bb6-251"> [Доступ к атрибутам с помощью отражения (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="f3bb6-251"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>
