---
title: -vbruntime
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbruntime
- -vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6c6529fabddc75fb6ac751e0314011f05db7869
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="-vbruntime"></a><span data-ttu-id="a3d07-102">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="a3d07-102">-vbruntime</span></span>
<span data-ttu-id="a3d07-103">Указывает, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic или со ссылкой на конкретную библиотеку времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="a3d07-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3d07-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a3d07-104">Syntax</span></span>  
  
```  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="a3d07-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a3d07-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="a3d07-106">Компиляцию без ссылки на библиотеку времени выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a3d07-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="a3d07-107">Компиляция со ссылкой на значение по умолчанию библиотеки времени выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a3d07-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="a3d07-108">Компиляцию без ссылки на библиотеку времени выполнения Visual Basic и внедрения в сборку базовую функциональность библиотеки времени выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a3d07-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="a3d07-109">Компиляция со ссылкой на указанную библиотеку (DLL).</span><span class="sxs-lookup"><span data-stu-id="a3d07-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3d07-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="a3d07-110">Remarks</span></span>  
 <span data-ttu-id="a3d07-111">`-vbruntime` Параметр компилятора позволяет указать, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a3d07-111">The `-vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="a3d07-112">Если компиляция выполняется без ссылки на библиотеку времени выполнения Visual Basic, ошибки или предупреждения регистрируются в код или языковой конструкции, которые создает вызов вспомогательный среды выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a3d07-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="a3d07-113">(A *Вспомогательная среда выполнения Visual Basic* является функция, определенная в Microsoft.VisualBasic.dll, которая вызывается во время выполнения, чтобы выполнить конкретную семантику языка.)</span><span class="sxs-lookup"><span data-stu-id="a3d07-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="a3d07-114">`-vbruntime+` Же поведение, которое возникает, если он не создает параметр `-vbruntime` указан ключ.</span><span class="sxs-lookup"><span data-stu-id="a3d07-114">The `-vbruntime+` option produces the same behavior that occurs if no `-vbruntime` switch is specified.</span></span> <span data-ttu-id="a3d07-115">Можно использовать `-vbruntime+` могут переопределить предыдущих `-vbruntime` коммутаторов.</span><span class="sxs-lookup"><span data-stu-id="a3d07-115">You can use the `-vbruntime+` option to override previous `-vbruntime` switches.</span></span>  
  
 <span data-ttu-id="a3d07-116">Большинство объектов `My` тип недоступны при использовании `-vbruntime-` или `-vbruntime:path` параметры.</span><span class="sxs-lookup"><span data-stu-id="a3d07-116">Most objects of the `My` type are unavailable when you use the `-vbruntime-` or `-vbruntime:path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="a3d07-117">Внедрение основных функциональных возможностей среды выполнения Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a3d07-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="a3d07-118">`-vbruntime*` Позволяет компилировать без ссылки на библиотеку времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="a3d07-118">The `-vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="a3d07-119">Вместо этого основные функции из библиотеки времени выполнения Visual Basic внедренных в сборку пользователя.</span><span class="sxs-lookup"><span data-stu-id="a3d07-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="a3d07-120">Этот параметр можно использовать, если приложение работает на платформах, которые не содержат среда выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a3d07-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="a3d07-121">Внедряются следующие компоненты времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="a3d07-121">The following runtime members are embedded:</span></span>  
  
