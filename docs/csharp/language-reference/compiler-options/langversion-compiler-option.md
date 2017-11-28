---
title: "-langversion (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
caps.latest.revision: "33"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d034958b14c54540aa175a23067d47bd5d850bab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="langversion-c-compiler-options"></a><span data-ttu-id="eda88-102">/langversion (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="eda88-102">/langversion (C# Compiler Options)</span></span>
<span data-ttu-id="eda88-103">Инструктирует компилятор принимать только синтаксис, включенный в заданную спецификацию языка C#.</span><span class="sxs-lookup"><span data-stu-id="eda88-103">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eda88-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eda88-104">Syntax</span></span>  
  
```console  
/langversion:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="eda88-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="eda88-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="eda88-106">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="eda88-106">The following values are valid:</span></span>  
  
|<span data-ttu-id="eda88-107">Параметр</span><span class="sxs-lookup"><span data-stu-id="eda88-107">Option</span></span>|<span data-ttu-id="eda88-108">Значение</span><span class="sxs-lookup"><span data-stu-id="eda88-108">Meaning</span></span>|  
|------------|-------------|  
|<span data-ttu-id="eda88-109">default</span><span class="sxs-lookup"><span data-stu-id="eda88-109">default</span></span>|<span data-ttu-id="eda88-110">Компилятор допускает использование любого допустимого синтаксиса языка, который он может поддерживать.</span><span class="sxs-lookup"><span data-stu-id="eda88-110">The compiler accepts all valid language syntax that it can support.</span></span> <span data-ttu-id="eda88-111"><sup id="TDefault">[По умолчанию](#FDefault)</sup></span><span class="sxs-lookup"><span data-stu-id="eda88-111"><sup id="TDefault">[Default](#FDefault)</sup></span></span>| 
|<span data-ttu-id="eda88-112">ISO-1</span><span class="sxs-lookup"><span data-stu-id="eda88-112">ISO-1</span></span>|<span data-ttu-id="eda88-113">Компилятор принимает только синтаксис, включенный в спецификацию ISO/IEC 23270:2003 C# (1.0/1.1) <sup id="TISO1">[ISO1](#FISO1)</sup></span><span class="sxs-lookup"><span data-stu-id="eda88-113">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.1) <sup id="TISO1">[ISO1](#FISO1)</sup></span></span>|  
|<span data-ttu-id="eda88-114">ISO-2</span><span class="sxs-lookup"><span data-stu-id="eda88-114">ISO-2</span></span>|<span data-ttu-id="eda88-115">Компилятор принимает только синтаксис, включенный в спецификацию ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup></span><span class="sxs-lookup"><span data-stu-id="eda88-115">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup></span></span>|
|<span data-ttu-id="eda88-116">3</span><span class="sxs-lookup"><span data-stu-id="eda88-116">3</span></span>|<span data-ttu-id="eda88-117">Компилятор принимает только синтаксис, включенный в спецификацию C# 3.0 или более раннюю <sup id="TCS3">[CS3](#FCS3)</sup></span><span class="sxs-lookup"><span data-stu-id="eda88-117">The compiler accepts only syntax that is included in C# 3.0 or lower <sup id="TCS3">[CS3](#FCS3)</sup></span></span>|
|<span data-ttu-id="eda88-118">4</span><span class="sxs-lookup"><span data-stu-id="eda88-118">4</span></span>|<span data-ttu-id="eda88-119">Компилятор принимает только синтаксис, включенный в спецификацию C# 4.0 или более раннюю <sup id="TCS4">[CS4](#FCS4)</sup></span><span class="sxs-lookup"><span data-stu-id="eda88-119">The compiler accepts only syntax that is included in C# 4.0 or lower <sup id="TCS4">[CS4](#FCS4)</sup></span></span>|
|<span data-ttu-id="eda88-120">5</span><span class="sxs-lookup"><span data-stu-id="eda88-120">5</span></span>|<span data-ttu-id="eda88-121">Компилятор принимает только синтаксис, включенный в спецификацию C# 5.0 или более раннюю <sup id="TCS5">[CS5](#FCS5)</sup></span><span class="sxs-lookup"><span data-stu-id="eda88-121">The compiler accepts only syntax that is included in C# 5.0 or lower <sup id="TCS5">[CS5](#FCS5)</sup></span></span>|
|<span data-ttu-id="eda88-122">6</span><span class="sxs-lookup"><span data-stu-id="eda88-122">6</span></span>|<span data-ttu-id="eda88-123">Компилятор принимает только синтаксис, включенный в спецификацию C# 6.0 или более раннюю <sup id="TCS6">[CS6](#FCS6)</sup></span><span class="sxs-lookup"><span data-stu-id="eda88-123">The compiler accepts only syntax that is included in C# 6.0 or lower <sup id="TCS6">[CS6](#FCS6)</sup></span></span>|
|<span data-ttu-id="eda88-124">7</span><span class="sxs-lookup"><span data-stu-id="eda88-124">7</span></span>|<span data-ttu-id="eda88-125">Компилятор принимает только синтаксис, включенный в спецификацию C# 7.0 или более раннюю <sup id="TCS7">[CS7](#FCS7)</sup></span><span class="sxs-lookup"><span data-stu-id="eda88-125">The compiler accepts only syntax that is included in C# 7.0 or lower <sup id="TCS7">[CS7](#FCS7)</sup></span></span>|
|<span data-ttu-id="eda88-126">latest</span><span class="sxs-lookup"><span data-stu-id="eda88-126">latest</span></span>|<span data-ttu-id="eda88-127">Компилятор допускает использование любого допустимого синтаксиса языка, который он может поддерживать.</span><span class="sxs-lookup"><span data-stu-id="eda88-127">The compiler accepts all valid language syntax that it can support.</span></span> <span data-ttu-id="eda88-128"><sup id="TLatest">[Последняя версия](#FLatest)</sup></span><span class="sxs-lookup"><span data-stu-id="eda88-128"><sup id="TLatest">[Latest](#FLatest)</sup></span></span>|
<!--- Uncomment and move these above
|latest| once they're officially released
|7.1|The compiler accepts only syntax that is included in C# 7.1 or lower <sup id="TCS71">[CS71](#FCS71)</sup>|
|7.2|The compiler accepts only syntax that is included in C# 7.2 or lower <sup id="TCS71">[CS72](#FCS72)</sup>|
|8|The compiler accepts only syntax that is included in C# 8 or lower <sup id="TCS71">[CS8](#FCS8)</sup>|
-->

  
## <a name="remarks"></a><span data-ttu-id="eda88-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="eda88-129">Remarks</span></span>  
 <span data-ttu-id="eda88-130">Параметр компилятора **/langversion** не влияет на метаданные, на которые ссылается ваше приложение C#.</span><span class="sxs-lookup"><span data-stu-id="eda88-130">Metadata referenced by your C# application is not subject to **/langversion** compiler option.</span></span>  
  
 <span data-ttu-id="eda88-131">Поскольку каждая версия компилятора C# содержит расширения для спецификации языка, параметр **/langversion** не позволяет получить функциональные возможности, аналогичные более ранней версии компилятора.</span><span class="sxs-lookup"><span data-stu-id="eda88-131">Because each version of the C# compiler contains extensions to the language specification, **/langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>  
 
 <span data-ttu-id="eda88-132">Кроме того, в отличие от обновлений версии C#, которые обычно совпадают с основными выпусками платформы .Net Framework, новые функции и возможности синтаксиса могут быть не привязаны к конкретной версии этой платформы.</span><span class="sxs-lookup"><span data-stu-id="eda88-132">Additionally, while C# version updates generally coincide with major .Net Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="eda88-133">Для работы с новыми версиями требуется обновление компилятора, которое также выпускается с новой редакцией C#. Тем не менее для каждой функции определен собственный набор минимальных требований к API .Net или общеязыковой среде выполнения, в результате чего их можно выполнять на более ранних версиях платформы, добавив необходимые пакеты NuGet или другие библиотеки.</span><span class="sxs-lookup"><span data-stu-id="eda88-133">While the new features will definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .Net API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>
  
 <span data-ttu-id="eda88-134">Независимо от того, какой параметр **/langversion** вы задали, для создания файлов с расширением EXE или DLL будет использоваться текущая версия общеязыковой среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="eda88-134">Regardless of which **/langversion** setting you use, you will use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="eda88-135">Единственным исключением являются дружественные сборки и [/moduleassemblyname (параметр компилятора C#)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), которые работают при установке параметра **/langversion:ISO-1**.</span><span class="sxs-lookup"><span data-stu-id="eda88-135">One exception is friend assemblies and [/moduleassemblyname (C# Compiler Option)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), which work under **/langversion:ISO-1**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="eda88-136">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="eda88-136">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="eda88-137">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="eda88-137">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="eda88-138">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="eda88-138">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="eda88-139">Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="eda88-139">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="eda88-140">Измените значение свойства **Версия языка**.</span><span class="sxs-lookup"><span data-stu-id="eda88-140">Modify the **Language Version** property.</span></span>  
  
 <span data-ttu-id="eda88-141">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="eda88-141">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>  
    
## <a name="see-also"></a><span data-ttu-id="eda88-142">См. также</span><span class="sxs-lookup"><span data-stu-id="eda88-142">See Also</span></span>  
 [<span data-ttu-id="eda88-143">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="eda88-143">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="eda88-144">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="eda88-144">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 
### <a name="c-language-specification"></a><span data-ttu-id="eda88-145">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="eda88-145">C# Language Specification</span></span>
 <span data-ttu-id="eda88-146">[Справочник по спецификации языка C#](../../../csharp/language-reference/language-specification/index.md): .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="eda88-146">[C# Language Specification Reference](../../../csharp/language-reference/language-specification/index.md) : .NET Foundation</span></span>  
 <span data-ttu-id="eda88-147">Информационные технологии C# 1.0/1.1 [ISO/IEC 23270:2003](https://www.iso.org/standard/36768.html) — спецификация языка C#: каталог ISO</span><span class="sxs-lookup"><span data-stu-id="eda88-147">C# 1.0/1.1 [ISO/IEC 23270:2003](https://www.iso.org/standard/36768.html) Information technology -- C# Language Specification : ISO Catalogue</span></span>  
 <span data-ttu-id="eda88-148">Информационные технологии C# 2.0 [ISO/IEC 23270:2006](https://www.iso.org/standard/42926.html) — спецификация языка C#: каталог ISO</span><span class="sxs-lookup"><span data-stu-id="eda88-148">C# 2.0 [ISO/IEC 23270:2006](https://www.iso.org/standard/42926.html) Information technology -- C# Language Specification : ISO Catalogue</span></span>  
 <span data-ttu-id="eda88-149">C# 2.0 [c042926_ISO_IEC_23270_2006(E).zip](http://go.microsoft.com/fwlink/?LinkId=144406) ISO/IEC 23270:2006 в формате PDF: общедоступные стандарты ISO</span><span class="sxs-lookup"><span data-stu-id="eda88-149">C# 2.0 [c042926_ISO_IEC_23270_2006(E).zip](http://go.microsoft.com/fwlink/?LinkId=144406) ISO/IEC 23270:2006 in PDF format : ISO Freely Available Standards</span></span>  
 <span data-ttu-id="eda88-150">C# 3.0 [CSharp Language Specification.doc](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc) — спецификация языка C# версии 3.0: корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="eda88-150">C# 3.0 [CSharp Language Specification.doc](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc) C# Language Specification Version 3.0 : Microsoft Corporation</span></span>  
 <span data-ttu-id="eda88-151">C# 4.0 [Ecma-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf) — стандарт ECMA-334, 4-й выпуск</span><span class="sxs-lookup"><span data-stu-id="eda88-151">C# 4.0 [Ecma-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf) Standard ECMA-334 4th Edition</span></span>    
 <span data-ttu-id="eda88-152">C# 5.0 [CSharp Language Specification.docx](https://www.microsoft.com/download/details.aspx?id=7029) — спецификация языка C# версии 5.0: корпорация Майкрософт</span><span class="sxs-lookup"><span data-stu-id="eda88-152">C# 5.0 [CSharp Language Specification.docx](https://www.microsoft.com/download/details.aspx?id=7029) C# Language Specification Version 5.0 : Microsoft Corporation</span></span>  
 <span data-ttu-id="eda88-153">C# 6.0 [README.md](https://github.com/dotnet/csharplang/blob/master/spec/README.md) спецификация языка C# версии 6 (неофициальный проект): .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="eda88-153">C# 6.0 [README.md](https://github.com/dotnet/csharplang/blob/master/spec/README.md) C# Language Specification Version 6 - Unofficial Draft : .NET Foundation</span></span>  
 <span data-ttu-id="eda88-154">C# 7.0 (в настоящее время недоступно)</span><span class="sxs-lookup"><span data-stu-id="eda88-154">C# 7.0 (not currently available)</span></span>  

<!--- Uncomment and add to the above when they become officially released
 C# 7.1 (spec is not yet finished)  
 C# 7.2 (spec is not yet finished)  
 C# 8.0 (spec is not yet finished)  
-->

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a><span data-ttu-id="eda88-155">Минимальная версия компилятора, необходимая для поддержки всех возможностей языка</span><span class="sxs-lookup"><span data-stu-id="eda88-155">Minimum compiler version needed to support all language features</span></span>   
<span data-ttu-id="eda88-156">[↩](#TDefault)<a name="FDefault">По умолчанию</a>, <a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .Net 2002 или встроенный компилятор .Net Framework 1.0</span><span class="sxs-lookup"><span data-stu-id="eda88-156">[↩](#TDefault)<a name="FDefault">Default</a>, <a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .Net 2002 or bundled .Net Framework 1.0 compiler</span></span>     
<span data-ttu-id="eda88-157">[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 или встроенный компилятор .Net Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="eda88-157">[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 or bundled .Net Framework 2.0 compiler</span></span>    
<span data-ttu-id="eda88-158">[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 или встроенный компилятор .Net Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="eda88-158">[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 or bundled .Net Framework 3.5 compiler</span></span>    
<span data-ttu-id="eda88-159">[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 или встроенный компилятор .Net Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="eda88-159">[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 or bundled .Net Framework 4.0 compiler</span></span>    
<span data-ttu-id="eda88-160">[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 или встроенный компилятор .Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="eda88-160">[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 or bundled .Net Framework 4.5 compiler</span></span>    
<span data-ttu-id="eda88-161">[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015</span><span class="sxs-lookup"><span data-stu-id="eda88-161">[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015</span></span>    
<span data-ttu-id="eda88-162">[↩](#TCS7)<a name="FCS7">CS7</a>, <a name="FLatest">последняя версия</a>: Microsoft Visual Studio/Build Tools 2017</span><span class="sxs-lookup"><span data-stu-id="eda88-162">[↩](#TCS7)<a name="FCS7">CS7</a>, <a name="FLatest">Latest</a>: Microsoft Visual Studio/Build Tools 2017</span></span>   

<!--- Uncomment and add to the above when they become officially released
[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS8)<a name="FCS71">CS8</a>: Microsoft Visual Studio/Build Tools 20??    
-->
