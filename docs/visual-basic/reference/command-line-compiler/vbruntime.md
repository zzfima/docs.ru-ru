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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e83a85e29eb4447f8d3b9dddc4f6ccdbc771b23c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515620"
---
# <a name="-vbruntime"></a><span data-ttu-id="81bee-102">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="81bee-102">-vbruntime</span></span>
<span data-ttu-id="81bee-103">Указывает, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic или со ссылкой на конкретную библиотеку времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="81bee-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81bee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81bee-104">Syntax</span></span>  
  
```  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="81bee-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="81bee-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="81bee-106">Выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="81bee-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="81bee-107">Скомпилируйте со ссылкой на библиотеку времени выполнения Visual Basic по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="81bee-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="81bee-108">Выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic и внедрения основных функциональных возможностей библиотеки времени выполнения Visual Basic в сборку.</span><span class="sxs-lookup"><span data-stu-id="81bee-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="81bee-109">Скомпилируйте со ссылкой на указанную библиотеку (DLL).</span><span class="sxs-lookup"><span data-stu-id="81bee-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81bee-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="81bee-110">Remarks</span></span>  
 <span data-ttu-id="81bee-111">`-vbruntime` Параметр компилятора позволяет указать, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="81bee-111">The `-vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="81bee-112">Если компиляция выполняется без ссылки на библиотеку времени выполнения Visual Basic, ошибки или предупреждения регистрируются на код или языковой конструкции, которые создает вызов вспомогательный класс среды выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="81bee-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="81bee-113">(Объект *вспомогательное средство среды выполнения Visual Basic* — это функция, определенная в Microsoft.VisualBasic.dll, которая вызывается во время выполнения для выполнения конкретного семантического языка.)</span><span class="sxs-lookup"><span data-stu-id="81bee-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="81bee-114">`-vbruntime+` Параметр определяет такое же поведение, возникающее, если не `-vbruntime` указан ключ.</span><span class="sxs-lookup"><span data-stu-id="81bee-114">The `-vbruntime+` option produces the same behavior that occurs if no `-vbruntime` switch is specified.</span></span> <span data-ttu-id="81bee-115">Можно использовать `-vbruntime+` переопределить предыдущий `-vbruntime` коммутаторов.</span><span class="sxs-lookup"><span data-stu-id="81bee-115">You can use the `-vbruntime+` option to override previous `-vbruntime` switches.</span></span>  
  
 <span data-ttu-id="81bee-116">Наибольшее число объектов `My` типа будут недоступны при использовании `-vbruntime-` или `-vbruntime:path` параметры.</span><span class="sxs-lookup"><span data-stu-id="81bee-116">Most objects of the `My` type are unavailable when you use the `-vbruntime-` or `-vbruntime:path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="81bee-117">Внедрение основные функциональные возможности среды выполнения Visual Basic</span><span class="sxs-lookup"><span data-stu-id="81bee-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="81bee-118">`-vbruntime*` Вариант позволяет выполнять компиляцию без ссылки на библиотеку времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="81bee-118">The `-vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="81bee-119">Вместо этого основных функциональных возможностей библиотеки времени выполнения Visual Basic внедренных в сборку пользователя.</span><span class="sxs-lookup"><span data-stu-id="81bee-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="81bee-120">Этот параметр можно использовать, если приложение выполняется на платформах, не содержащих среда выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="81bee-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="81bee-121">Внедряются следующие компоненты времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="81bee-121">The following runtime members are embedded:</span></span>  
  
