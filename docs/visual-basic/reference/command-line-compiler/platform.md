---
title: -platform
ms.date: 03/13/2018
helpviewer_keywords:
- platform compiler option [Visual Basic]
- /platform compiler option [Visual Basic]
- -platform compiler option [Visual Basic]
ms.assetid: f9bc61e6-e854-4ae1-87b9-d6244de23fd1
ms.openlocfilehash: a6226b73d5d5d4d48a71afe39e8a546019d4c0bc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352348"
---
# <a name="-platform-visual-basic"></a><span data-ttu-id="43f2c-102">-platform (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43f2c-102">-platform (Visual Basic)</span></span>
<span data-ttu-id="43f2c-103">Указывает, на какой версии платформы среды CLR может запускаться выходной файл.</span><span class="sxs-lookup"><span data-stu-id="43f2c-103">Specifies which platform version of common language runtime (CLR) can run the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43f2c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43f2c-104">Syntax</span></span>  
  
```console  
-platform:{ x86 | x64 | Itanium | arm | anycpu | anycpu32bitpreferred }  
```  
  
## <a name="arguments"></a><span data-ttu-id="43f2c-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="43f2c-105">Arguments</span></span>  
  
|<span data-ttu-id="43f2c-106">Термин</span><span class="sxs-lookup"><span data-stu-id="43f2c-106">Term</span></span>|<span data-ttu-id="43f2c-107">Определение</span><span class="sxs-lookup"><span data-stu-id="43f2c-107">Definition</span></span>|  
|---|---|  
|`x86`|<span data-ttu-id="43f2c-108">Компилирует сбору для запуска в 32-разрядной среде CLR с архитектурой x86.</span><span class="sxs-lookup"><span data-stu-id="43f2c-108">Compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>|  
|`x64`|<span data-ttu-id="43f2c-109">Компилирует сбору для запуска в 64-разрядной среде CLR на компьютере, поддерживающем набор инструкций AMD64 или EM64T.</span><span class="sxs-lookup"><span data-stu-id="43f2c-109">Compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>|  
|`Itanium`|<span data-ttu-id="43f2c-110">Компилирует сбору для запуска в 64-разрядной среде CLR на компьютере с процессором Itanium.</span><span class="sxs-lookup"><span data-stu-id="43f2c-110">Compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>|  
|`arm`|<span data-ttu-id="43f2c-111">Компилирует сбору для запуска на компьютере с процессором ARM.</span><span class="sxs-lookup"><span data-stu-id="43f2c-111">Compiles your assembly to be run on a computer with an ARM (Advanced RISC Machine) processor.</span></span>|  
|`anycpu`|<span data-ttu-id="43f2c-112">Компилирует сбору для запуска на любой платформе.</span><span class="sxs-lookup"><span data-stu-id="43f2c-112">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="43f2c-113">Приложение будет выполняться как 32-разрядное приложение в 32-разрядных версиях Windows и как 64-разрядное приложение в 64-разрядных версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="43f2c-113">The application will run as a 32-bit application on 32-bit versions of Windows and as a 64-bit application on 64-bit versions of Windows.</span></span> <span data-ttu-id="43f2c-114">Этот флаг — значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="43f2c-114">This flag is the default value.</span></span>|  
|`anycpu32bitpreferred`|<span data-ttu-id="43f2c-115">Компилирует сбору для запуска на любой платформе.</span><span class="sxs-lookup"><span data-stu-id="43f2c-115">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="43f2c-116">Приложение будет выполняться как 32-разрядное приложение в 32-разрядных и 64-разрядных версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="43f2c-116">The application will run as a 32-bit application on both 32-bit and 64-bit versions of Windows.</span></span> <span data-ttu-id="43f2c-117">This flag is valid only for executables (.EXE) and requires .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="43f2c-117">This flag is valid only for executables (.EXE) and requires .NET Framework 4.5.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43f2c-118">Заметки</span><span class="sxs-lookup"><span data-stu-id="43f2c-118">Remarks</span></span>  
 <span data-ttu-id="43f2c-119">Используйте параметр `-platform`, чтобы указать процессор назначения для выходного файла.</span><span class="sxs-lookup"><span data-stu-id="43f2c-119">Use the `-platform` option to specify the type of processor targeted by the output file.</span></span>  
  
 <span data-ttu-id="43f2c-120">В целом, сборки .NET Framework, написанные на Visual Basic, будут работать одинаково вне зависимости от платформы.</span><span class="sxs-lookup"><span data-stu-id="43f2c-120">In general, .NET Framework assemblies written in Visual Basic will run the same regardless of the platform.</span></span> <span data-ttu-id="43f2c-121">Тем не менее, в некоторых случаях поведение программ на разных платформах может различаться.</span><span class="sxs-lookup"><span data-stu-id="43f2c-121">However, there are some cases that behave differently on different platforms.</span></span> <span data-ttu-id="43f2c-122">Вот эти случаи:</span><span class="sxs-lookup"><span data-stu-id="43f2c-122">These common cases are:</span></span>  
  
