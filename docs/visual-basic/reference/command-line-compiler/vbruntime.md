---
title: -vbruntime
ms.date: 03/13/2018
f1_keywords:
- vbruntime
- -vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
ms.openlocfilehash: 8c7789c6af7b82ecb40ecd73d09f64aa1da3fd4b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005053"
---
# <a name="-vbruntime"></a><span data-ttu-id="35776-102">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="35776-102">-vbruntime</span></span>
<span data-ttu-id="35776-103">Указывает, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic или со ссылкой на конкретную библиотеку времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="35776-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35776-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35776-104">Syntax</span></span>  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="35776-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="35776-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="35776-106">Скомпилируйте без ссылки на библиотеку времени выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="35776-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="35776-107">Скомпилируйте со ссылкой на библиотеку времени выполнения Visual Basic по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="35776-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="35776-108">Скомпилируйте без ссылки на библиотеку времени выполнения Visual Basic и внедрите основные функции из библиотеки среды выполнения Visual Basic в сборку.</span><span class="sxs-lookup"><span data-stu-id="35776-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="35776-109">Скомпилируйте со ссылкой на указанную библиотеку (DLL).</span><span class="sxs-lookup"><span data-stu-id="35776-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35776-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="35776-110">Remarks</span></span>  
 <span data-ttu-id="35776-111">Параметр компилятора `-vbruntime` позволяет указать, что компилятор должен компилироваться без ссылки на библиотеку времени выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="35776-111">The `-vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="35776-112">Если компиляция выполняется без ссылки на библиотеку времени выполнения Visual Basic, ошибки или предупреждения записываются в код или языковые конструкции, которые создают вызов вспомогательного метода среды выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="35776-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="35776-113">( *Вспомогательный объект среды выполнения Visual Basic* — это функция, определенная в Microsoft. VisualBasic. dll, которая вызывается во время выполнения для выполнения определенной семантики языка.)</span><span class="sxs-lookup"><span data-stu-id="35776-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="35776-114">Параметр `-vbruntime+` дает такое же поведение, которое происходит, если не указан параметр `-vbruntime`.</span><span class="sxs-lookup"><span data-stu-id="35776-114">The `-vbruntime+` option produces the same behavior that occurs if no `-vbruntime` switch is specified.</span></span> <span data-ttu-id="35776-115">Для переопределения предыдущих параметров `-vbruntime` можно использовать параметр `-vbruntime+`.</span><span class="sxs-lookup"><span data-stu-id="35776-115">You can use the `-vbruntime+` option to override previous `-vbruntime` switches.</span></span>  
  
 <span data-ttu-id="35776-116">Большинство объектов типа `My` недоступны при использовании параметров `-vbruntime-` или `-vbruntime:path`.</span><span class="sxs-lookup"><span data-stu-id="35776-116">Most objects of the `My` type are unavailable when you use the `-vbruntime-` or `-vbruntime:path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="35776-117">Внедрение основных функций среды выполнения Visual Basic</span><span class="sxs-lookup"><span data-stu-id="35776-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="35776-118">Параметр `-vbruntime*` позволяет компилировать без ссылки на библиотеку времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="35776-118">The `-vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="35776-119">Вместо этого основные функции из библиотеки среды выполнения Visual Basic встраиваются в сборку пользователя.</span><span class="sxs-lookup"><span data-stu-id="35776-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="35776-120">Этот параметр можно использовать, если приложение работает на платформах, которые не содержат Visual Basic среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="35776-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="35776-121">Внедряются следующие члены среды выполнения:</span><span class="sxs-lookup"><span data-stu-id="35776-121">The following runtime members are embedded:</span></span>  
  