-   <span data-ttu-id="81bee-122">Класс <xref:Microsoft.VisualBasic.CompilerServices.Conversions></span><span class="sxs-lookup"><span data-stu-id="81bee-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
-   <span data-ttu-id="81bee-123">Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29></span><span class="sxs-lookup"><span data-stu-id="81bee-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
-   <span data-ttu-id="81bee-124">Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="81bee-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
-   <span data-ttu-id="81bee-125">Метод <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29></span><span class="sxs-lookup"><span data-stu-id="81bee-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
-   <span data-ttu-id="81bee-126"><xref:Microsoft.VisualBasic.Constants.vbBack> Константы</span><span class="sxs-lookup"><span data-stu-id="81bee-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
-   <span data-ttu-id="81bee-127"><xref:Microsoft.VisualBasic.Constants.vbCr> Константы</span><span class="sxs-lookup"><span data-stu-id="81bee-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
-   <span data-ttu-id="81bee-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> Константы</span><span class="sxs-lookup"><span data-stu-id="81bee-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
-   <span data-ttu-id="81bee-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> Константы</span><span class="sxs-lookup"><span data-stu-id="81bee-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
-   <span data-ttu-id="81bee-130"><xref:Microsoft.VisualBasic.Constants.vbLf> Константы</span><span class="sxs-lookup"><span data-stu-id="81bee-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
-   <span data-ttu-id="81bee-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> Константы</span><span class="sxs-lookup"><span data-stu-id="81bee-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
-   <span data-ttu-id="81bee-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> Константы</span><span class="sxs-lookup"><span data-stu-id="81bee-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
-   <span data-ttu-id="81bee-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> Константы</span><span class="sxs-lookup"><span data-stu-id="81bee-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
-   <span data-ttu-id="81bee-134"><xref:Microsoft.VisualBasic.Constants.vbTab> Константы</span><span class="sxs-lookup"><span data-stu-id="81bee-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
-   <span data-ttu-id="81bee-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> Константы</span><span class="sxs-lookup"><span data-stu-id="81bee-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
-   <span data-ttu-id="81bee-136">Некоторые объекты из `My` типа</span><span class="sxs-lookup"><span data-stu-id="81bee-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="81bee-137">Если компиляция выполняется с помощью `-vbruntime*` параметр и код ссылается на элемент из библиотеки среды выполнения Visual Basic не внедряется с основные функциональные возможности, компилятор возвращает ошибку, указывающую, что член недоступен.</span><span class="sxs-lookup"><span data-stu-id="81bee-137">If you compile using the `-vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="81bee-138">Ссылки на указанную библиотеку</span><span class="sxs-lookup"><span data-stu-id="81bee-138">Referencing a specified library</span></span>  
 <span data-ttu-id="81bee-139">Можно использовать `path` аргумент для компиляции со ссылкой на библиотеку настраиваемую среду выполнения вместо библиотеки времени выполнения Visual Basic по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="81bee-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="81bee-140">Если значение `path` равно полный путь к DLL, компилятор будет использовать этот файл как на библиотеку времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="81bee-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="81bee-141">Если значение `path` аргумент не является полный путь к DLL, компилятор Visual Basic будет сначала искать указанный DLL в текущей папке.</span><span class="sxs-lookup"><span data-stu-id="81bee-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="81bee-142">Затем будет выполнен поиск по пути, который указан с помощью [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="81bee-142">It will then search in the path that you have specified by using the [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="81bee-143">Если `-sdkpath` не используется параметр компилятора, компилятор будет искать идентифицированной библиотеки DLL в папке .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span><span class="sxs-lookup"><span data-stu-id="81bee-143">If the `-sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="81bee-144">Пример</span><span class="sxs-lookup"><span data-stu-id="81bee-144">Example</span></span>  
 <span data-ttu-id="81bee-145">В следующем примере показано, как использовать `-vbruntime` для компиляции со ссылкой на пользовательской библиотеки.</span><span class="sxs-lookup"><span data-stu-id="81bee-145">The following example shows how to use the `-vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="81bee-146">См. также</span><span class="sxs-lookup"><span data-stu-id="81bee-146">See Also</span></span>  
 [<span data-ttu-id="81bee-147">Core в Visual Basic — новый режим компиляции в Visual Studio 2010 с пакетом обновления 1</span><span class="sxs-lookup"><span data-stu-id="81bee-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](https://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)  
 [<span data-ttu-id="81bee-148">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="81bee-148">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="81bee-149">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="81bee-149">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="81bee-150">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="81bee-150">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
