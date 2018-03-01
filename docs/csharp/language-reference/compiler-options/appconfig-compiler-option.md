---
title: "-appconfig (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /appconfig
helpviewer_keywords:
- /appconfig compiler option [C#]
- -appconfig compiler option [C#]
- appconfig compiler option [C#]
ms.assetid: 1cdbcbcc-7813-4010-b5b8-e67c107c5a98
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a3f2c1bc9d0d3fec0635d284f64138f0432f59ef
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="-appconfig-c-compiler-options"></a><span data-ttu-id="3cd9b-102">-appconfig (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="3cd9b-102">-appconfig (C# Compiler Options)</span></span>
<span data-ttu-id="3cd9b-103">Параметр компилятора **-appconfig** позволяет приложению C# задать расположение файла конфигурации приложения сборки (app.config) в среде CLR во время привязки сборки.</span><span class="sxs-lookup"><span data-stu-id="3cd9b-103">The **-appconfig** compiler option enables a C# application to specify the location of an assembly's application configuration (app.config) file to the common language runtime (CLR) at assembly binding time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cd9b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cd9b-104">Syntax</span></span>  
  
```console  
-appconfig:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="3cd9b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3cd9b-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="3cd9b-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="3cd9b-106">Required.</span></span> <span data-ttu-id="3cd9b-107">Файл конфигурации приложения, содержащий параметры привязки сборки.</span><span class="sxs-lookup"><span data-stu-id="3cd9b-107">The application configuration file that contains assembly binding settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cd9b-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="3cd9b-108">Remarks</span></span>  
 <span data-ttu-id="3cd9b-109">Один из случаев использования параметра **-appconfig** — сложные сценарии, когда в сборке одновременно используются ссылки и на версию .NET Framework, и на версию .NET Framework для Silverlight определенной базовой сборки.</span><span class="sxs-lookup"><span data-stu-id="3cd9b-109">One use of **-appconfig** is advanced scenarios in which an assembly has to reference both the .NET Framework version and the .NET Framework for Silverlight version of a particular reference assembly at the same time.</span></span> <span data-ttu-id="3cd9b-110">Например, для конструктора XAML, написанного в Windows Presentation Foundation (WPF), может потребоваться ссылаться на оба рабочих стола WPF, для пользовательского интерфейса конструктора и для подмножества WPF, поставляемого с Silverlight.</span><span class="sxs-lookup"><span data-stu-id="3cd9b-110">For example, a XAML designer written in Windows Presentation Foundation (WPF) might have to reference both the WPF Desktop, for the designer's user interface, and the subset of WPF that is included with Silverlight.</span></span> <span data-ttu-id="3cd9b-111">Одна и та же сборка конструктора имеет доступ к обеим сборкам.</span><span class="sxs-lookup"><span data-stu-id="3cd9b-111">The same designer assembly has to access both assemblies.</span></span> <span data-ttu-id="3cd9b-112">По умолчанию отдельные ссылки вызывают ошибку компиляции, так как привязка сборки видит две эквивалентные сборки.</span><span class="sxs-lookup"><span data-stu-id="3cd9b-112">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span>  
  
 <span data-ttu-id="3cd9b-113">Параметр компилятора **-appconfig** позволяет указать расположение файла app.config, который отключает поведение по умолчанию с помощью тега `<supportPortability>`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3cd9b-113">The **-appconfig** compiler option enables you to specify the location of an app.config file that disables the default behavior by using a `<supportPortability>` tag, as shown in the following example.</span></span>  
  
 `<supportPortability PKT="7cec85d7bea7798e" enable="false"/>`  
  
 <span data-ttu-id="3cd9b-114">Компилятор передает расположение файла в логику с привязкой сборки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="3cd9b-114">The compiler passes the location of the file to the CLR's assembly-binding logic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3cd9b-115">При сборке приложения с помощью Microsoft Build Engine (MSBuild) можно задать параметр компилятора **-appconfig**, добавив тег свойства в CSPROJ-файл.</span><span class="sxs-lookup"><span data-stu-id="3cd9b-115">If you are using the Microsoft Build Engine (MSBuild) to build your application, you can set the **-appconfig** compiler option by adding a property tag to the .csproj file.</span></span> <span data-ttu-id="3cd9b-116">Чтобы использовать файл app.config, уже заданный в проекте, добавьте тег свойства `<UseAppConfigForCompiler>` в CSPROJ-файл и задайте для него значение `true`.</span><span class="sxs-lookup"><span data-stu-id="3cd9b-116">To use the app.config file that is already set in the project, add property tag `<UseAppConfigForCompiler>` to the .csproj file and set its value to `true`.</span></span> <span data-ttu-id="3cd9b-117">Чтобы указать другой файл app.config, добавьте тег свойства `<AppConfigForCompiler>` и задайте в качестве его значения расположение требуемого файла.</span><span class="sxs-lookup"><span data-stu-id="3cd9b-117">To specify a different app.config file, add property tag `<AppConfigForCompiler>` and set its value to the location of the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cd9b-118">Пример</span><span class="sxs-lookup"><span data-stu-id="3cd9b-118">Example</span></span>  
 <span data-ttu-id="3cd9b-119">В следующем примере показан файл app.config, позволяющий приложению иметь ссылки на реализации .NET Framework и .NET Framework для реализации Silverlight любой сборки .NET Framework, существующей в обеих реализациях.</span><span class="sxs-lookup"><span data-stu-id="3cd9b-119">The following example shows an app.config file that enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="3cd9b-120">Параметр компилятора **-appconfig** указывает расположение этого файла app.config.</span><span class="sxs-lookup"><span data-stu-id="3cd9b-120">The **-appconfig** compiler option specifies the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
      <runtime>  
      <assemblyBinding>  
            <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
            <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
      </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cd9b-121">См. также</span><span class="sxs-lookup"><span data-stu-id="3cd9b-121">See Also</span></span>  
 [<span data-ttu-id="3cd9b-122">Элемент \<supportPortability></span><span class="sxs-lookup"><span data-stu-id="3cd9b-122">\<supportPortability> Element</span></span>](../../../framework/configure-apps/file-schema/runtime/supportportability-element.md)  
 [<span data-ttu-id="3cd9b-123">Параметры компилятора C# в алфавитном порядке</span><span class="sxs-lookup"><span data-stu-id="3cd9b-123">C# Compiler Options Listed Alphabetically</span></span>](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)