- <span data-ttu-id="35776-122">Класс <xref:Microsoft.VisualBasic.CompilerServices.Conversions></span><span class="sxs-lookup"><span data-stu-id="35776-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
- <span data-ttu-id="35776-123">Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29></span><span class="sxs-lookup"><span data-stu-id="35776-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
- <span data-ttu-id="35776-124">Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="35776-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
- <span data-ttu-id="35776-125">Метод <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29></span><span class="sxs-lookup"><span data-stu-id="35776-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
- <span data-ttu-id="35776-126">Константа <xref:Microsoft.VisualBasic.Constants.vbBack></span><span class="sxs-lookup"><span data-stu-id="35776-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
- <span data-ttu-id="35776-127">Константа <xref:Microsoft.VisualBasic.Constants.vbCr></span><span class="sxs-lookup"><span data-stu-id="35776-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
- <span data-ttu-id="35776-128">Константа <xref:Microsoft.VisualBasic.Constants.vbCrLf></span><span class="sxs-lookup"><span data-stu-id="35776-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
- <span data-ttu-id="35776-129">Константа <xref:Microsoft.VisualBasic.Constants.vbFormFeed></span><span class="sxs-lookup"><span data-stu-id="35776-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
- <span data-ttu-id="35776-130">Константа <xref:Microsoft.VisualBasic.Constants.vbLf></span><span class="sxs-lookup"><span data-stu-id="35776-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
- <span data-ttu-id="35776-131">Константа <xref:Microsoft.VisualBasic.Constants.vbNewLine></span><span class="sxs-lookup"><span data-stu-id="35776-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
- <span data-ttu-id="35776-132">Константа <xref:Microsoft.VisualBasic.Constants.vbNullChar></span><span class="sxs-lookup"><span data-stu-id="35776-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
- <span data-ttu-id="35776-133">Константа <xref:Microsoft.VisualBasic.Constants.vbNullString></span><span class="sxs-lookup"><span data-stu-id="35776-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
- <span data-ttu-id="35776-134">Константа <xref:Microsoft.VisualBasic.Constants.vbTab></span><span class="sxs-lookup"><span data-stu-id="35776-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
- <span data-ttu-id="35776-135">Константа <xref:Microsoft.VisualBasic.Constants.vbVerticalTab></span><span class="sxs-lookup"><span data-stu-id="35776-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
- <span data-ttu-id="35776-136">Некоторые объекты типа `My`</span><span class="sxs-lookup"><span data-stu-id="35776-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="35776-137">Если компиляция выполняется с параметром `-vbruntime*`, а код ссылается на элемент из библиотеки среды выполнения Visual Basic, который не внедрен в основные функции, компилятор возвращает ошибку, указывающую, что элемент недоступен.</span><span class="sxs-lookup"><span data-stu-id="35776-137">If you compile using the `-vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="35776-138">Ссылка на указанную библиотеку</span><span class="sxs-lookup"><span data-stu-id="35776-138">Referencing a specified library</span></span>  
 <span data-ttu-id="35776-139">Аргумент `path` можно использовать для компиляции со ссылкой на пользовательскую библиотеку времени выполнения вместо библиотеки среды выполнения по умолчанию Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="35776-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="35776-140">Если значение аргумента `path` является полным путем к библиотеке DLL, компилятор будет использовать этот файл в качестве библиотеки времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="35776-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="35776-141">Если значение аргумента `path` не является полным путем к DLL, компилятор Visual Basic будет сначала искать определенную библиотеку DLL в текущей папке.</span><span class="sxs-lookup"><span data-stu-id="35776-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="35776-142">Затем он будет искать по пути, указанному с помощью параметра компилятора [-сдкпас](../../../visual-basic/reference/command-line-compiler/sdkpath.md) .</span><span class="sxs-lookup"><span data-stu-id="35776-142">It will then search in the path that you have specified by using the [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="35776-143">Если параметр компилятора `-sdkpath` не используется, компилятор выполнит поиск идентифицированной библиотеки DLL в папке .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="35776-143">If the `-sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="35776-144">Пример</span><span class="sxs-lookup"><span data-stu-id="35776-144">Example</span></span>  
 <span data-ttu-id="35776-145">В следующем примере показано, как использовать параметр `-vbruntime` для компиляции со ссылкой на пользовательскую библиотеку.</span><span class="sxs-lookup"><span data-stu-id="35776-145">The following example shows how to use the `-vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="35776-146">См. также</span><span class="sxs-lookup"><span data-stu-id="35776-146">See also</span></span>

- [<span data-ttu-id="35776-147">Visual Basic Core — новый режим компиляции в Visual Studio 2010 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="35776-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [<span data-ttu-id="35776-148">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="35776-148">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="35776-149">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="35776-149">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="35776-150">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="35776-150">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