- <span data-ttu-id="43f2c-123">Структуры, содержащие члены, размер которых изменяется в зависимости от платформы, например, любые типы указателей.</span><span class="sxs-lookup"><span data-stu-id="43f2c-123">Structures that contain members that change size depending on the platform, such as any pointer type.</span></span>  
  
- <span data-ttu-id="43f2c-124">Арифметика указателя, содержащая постоянные размеры.</span><span class="sxs-lookup"><span data-stu-id="43f2c-124">Pointer arithmetic that includes constant sizes.</span></span>  
  
- <span data-ttu-id="43f2c-125">Неверный вызов платформ или объявления СОМ, использующие дескрипторы `Integer` вместо <xref:System.IntPtr>.</span><span class="sxs-lookup"><span data-stu-id="43f2c-125">Incorrect platform invoke or COM declarations that use `Integer` for handles instead of <xref:System.IntPtr>.</span></span>  
  
- <span data-ttu-id="43f2c-126">Приведение <xref:System.IntPtr> к `Integer`.</span><span class="sxs-lookup"><span data-stu-id="43f2c-126">Casting <xref:System.IntPtr> to `Integer`.</span></span>  
  
- <span data-ttu-id="43f2c-127">Использование вызов платформ или взаимодействия СОМ с компонентами, существующими не на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="43f2c-127">Using platform invoke or COM interop with components that do not exist on all platforms.</span></span>  
  
 <span data-ttu-id="43f2c-128">The **-platform** option will mitigate some issues if you know you have made assumptions about the architecture your code will run on.</span><span class="sxs-lookup"><span data-stu-id="43f2c-128">The **-platform** option will mitigate some issues if you know you have made assumptions about the architecture your code will run on.</span></span> <span data-ttu-id="43f2c-129">В частности:</span><span class="sxs-lookup"><span data-stu-id="43f2c-129">Specifically:</span></span>  
  
- <span data-ttu-id="43f2c-130">Если целевой является 64-разрядная платформа, а приложение запущено на 32-разрядном компьютере, сообщение об ошибке появится гораздо раньше и будет более точным, чем сообщение об ошибке, которое появится без этого параметра.</span><span class="sxs-lookup"><span data-stu-id="43f2c-130">If you decide to target a 64-bit platform, and the application is run on a 32-bit machine, the error message comes much earlier and is more targeted at the problem than the error that occurs without using this switch.</span></span>  
  
