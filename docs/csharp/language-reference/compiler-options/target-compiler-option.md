---
title: -target (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /target
helpviewer_keywords:
- target compiler options [C#]
- /target compiler options [C#]
- assemblies [C#], compiling
- -target compiler options [C#]
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
ms.openlocfilehash: a337ecbc614ff40eda42fc5263dbb52aa92b905f
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45668149"
---
# <a name="-target-c-compiler-options"></a><span data-ttu-id="5b9c8-102">-target (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="5b9c8-102">-target (C# Compiler Options)</span></span>
<span data-ttu-id="5b9c8-103">Параметр компилятора **-target** можно задать в одной из четырех форм:</span><span class="sxs-lookup"><span data-stu-id="5b9c8-103">The **-target** compiler option can be specified in one of four forms:</span></span>  
  
 [<span data-ttu-id="5b9c8-104">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="5b9c8-104">-target:appcontainerexe</span></span>](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
 <span data-ttu-id="5b9c8-105">Создание EXE-файла для приложений [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b9c8-105">To create an .exe file for [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [<span data-ttu-id="5b9c8-106">/target:exe</span><span class="sxs-lookup"><span data-stu-id="5b9c8-106">-target:exe</span></span>](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md)  
 <span data-ttu-id="5b9c8-107">Создание EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="5b9c8-107">To create an .exe file.</span></span>  
  
 [<span data-ttu-id="5b9c8-108">/target:library</span><span class="sxs-lookup"><span data-stu-id="5b9c8-108">-target:library</span></span>](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md)  
 <span data-ttu-id="5b9c8-109">Создание библиотеки кодов.</span><span class="sxs-lookup"><span data-stu-id="5b9c8-109">To create a code library.</span></span>  
  
 [<span data-ttu-id="5b9c8-110">/target:module</span><span class="sxs-lookup"><span data-stu-id="5b9c8-110">-target:module</span></span>](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)  
 <span data-ttu-id="5b9c8-111">Создание модуля.</span><span class="sxs-lookup"><span data-stu-id="5b9c8-111">To create a module.</span></span>  
  
 [<span data-ttu-id="5b9c8-112">/target:winexe</span><span class="sxs-lookup"><span data-stu-id="5b9c8-112">-target:winexe</span></span>](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 <span data-ttu-id="5b9c8-113">Создание программы Windows.</span><span class="sxs-lookup"><span data-stu-id="5b9c8-113">To create a Windows program.</span></span>  
  
 [<span data-ttu-id="5b9c8-114">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="5b9c8-114">-target:winmdobj</span></span>](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
 <span data-ttu-id="5b9c8-115">Создание промежуточного WINMDOBJ-файла.</span><span class="sxs-lookup"><span data-stu-id="5b9c8-115">To create an intermediate .winmdobj file.</span></span>  
  
 <span data-ttu-id="5b9c8-116">Если **-target:module** не указан, **-target** предписывает разместить манифест сборки .NET Framework в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="5b9c8-116">Unless you specify **-target:module**, **-target** causes a .NET Framework assembly manifest to be placed in an output file.</span></span> <span data-ttu-id="5b9c8-117">Дополнительные сведения см. в разделах [Сборки в среде CLR](../../../framework/app-domains/assemblies-in-the-common-language-runtime.md) и [Общие атрибуты](../../programming-guide/concepts/attributes/common-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="5b9c8-117">For more information, see [Assemblies in the Common Language Runtime](../../../framework/app-domains/assemblies-in-the-common-language-runtime.md) and [Common Attributes](../../programming-guide/concepts/attributes/common-attributes.md).</span></span>  
  
 <span data-ttu-id="5b9c8-118">Манифест сборки помещается в первый выходной файл EXE в компиляции или в первый файл DLL, если выходной файл EXE не существует.</span><span class="sxs-lookup"><span data-stu-id="5b9c8-118">The assembly manifest is placed in the first .exe output file in the compilation or in the first DLL, if there is no .exe output file.</span></span> <span data-ttu-id="5b9c8-119">Например, в следующей командной строке манифест будут помещен в `1.exe`:</span><span class="sxs-lookup"><span data-stu-id="5b9c8-119">For example, in the following command line, the manifest will be placed in `1.exe`:</span></span>  
  
```console  
csc -out:1.exe t1.cs -out:2.netmodule t2.cs  
```  
  
 <span data-ttu-id="5b9c8-120">При каждой компиляции компилятор создает только один манифест сборки.</span><span class="sxs-lookup"><span data-stu-id="5b9c8-120">The compiler creates only one assembly manifest per compilation.</span></span> <span data-ttu-id="5b9c8-121">В манифест сборки добавляются сведения обо всех файлах в компиляции.</span><span class="sxs-lookup"><span data-stu-id="5b9c8-121">Information about all files in a compilation is placed in the assembly manifest.</span></span> <span data-ttu-id="5b9c8-122">Все выходные файлы, кроме созданных с **-target:module**, могут содержать манифест сборки.</span><span class="sxs-lookup"><span data-stu-id="5b9c8-122">All output files except those created with **-target:module** can contain an assembly manifest.</span></span> <span data-ttu-id="5b9c8-123">При создании нескольких выходных файлов в командной строке может быть создан только один манифест сборки, который добавляется в первый выходной файл, указанный в командной строке.</span><span class="sxs-lookup"><span data-stu-id="5b9c8-123">When producing multiple output files at the command line, only one assembly manifest can be created and it must go into the first output file specified on the command line.</span></span> <span data-ttu-id="5b9c8-124">Каким бы ни был выходной файл (**-target:exe**, **-target:winexe**, **-target:library** или **-target:module**), все остальные выходные файлы в той же компиляции должны быть модулями (**-target:module**).</span><span class="sxs-lookup"><span data-stu-id="5b9c8-124">No matter what the first output file is (**-target:exe**, **-target:winexe**, **-target:library** or **-target:module**), any other output files produced in the same compilation must be modules (**-target:module**).</span></span>  
  
 <span data-ttu-id="5b9c8-125">При создании сборки можно указать, что код полностью или частично CLS-совместим с атрибутом <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5b9c8-125">If you create an assembly, you can indicate that all or part of your code is CLS compliant with the <xref:System.CLSCompliantAttribute> attribute.</span></span>  
  
```csharp  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 <span data-ttu-id="5b9c8-126">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="5b9c8-126">For more information about setting this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b9c8-127">См. также</span><span class="sxs-lookup"><span data-stu-id="5b9c8-127">See Also</span></span>  

- [<span data-ttu-id="5b9c8-128">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="5b9c8-128">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="5b9c8-129">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="5b9c8-129">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
- [<span data-ttu-id="5b9c8-130">-subsystemversion (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="5b9c8-130">-subsystemversion (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)
