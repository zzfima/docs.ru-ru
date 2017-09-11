---
title: "/ vbruntime | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbruntime
- /vbruntime
dev_langs:
- VB
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: cb07ed8c2f6070079cc51c290ff5a61305c5a5d3
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="vbruntime"></a><span data-ttu-id="9ea6d-102">/vbruntime</span><span class="sxs-lookup"><span data-stu-id="9ea6d-102">/vbruntime</span></span>
<span data-ttu-id="9ea6d-103">Указывает, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic или со ссылкой на конкретную библиотеку времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ea6d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ea6d-104">Syntax</span></span>  
  
```  
/vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="9ea6d-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="9ea6d-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="9ea6d-106">Компиляция без ссылки на библиотеку времени выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="9ea6d-107">Компиляция со ссылкой на значение по умолчанию библиотеки времени выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="9ea6d-108">Компиляция без ссылки на библиотеку времени выполнения Visual Basic и внедрения в сборку базовую функциональность библиотеки времени выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="9ea6d-109">Компиляция со ссылкой на указанную библиотеку (DLL).</span><span class="sxs-lookup"><span data-stu-id="9ea6d-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ea6d-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="9ea6d-110">Remarks</span></span>  
 <span data-ttu-id="9ea6d-111">`/vbruntime` Параметр компилятора позволяет указать, что компилятор должен компилировать без ссылки на библиотеку времени выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-111">The `/vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="9ea6d-112">Если компиляция выполняется без ссылки на библиотеку времени выполнения Visual Basic, ошибки или предупреждения регистрируются на код или языковой конструкции, которые создает вызов вспомогательной среды выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="9ea6d-113">(Объект *Вспомогательная среда выполнения Visual Basic* является функцией, определяемой в Microsoft.VisualBasic.dll, которая вызывается во время выполнения, чтобы выполнить конкретную семантику языка.)</span><span class="sxs-lookup"><span data-stu-id="9ea6d-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="9ea6d-114">`/vbruntime+` Параметр создает такое же поведение, которое возникает, если не `/vbruntime` указан ключ.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-114">The `/vbruntime+` option produces the same behavior that occurs if no `/vbruntime` switch is specified.</span></span> <span data-ttu-id="9ea6d-115">Можно использовать `/vbruntime+` могут переопределить предыдущих `/vbruntime` коммутаторов.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-115">You can use the `/vbruntime+` option to override previous `/vbruntime` switches.</span></span>  
  
 <span data-ttu-id="9ea6d-116">Большинство объектов `My` тип недоступны при использовании `/vbruntime-` или `vbruntime:``path` параметры.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-116">Most objects of the `My` type are unavailable when you use the `/vbruntime-` or `vbruntime:``path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="9ea6d-117">Внедрение основные функциональные возможности среды выполнения Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ea6d-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="9ea6d-118">`/vbruntime*` Вариант позволяет выполнять компиляцию без ссылки на библиотеку времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-118">The `/vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="9ea6d-119">Вместо этого основных функций из библиотеки времени выполнения Visual Basic внедренного в сборку пользователя.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="9ea6d-120">Этот параметр можно использовать, если приложение выполняется на платформах, которые не содержат среда выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="9ea6d-121">Внедренные следующие компоненты времени выполнения:</span><span class="sxs-lookup"><span data-stu-id="9ea6d-121">The following runtime members are embedded:</span></span>  
  
-   <span data-ttu-id="9ea6d-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions>класс</xref:Microsoft.VisualBasic.CompilerServices.Conversions></span><span class="sxs-lookup"><span data-stu-id="9ea6d-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
-   <span data-ttu-id="9ea6d-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>метод</xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29></span><span class="sxs-lookup"><span data-stu-id="9ea6d-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
-   <span data-ttu-id="9ea6d-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>метод</xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="9ea6d-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
-   <span data-ttu-id="9ea6d-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>метод</xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29></span><span class="sxs-lookup"><span data-stu-id="9ea6d-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
-   <span data-ttu-id="9ea6d-126"><xref:Microsoft.VisualBasic.Constants.vbBack>Константа</xref:Microsoft.VisualBasic.Constants.vbBack></span><span class="sxs-lookup"><span data-stu-id="9ea6d-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
-   <span data-ttu-id="9ea6d-127"><xref:Microsoft.VisualBasic.Constants.vbCr>Константа</xref:Microsoft.VisualBasic.Constants.vbCr></span><span class="sxs-lookup"><span data-stu-id="9ea6d-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
-   <span data-ttu-id="9ea6d-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf>Константа</xref:Microsoft.VisualBasic.Constants.vbCrLf></span><span class="sxs-lookup"><span data-stu-id="9ea6d-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
-   <span data-ttu-id="9ea6d-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed>Константа</xref:Microsoft.VisualBasic.Constants.vbFormFeed></span><span class="sxs-lookup"><span data-stu-id="9ea6d-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
-   <span data-ttu-id="9ea6d-130"><xref:Microsoft.VisualBasic.Constants.vbLf>Константа</xref:Microsoft.VisualBasic.Constants.vbLf></span><span class="sxs-lookup"><span data-stu-id="9ea6d-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
-   <span data-ttu-id="9ea6d-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine>Константа</xref:Microsoft.VisualBasic.Constants.vbNewLine></span><span class="sxs-lookup"><span data-stu-id="9ea6d-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
-   <span data-ttu-id="9ea6d-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar>Константа</xref:Microsoft.VisualBasic.Constants.vbNullChar></span><span class="sxs-lookup"><span data-stu-id="9ea6d-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
-   <span data-ttu-id="9ea6d-133"><xref:Microsoft.VisualBasic.Constants.vbNullString>Константа</xref:Microsoft.VisualBasic.Constants.vbNullString></span><span class="sxs-lookup"><span data-stu-id="9ea6d-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
-   <span data-ttu-id="9ea6d-134"><xref:Microsoft.VisualBasic.Constants.vbTab>Константа</xref:Microsoft.VisualBasic.Constants.vbTab></span><span class="sxs-lookup"><span data-stu-id="9ea6d-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
-   <span data-ttu-id="9ea6d-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab>Константа</xref:Microsoft.VisualBasic.Constants.vbVerticalTab></span><span class="sxs-lookup"><span data-stu-id="9ea6d-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
-   <span data-ttu-id="9ea6d-136">Некоторые объекты `My` типа</span><span class="sxs-lookup"><span data-stu-id="9ea6d-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="9ea6d-137">Если компиляция выполняется с помощью `/vbruntime*` параметр и код ссылается на элемент из библиотеки времени выполнения Visual Basic, который не внедрен с основными функциями, компилятор возвращает ошибку, указывающую, что элемент недоступен.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-137">If you compile using the `/vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="9ea6d-138">Ссылка на указанную библиотеку</span><span class="sxs-lookup"><span data-stu-id="9ea6d-138">Referencing a specified library</span></span>  
 <span data-ttu-id="9ea6d-139">Можно использовать `path` аргумент для компиляции со ссылкой на библиотеку настраиваемую среду выполнения вместо библиотеки времени выполнения Visual Basic по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="9ea6d-140">Если значение `path` аргумент — полный путь к библиотеке DLL, компилятор будет использовать этот файл как библиотеку среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="9ea6d-141">Если значение `path` аргумент не является полный путь к библиотеке DLL, компилятор Visual Basic будет сначала поиск идентифицированной библиотеки DLL в текущей папке.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="9ea6d-142">Затем выполнит поиск по пути, указанному с помощью [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-142">It will then search in the path that you have specified by using the [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="9ea6d-143">Если `/sdkpath` не используется параметр компилятора, компилятор будет искать идентифицированной библиотеки DLL в папке .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="9ea6d-143">If the `/sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ea6d-144">Пример</span><span class="sxs-lookup"><span data-stu-id="9ea6d-144">Example</span></span>  
 <span data-ttu-id="9ea6d-145">В следующем примере показано, как использовать `/vbruntime` для компиляции со ссылкой на пользовательскую библиотеку.</span><span class="sxs-lookup"><span data-stu-id="9ea6d-145">The following example shows how to use the `/vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```  
vbc /vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ea6d-146">См. также</span><span class="sxs-lookup"><span data-stu-id="9ea6d-146">See Also</span></span>  
 <span data-ttu-id="9ea6d-147">[Visual Basic Core — новый режим компиляции в Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx) </span><span class="sxs-lookup"><span data-stu-id="9ea6d-147">[Visual Basic Core – New compilation mode in Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx) </span></span>  
<span data-ttu-id="9ea6d-148"> [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="9ea6d-148"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="9ea6d-149"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="9ea6d-149"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="9ea6d-150"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span><span class="sxs-lookup"><span data-stu-id="9ea6d-150"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span></span>