- <span data-ttu-id="43f2c-131">Если задать флаг `x86` для параметра, а потом запустить приложение на 64-разрядном компьютере, приложение будет запущено в подсистеме WOW, а не непосредственно.</span><span class="sxs-lookup"><span data-stu-id="43f2c-131">If you set the `x86` flag on the option and the application is subsequently run on a 64-bit machine, the application will run in the WOW subsystem instead of running natively.</span></span>  
  
 <span data-ttu-id="43f2c-132">В 64-разрядной ОС Windows:</span><span class="sxs-lookup"><span data-stu-id="43f2c-132">On a 64-bit Windows operating system:</span></span>  
  
- <span data-ttu-id="43f2c-133">Сборки, скомпилированные с параметром `-platform:x86`, будут выполняться в 32-разрядной среде CLR с WOW64.</span><span class="sxs-lookup"><span data-stu-id="43f2c-133">Assemblies compiled with `-platform:x86` will execute on the 32-bit CLR running under WOW64.</span></span>  
  
- <span data-ttu-id="43f2c-134">Исполняемые файлы, скомпилированные с параметром `-platform:anycpu`, будут выполняться в 64-разрядной среде CLR.</span><span class="sxs-lookup"><span data-stu-id="43f2c-134">Executables compiled with the `-platform:anycpu` will execute on the 64-bit CLR.</span></span>  
  
- <span data-ttu-id="43f2c-135">Библиотеки DLL, скомпилированные с параметром `-platform:anycpu`, будут выполняться в тоже де среде CLR, что и процесс, загрузивший эти библиотеки.</span><span class="sxs-lookup"><span data-stu-id="43f2c-135">A DLL compiled with the `-platform:anycpu` will execute on the same CLR as the process into which it loaded.</span></span>  
  
- <span data-ttu-id="43f2c-136">Исполняемые файлы, скомпилированные с параметром `-platform:anycpu32bitpreferred`, будут выполняться в 32-разрядной среде CLR.</span><span class="sxs-lookup"><span data-stu-id="43f2c-136">Executables that are compiled with `-platform:anycpu32bitpreferred` will execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="43f2c-137">For more information about how to develop an application to run on a 64-bit version of Windows, see [64-bit Applications](../../../framework/64-bit-apps.md).</span><span class="sxs-lookup"><span data-stu-id="43f2c-137">For more information about how to develop an application to run on a 64-bit version of Windows, see [64-bit Applications](../../../framework/64-bit-apps.md).</span></span>  
  
### <a name="to-set--platform-in-the-visual-studio-ide"></a><span data-ttu-id="43f2c-138">To set -platform in the Visual Studio IDE</span><span class="sxs-lookup"><span data-stu-id="43f2c-138">To set -platform in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="43f2c-139">In **Solution Explorer**, choose the project, open the **Project** menu, and then click **Properties**.</span><span class="sxs-lookup"><span data-stu-id="43f2c-139">In **Solution Explorer**, choose the project, open the **Project** menu, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="43f2c-140">On the **Compile** tab, select or clear the **Prefer 32-bit** check box, or, in the **Target CPU** list, choose a value.</span><span class="sxs-lookup"><span data-stu-id="43f2c-140">On the **Compile** tab, select or clear the **Prefer 32-bit** check box, or, in the **Target CPU** list, choose a value.</span></span>  
  
     <span data-ttu-id="43f2c-141">For more information, see [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="43f2c-141">For more information, see [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="example"></a><span data-ttu-id="43f2c-142">Пример</span><span class="sxs-lookup"><span data-stu-id="43f2c-142">Example</span></span>  
 <span data-ttu-id="43f2c-143">В следующем примере показано использование параметра компилятора `-platform`.</span><span class="sxs-lookup"><span data-stu-id="43f2c-143">The following example illustrates how to use the `-platform` compiler option.</span></span>  
  
```console
vbc -platform:x86 myFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="43f2c-144">См. также</span><span class="sxs-lookup"><span data-stu-id="43f2c-144">See also</span></span>

- [<span data-ttu-id="43f2c-145">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43f2c-145">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="43f2c-146">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="43f2c-146">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="43f2c-147">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="43f2c-147">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
