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
ms.openlocfilehash: 7736b8850a7b09f7212e83e05acf0e1994bce0fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-target-c-compiler-options"></a>-target (параметры компилятора C#)
Параметр компилятора **-target** можно задать в одной из четырех форм:  
  
 [/target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
 Создание EXE-файла для приложений [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].  
  
 [/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md)  
 Создание EXE-файла.  
  
 [/target:library](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md)  
 Создание библиотеки кодов.  
  
 [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)  
 Создание модуля.  
  
 [/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 Создание программы Windows.  
  
 [/target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
 Создание промежуточного WINMDOBJ-файла.  
  
 Если **-target:module** не указан, **-target** предписывает разместить манифест сборки .NET Framework в выходном файле. Дополнительные сведения см. в разделах [Сборки в среде CLR](../../../framework/app-domains/assemblies-in-the-common-language-runtime.md) и [Общие атрибуты](../../programming-guide/concepts/attributes/common-attributes.md).  
  
 Манифест сборки помещается в первый выходной файл EXE в компиляции или в первый файл DLL, если выходной файл EXE не существует. Например, в следующей командной строке манифест будут помещен в `1.exe`:  
  
```console  
csc -out:1.exe t1.cs -out:2.netmodule t2.cs  
```  
  
 При каждой компиляции компилятор создает только один манифест сборки. В манифест сборки добавляются сведения обо всех файлах в компиляции. Все выходные файлы, кроме созданных с **-target:module**, могут содержать манифест сборки. При создании нескольких выходных файлов в командной строке может быть создан только один манифест сборки, который добавляется в первый выходной файл, указанный в командной строке. Каким бы ни был выходной файл (**-target:exe**, **-target:winexe**, **-target:library** или **-target:module**), все остальные выходные файлы в той же компиляции должны быть модулями (**-target:module**).  
  
 При создании сборки можно указать, что код полностью или частично CLS-совместим с атрибутом <xref:System.CLSCompliantAttribute>.  
  
```csharp  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)  
 [-subsystemversion (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)
