---
title: /platform (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- platform compiler option [Visual Basic]
- /platform compiler option [Visual Basic]
- -platform compiler option [Visual Basic]
ms.assetid: f9bc61e6-e854-4ae1-87b9-d6244de23fd1
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4d52ade26bc249625a77720fe05ad9c1ab58b04f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="platform-visual-basic"></a><span data-ttu-id="8f4bc-102">/platform (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f4bc-102">/platform (Visual Basic)</span></span>
<span data-ttu-id="8f4bc-103">Указывает, на какой версии платформы среды CLR может запускаться выходной файл.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-103">Specifies which platform version of common language runtime (CLR) can run the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f4bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f4bc-104">Syntax</span></span>  
  
```  
/platform:{ x86 | x64 | Itanium | arm | anycpu | anycpu32bitpreferred }  
```  
  
## <a name="arguments"></a><span data-ttu-id="8f4bc-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="8f4bc-105">Arguments</span></span>  
  
|<span data-ttu-id="8f4bc-106">Термин</span><span class="sxs-lookup"><span data-stu-id="8f4bc-106">Term</span></span>|<span data-ttu-id="8f4bc-107">Определение</span><span class="sxs-lookup"><span data-stu-id="8f4bc-107">Definition</span></span>|  
|---|---|  
|`x86`|<span data-ttu-id="8f4bc-108">Компилирует сбору для запуска в 32-разрядной среде CLR с архитектурой x86.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-108">Compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>|  
|`x64`|<span data-ttu-id="8f4bc-109">Компилирует сбору для запуска в 64-разрядной среде CLR на компьютере, поддерживающем набор инструкций AMD64 или EM64T.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-109">Compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>|  
|`Itanium`|<span data-ttu-id="8f4bc-110">Компилирует сбору для запуска в 64-разрядной среде CLR на компьютере с процессором Itanium.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-110">Compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>|  
|`arm`|<span data-ttu-id="8f4bc-111">Компилирует сбору для запуска на компьютере с процессором ARM.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-111">Compiles your assembly to be run on a computer with an ARM (Advanced RISC Machine) processor.</span></span>|  
|`anycpu`|<span data-ttu-id="8f4bc-112">Компилирует сбору для запуска на любой платформе.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-112">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="8f4bc-113">Приложение будет выполняться как 32-разрядное приложение в 32-разрядных версиях Windows и как 64-разрядное приложение в 64-разрядных версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-113">The application will run as a 32-bit application on 32-bit versions of Windows and as a 64-bit application on 64-bit versions of Windows.</span></span> <span data-ttu-id="8f4bc-114">Этот флаг — значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-114">This flag is the default value.</span></span>|  
|`anycpu32bitpreferred`|<span data-ttu-id="8f4bc-115">Компилирует сбору для запуска на любой платформе.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-115">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="8f4bc-116">Приложение будет выполняться как 32-разрядное приложение в 32-разрядных и 64-разрядных версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-116">The application will run as a 32-bit application on both 32-bit and 64-bit versions of Windows.</span></span> <span data-ttu-id="8f4bc-117">Этот флаг действителен только для исполняемых файлов (.EXE), для него требуется [!INCLUDE[net_v45](~/includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f4bc-117">This flag is valid only for executables (.EXE) and requires [!INCLUDE[net_v45](~/includes/net-v45-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f4bc-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="8f4bc-118">Remarks</span></span>  
 <span data-ttu-id="8f4bc-119">Используйте параметр `/platform`, чтобы указать процессор назначения для выходного файла.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-119">Use the `/platform` option to specify the type of processor targeted by the output file.</span></span>  
  
 <span data-ttu-id="8f4bc-120">В целом, сборки .NET Framework, написанные на Visual Basic, будут работать одинаково вне зависимости от платформы.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-120">In general, .NET Framework assemblies written in Visual Basic will run the same regardless of the platform.</span></span> <span data-ttu-id="8f4bc-121">Тем не менее, в некоторых случаях поведение программ на разных платформах может различаться.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-121">However, there are some cases that behave differently on different platforms.</span></span> <span data-ttu-id="8f4bc-122">Вот эти случаи:</span><span class="sxs-lookup"><span data-stu-id="8f4bc-122">These common cases are:</span></span>  
  
-   <span data-ttu-id="8f4bc-123">Структуры, содержащие члены, размер которых изменяется в зависимости от платформы, например, любые типы указателей.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-123">Structures that contain members that change size depending on the platform, such as any pointer type.</span></span>  
  
-   <span data-ttu-id="8f4bc-124">Арифметика указателя, содержащая постоянные размеры.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-124">Pointer arithmetic that includes constant sizes.</span></span>  
  
-   <span data-ttu-id="8f4bc-125">Неверный вызов платформ или объявления СОМ, использующие дескрипторы `Integer` вместо <xref:System.IntPtr>.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-125">Incorrect platform invoke or COM declarations that use `Integer` for handles instead of <xref:System.IntPtr>.</span></span>  
  
-   <span data-ttu-id="8f4bc-126">Приведение <xref:System.IntPtr> к `Integer`.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-126">Casting <xref:System.IntPtr> to `Integer`.</span></span>  
  
-   <span data-ttu-id="8f4bc-127">Использование вызов платформ или взаимодействия СОМ с компонентами, существующими не на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-127">Using platform invoke or COM interop with components that do not exist on all platforms.</span></span>  
  
 <span data-ttu-id="8f4bc-128">**/Platform** позволит устранить некоторые проблемы, если известно, что были внесены предположения об архитектуре, код будет работать на.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-128">The **/platform** option will mitigate some issues if you know you have made assumptions about the architecture your code will run on.</span></span> <span data-ttu-id="8f4bc-129">В частности:</span><span class="sxs-lookup"><span data-stu-id="8f4bc-129">Specifically:</span></span>  
  
-   <span data-ttu-id="8f4bc-130">Если целевой является 64-разрядная платформа, а приложение запущено на 32-разрядном компьютере, сообщение об ошибке появится гораздо раньше и будет более точным, чем сообщение об ошибке, которое появится без этого параметра.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-130">If you decide to target a 64-bit platform, and the application is run on a 32-bit machine, the error message comes much earlier and is more targeted at the problem than the error that occurs without using this switch.</span></span>  
  
-   <span data-ttu-id="8f4bc-131">Если задать флаг `x86` для параметра, а потом запустить приложение на 64-разрядном компьютере, приложение будет запущено в подсистеме WOW, а не непосредственно.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-131">If you set the `x86` flag on the option and the application is subsequently run on a 64-bit machine, the application will run in the WOW subsystem instead of running natively.</span></span>  
  
 <span data-ttu-id="8f4bc-132">В 64-разрядной ОС Windows:</span><span class="sxs-lookup"><span data-stu-id="8f4bc-132">On a 64-bit Windows operating system:</span></span>  
  
-   <span data-ttu-id="8f4bc-133">Сборки, скомпилированные с параметром `/platform:x86`, будут выполняться в 32-разрядной среде CLR с WOW64.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-133">Assemblies compiled with `/platform:x86` will execute on the 32-bit CLR running under WOW64.</span></span>  
  
-   <span data-ttu-id="8f4bc-134">Исполняемые файлы, скомпилированные с параметром `/platform:anycpu`, будут выполняться в 64-разрядной среде CLR.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-134">Executables compiled with the `/platform:anycpu` will execute on the 64-bit CLR.</span></span>  
  
-   <span data-ttu-id="8f4bc-135">Библиотеки DLL, скомпилированные с параметром `/platform:anycpu`, будут выполняться в тоже де среде CLR, что и процесс, загрузивший эти библиотеки.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-135">A DLL compiled with the `/platform:anycpu` will execute on the same CLR as the process into which it loaded.</span></span>  
  
-   <span data-ttu-id="8f4bc-136">Исполняемые файлы, скомпилированные с параметром `/platform:anycpu32bitpreferred`, будут выполняться в 32-разрядной среде CLR.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-136">Executables that are compiled with `/platform:anycpu32bitpreferred` will execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="8f4bc-137">Дополнительные сведения о том, как разрабатывать приложения для запуска в 64-разрядной версии Windows, см. в разделе [64-разрядных приложений](https://msdn.microsoft.com/library/ms241064).</span><span class="sxs-lookup"><span data-stu-id="8f4bc-137">For more information about how to develop an application to run on a 64-bit version of Windows, see [64-bit Applications](https://msdn.microsoft.com/library/ms241064).</span></span>  
  
### <a name="to-set-platform-in-the-visual-studio-ide"></a><span data-ttu-id="8f4bc-138">Чтобы задать параметр /platform в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8f4bc-138">To set /platform in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="8f4bc-139">В **обозревателе решений**, выберите проект, откройте **проекта** меню, а затем нажмите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-139">In **Solution Explorer**, choose the project, open the **Project** menu, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="8f4bc-140">Дополнительные сведения см. в разделе [NIB: управление свойства проекта с помощью конструктора проектов](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span><span class="sxs-lookup"><span data-stu-id="8f4bc-140">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="8f4bc-141">На **компиляции** установите или снимите **предпочитать 32-разрядных** флажок, либо в **целевой Процессор** выберите значение.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-141">On the **Compile** tab, select or clear the **Prefer 32-bit** check box, or, in the **Target CPU** list, choose a value.</span></span>  
  
     <span data-ttu-id="8f4bc-142">Дополнительные сведения см. в разделе [компиляция, конструктора проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="8f4bc-142">For more information, see [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f4bc-143">Пример</span><span class="sxs-lookup"><span data-stu-id="8f4bc-143">Example</span></span>  
 <span data-ttu-id="8f4bc-144">В следующем примере показано использование параметра компилятора `/platform`.</span><span class="sxs-lookup"><span data-stu-id="8f4bc-144">The following example illustrates how to use the `/platform` compiler option.</span></span>  
  
```  
vbc /platform:x86 myFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f4bc-145">См. также</span><span class="sxs-lookup"><span data-stu-id="8f4bc-145">See Also</span></span>  
 [<span data-ttu-id="8f4bc-146">/ Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f4bc-146">/target (Visual Basic)</span></span>](target.md)  
 [<span data-ttu-id="8f4bc-147">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="8f4bc-147">Visual Basic Command-Line Compiler</span></span>](index.md)  
 [<span data-ttu-id="8f4bc-148">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="8f4bc-148">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