-   <span data-ttu-id="a3d07-122">Класс <xref:Microsoft.VisualBasic.CompilerServices.Conversions></span><span class="sxs-lookup"><span data-stu-id="a3d07-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
-   <span data-ttu-id="a3d07-123">Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29></span><span class="sxs-lookup"><span data-stu-id="a3d07-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
-   <span data-ttu-id="a3d07-124">Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="a3d07-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
-   <span data-ttu-id="a3d07-125">Метод <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29></span><span class="sxs-lookup"><span data-stu-id="a3d07-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
-   <span data-ttu-id="a3d07-126"><xref:Microsoft.VisualBasic.Constants.vbBack> Константа</span><span class="sxs-lookup"><span data-stu-id="a3d07-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
-   <span data-ttu-id="a3d07-127"><xref:Microsoft.VisualBasic.Constants.vbCr> Константа</span><span class="sxs-lookup"><span data-stu-id="a3d07-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
-   <span data-ttu-id="a3d07-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> Константа</span><span class="sxs-lookup"><span data-stu-id="a3d07-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
-   <span data-ttu-id="a3d07-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> Константа</span><span class="sxs-lookup"><span data-stu-id="a3d07-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
-   <span data-ttu-id="a3d07-130"><xref:Microsoft.VisualBasic.Constants.vbLf> Константа</span><span class="sxs-lookup"><span data-stu-id="a3d07-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
-   <span data-ttu-id="a3d07-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> Константа</span><span class="sxs-lookup"><span data-stu-id="a3d07-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
-   <span data-ttu-id="a3d07-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> Константа</span><span class="sxs-lookup"><span data-stu-id="a3d07-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
-   <span data-ttu-id="a3d07-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> Константа</span><span class="sxs-lookup"><span data-stu-id="a3d07-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
-   <span data-ttu-id="a3d07-134"><xref:Microsoft.VisualBasic.Constants.vbTab> Константа</span><span class="sxs-lookup"><span data-stu-id="a3d07-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
-   <span data-ttu-id="a3d07-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> Константа</span><span class="sxs-lookup"><span data-stu-id="a3d07-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
-   <span data-ttu-id="a3d07-136">Некоторые объекты `My` типа</span><span class="sxs-lookup"><span data-stu-id="a3d07-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="a3d07-137">Если компиляция выполняется с помощью `-vbruntime*` параметр и код ссылается на элемент из библиотеки среды выполнения Visual Basic, не внедрены в основных функциональных возможностей, компилятор возвращает ошибку, указывающую, что член недоступен.</span><span class="sxs-lookup"><span data-stu-id="a3d07-137">If you compile using the `-vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="a3d07-138">Создание ссылок на указанную библиотеку</span><span class="sxs-lookup"><span data-stu-id="a3d07-138">Referencing a specified library</span></span>  
 <span data-ttu-id="a3d07-139">Можно использовать `path` аргумент для компиляции со ссылкой на библиотеку времени выполнения пользовательского вместо значения по умолчанию библиотеки времени выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a3d07-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="a3d07-140">Если значение `path` аргумент — полный путь к DLL-файлу, компилятор будет использовать этот файл как библиотеку среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a3d07-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="a3d07-141">Если значение `path` аргумент не является полный путь к библиотеке DLL, компилятор Visual Basic будет сначала искать идентифицированной библиотеки DLL в текущей папке.</span><span class="sxs-lookup"><span data-stu-id="a3d07-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="a3d07-142">Затем будет выполнен поиск по пути, указанному с помощью [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="a3d07-142">It will then search in the path that you have specified by using the [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="a3d07-143">Если `-sdkpath` не используется параметр компилятора, компилятор будет искать идентифицированной библиотеки DLL в папке .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="a3d07-143">If the `-sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3d07-144">Пример</span><span class="sxs-lookup"><span data-stu-id="a3d07-144">Example</span></span>  
 <span data-ttu-id="a3d07-145">В следующем примере показано, как использовать `-vbruntime` для компиляции со ссылкой на пользовательскую библиотеку.</span><span class="sxs-lookup"><span data-stu-id="a3d07-145">The following example shows how to use the `-vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3d07-146">См. также</span><span class="sxs-lookup"><span data-stu-id="a3d07-146">See Also</span></span>  
 [<span data-ttu-id="a3d07-147">Основные Visual Basic — новый режим компиляции в Visual Studio 2010 SP1</span><span class="sxs-lookup"><span data-stu-id="a3d07-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)  
 [<span data-ttu-id="a3d07-148">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="a3d07-148">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="a3d07-149">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="a3d07-149">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="a3d07-150">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="a3d07-150">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
