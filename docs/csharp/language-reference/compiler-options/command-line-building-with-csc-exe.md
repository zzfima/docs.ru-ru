---
title: "Построение из командной строки с помощью csc.exe"
ms.date: 2017-04-19
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- builds [C#]
- command line [C#]
ms.assetid: 66e70056-dd20-453c-a9b3-507e0478b015
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: dd47544e11222dfb0035f37196abcdf5654d5537
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="command-line-build-with-cscexe"></a><span data-ttu-id="43756-102">Построение из командной строки с помощью csc.exe</span><span class="sxs-lookup"><span data-stu-id="43756-102">Command-line build with csc.exe</span></span>
<span data-ttu-id="43756-103">Чтобы вызвать компилятор C#, следует ввести имя соответствующего исполняемого файла (*csc.exe*) в командной строке.</span><span class="sxs-lookup"><span data-stu-id="43756-103">You can invoke the C# compiler by typing the name of its executable file (*csc.exe*) at a command prompt.</span></span>

<span data-ttu-id="43756-104">Если используется окно **Командная строка разработчика для Visual Studio**, все необходимые переменные среды устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="43756-104">If you use the **Developer Command Prompt for Visual Studio** window, all the necessary environment variables are set for you.</span></span> <span data-ttu-id="43756-105">Дополнительные сведения о получении доступа к этому инструменту см. в статье [Командная строка разработчика для Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="43756-105">For information on how to access this tool, see the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md) topic.</span></span> 

<span data-ttu-id="43756-106">Если используется стандартное окно командной строки, необходимо изменить путь к файлу *csc.exe*, прежде чем вызывать его из любого подкаталога на компьютере.</span><span class="sxs-lookup"><span data-stu-id="43756-106">If you use a standard Command Prompt window, you must adjust your path before you can invoke *csc.exe* from any subdirectory on your computer.</span></span> <span data-ttu-id="43756-107">Чтобы задать соответствующие переменные среды для поддержки построения из командной строки, необходимо запустить пакетный файл *vsvars32.bat*.</span><span class="sxs-lookup"><span data-stu-id="43756-107">You also must run *vsvars32.bat* to set the appropriate environment variables to support command-line builds.</span></span> <span data-ttu-id="43756-108">Дополнительные сведения о файле *vsvars32.bat*, включая инструкции по его поиску и запуску, см. в разделе [Практическое руководство. Настройка переменных среды для командной строки Visual Studio](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="43756-108">For more information about *vsvars32.bat*, including instructions for how to find and run it, see [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span></span>

<span data-ttu-id="43756-109">Если на вашем компьютере установлен только пакет [!INCLUDE[winsdklong](~/includes/winsdklong-md.md)], компилятор C# можно использовать из **командной строки SDK**, которая открывается через пункт меню **Microsoft .NET Framework SDK**.</span><span class="sxs-lookup"><span data-stu-id="43756-109">If you're working on a computer that has only the [!INCLUDE[winsdklong](~/includes/winsdklong-md.md)], you can use the C# compiler at the **SDK Command Prompt**, which you open from the **Microsoft .NET Framework SDK** menu option.</span></span>

<span data-ttu-id="43756-110">Для программного построения программ C# можно также использовать средство MSBuild.</span><span class="sxs-lookup"><span data-stu-id="43756-110">You can also use MSBuild to build C# programs programmatically.</span></span> <span data-ttu-id="43756-111">Дополнительные сведения см. в разделе [MSBuild](/visualstudio/msbuild/msbuild).</span><span class="sxs-lookup"><span data-stu-id="43756-111">For more information, see [MSBuild](/visualstudio/msbuild/msbuild).</span></span>

<span data-ttu-id="43756-112">Обычно исполняемый файл *csc.exe* расположен в папке Microsoft.NET\Framework\\*\<версия>* в каталоге *Windows*.</span><span class="sxs-lookup"><span data-stu-id="43756-112">The *csc.exe* executable file usually is located in the Microsoft.NET\Framework\\*\<Version>* folder under the *Windows* directory.</span></span> <span data-ttu-id="43756-113">Расположение файла может зависеть от конкретной конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="43756-113">Its location might vary depending on the exact configuration of a particular computer.</span></span> <span data-ttu-id="43756-114">Если на компьютере установлено несколько версий .NET Framework, будет несколько версий этого файла.</span><span class="sxs-lookup"><span data-stu-id="43756-114">If more than one version of the .NET Framework is installed on your computer, you'll find multiple versions of this file.</span></span> <span data-ttu-id="43756-115">Дополнительные сведения о подобных вариантах установки см. в разделе [Практическое руководство. Определение установленных версий платформы .NET Framework](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="43756-115">For more information about such installations, see [How to: determine which versions of the .NET Framework are installed](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>

> [!TIP]
>  <span data-ttu-id="43756-116">При сборке проекта в интегрированной среде разработки Visual Studio можно открыть команду **csc** и связанные с ней параметры компилятора в окне **Вывод**.</span><span class="sxs-lookup"><span data-stu-id="43756-116">When you build a project by using the Visual Studio IDE, you can display the **csc** command and its associated compiler options in the **Output** window.</span></span> <span data-ttu-id="43756-117">Чтобы отобразить эту информацию, следуйте инструкциям в разделе [Практическое руководство. Просмотр, сохранение и настройка файлов журнала сборки](/visualstudio/ide/how-to-view-save-and-configure-build-log-files#to-change-the-amount-of-information-included-in-the-build-log) для изменения уровня детализации журнала на **Обычный** или **Подробный**.</span><span class="sxs-lookup"><span data-stu-id="43756-117">To display this information, follow the instructions in [How to: View, Save, and Configure Build Log Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files#to-change-the-amount-of-information-included-in-the-build-log) to change the verbosity level of the log data to **Normal** or **Detailed**.</span></span> <span data-ttu-id="43756-118">После сборки проекта выполните поиск по слову **csc** в окне **Вывод**, чтобы найти информацию о запуске компилятора C#.</span><span class="sxs-lookup"><span data-stu-id="43756-118">After you rebuild your project, search the **Output** window for **csc** to find the invocation of the C# compiler.</span></span>

 <span data-ttu-id="43756-119">**Содержание раздела**</span><span class="sxs-lookup"><span data-stu-id="43756-119">**In this topic**</span></span>

- [<span data-ttu-id="43756-120">Правила синтаксиса командной строки компоновщика</span><span class="sxs-lookup"><span data-stu-id="43756-120">Rules for command-line syntax</span></span>](#-rules-for-command-line-syntax-for-the-c-compiler)

- [<span data-ttu-id="43756-121">Примеры командных строк</span><span class="sxs-lookup"><span data-stu-id="43756-121">Sample command lines</span></span>](#sample-command-lines-for-the-c-compiler)

- [<span data-ttu-id="43756-122">Различия между выходными данными компилятора C# и компилятора C++</span><span class="sxs-lookup"><span data-stu-id="43756-122">Differences between C# compiler and C++ compiler output</span></span>](#differences-between-c-compiler-and-c-compiler-output)

## <a name="rules-for-command-line-syntax-for-the-c-compiler"></a><span data-ttu-id="43756-123">Правила синтаксиса командной строки для компилятора C#</span><span class="sxs-lookup"><span data-stu-id="43756-123">Rules for command-line syntax for the C# compiler</span></span>

<span data-ttu-id="43756-124">Компилятор C# использует следующие правила при обработке аргументов, вводимых в командной строке операционной системы.</span><span class="sxs-lookup"><span data-stu-id="43756-124">The C# compiler uses the following rules when it interprets arguments given on the operating system command line:</span></span>

- <span data-ttu-id="43756-125">Аргументы разделяются пробелами (пробел или табуляция).</span><span class="sxs-lookup"><span data-stu-id="43756-125">Arguments are delimited by white space, which is either a space or a tab.</span></span>

- <span data-ttu-id="43756-126">Символ каретки (^) не воспринимается как escape-символ или разделитель.</span><span class="sxs-lookup"><span data-stu-id="43756-126">The caret character (^) is not recognized as an escape character or delimiter.</span></span> <span data-ttu-id="43756-127">Этот символ обрабатывается синтаксическим анализатором командной строки в операционной системе, прежде чем передается в массив `argv` программы.</span><span class="sxs-lookup"><span data-stu-id="43756-127">The character is handled by the command-line parser in the operating system before it's passed to the `argv` array in the program.</span></span>

- <span data-ttu-id="43756-128">Строка, заключенная в двойные прямые кавычки ("строка"), обрабатывается как один аргумент, независимо от пробельных символов, которые могут в ней присутствовать.</span><span class="sxs-lookup"><span data-stu-id="43756-128">A string enclosed in double quotation marks ("string") is interpreted as a single argument, regardless of white space that is contained within.</span></span> <span data-ttu-id="43756-129">Строку в кавычках можно встроить в аргумент.</span><span class="sxs-lookup"><span data-stu-id="43756-129">A quoted string can be embedded in an argument.</span></span>

- <span data-ttu-id="43756-130">Символ двойной кавычки после обратной косой черты (\\") обрабатывается как символ двойной кавычки литерала (").</span><span class="sxs-lookup"><span data-stu-id="43756-130">A double quotation mark preceded by a backslash (\\") is interpreted as a literal double quotation mark character (").</span></span>

- <span data-ttu-id="43756-131">Символы обратной косой черты обрабатываются буквально, если только им не предшествует двойная кавычка.</span><span class="sxs-lookup"><span data-stu-id="43756-131">Backslashes are interpreted literally, unless they immediately precede a double quotation mark.</span></span>

- <span data-ttu-id="43756-132">Если после четного числа символов обратной косой черты стоит двойная кавычка, в массив `argv` помещается по одному символу обратной косой черты (\) для каждой пары символов обратной косой черты (\\), а двойная кавычка (") обрабатывается как разделитель строки.</span><span class="sxs-lookup"><span data-stu-id="43756-132">If an even number of backslashes is followed by a double quotation mark, one backslash is put in the `argv` array for every pair of backslashes, and the double quotation mark is interpreted as a string delimiter.</span></span>

- <span data-ttu-id="43756-133">Если после нечетного числа символов обратной косой черты стоит двойная кавычка, в массив `argv` помещается по одному символу обратной косой черты (\) для каждой пары символов обратной косой черты (\\), а двойная кавычка (") "изолируется" с помощью оставшихся косых черт.</span><span class="sxs-lookup"><span data-stu-id="43756-133">If an odd number of backslashes is followed by a double quotation mark, one backslash is put in the `argv` array for every pair of backslashes, and the double quotation mark is "escaped" by the remaining backslash.</span></span> <span data-ttu-id="43756-134">В результате литеральный символ двойной кавычки (") добавляется в массив `argv`.</span><span class="sxs-lookup"><span data-stu-id="43756-134">This causes a literal double quotation mark (") to be added in `argv`.</span></span>

## <a name="sample-command-lines-for-the-c-compiler"></a><span data-ttu-id="43756-135">Примеры командных строк для компилятора C#</span><span class="sxs-lookup"><span data-stu-id="43756-135">Sample command lines for the C# compiler</span></span>

- <span data-ttu-id="43756-136">Компиляция *File.cs* и создание *File.exe*:</span><span class="sxs-lookup"><span data-stu-id="43756-136">Compiles *File.cs* producing *File.exe*:</span></span>

```console
csc File.cs 
```

- <span data-ttu-id="43756-137">Компиляция *File.cs* и создание *File.dll*:</span><span class="sxs-lookup"><span data-stu-id="43756-137">Compiles *File.cs* producing *File.dll*:</span></span>

```console
csc /target:library File.cs
```

- <span data-ttu-id="43756-138">Компиляция *File.cs* и создание *My.exe*:</span><span class="sxs-lookup"><span data-stu-id="43756-138">Compiles *File.cs* and creates *My.exe*:</span></span>

```console
csc /out:My.exe File.cs
```

- <span data-ttu-id="43756-139">Компиляция всех файлов C# в текущем каталоге с включенными оптимизациями и определение символа DEBUG.</span><span class="sxs-lookup"><span data-stu-id="43756-139">Compiles all the C# files in the current directory with optimizations enabled and defines the DEBUG symbol.</span></span> <span data-ttu-id="43756-140">Выводится файл *File2.exe*:</span><span class="sxs-lookup"><span data-stu-id="43756-140">The output is *File2.exe*:</span></span>

```console
csc /define:DEBUG /optimize /out:File2.exe *.cs
```

- <span data-ttu-id="43756-141">Компиляция всех файлов C# в текущем каталоге с созданием отладочной версии *File2.dll*.</span><span class="sxs-lookup"><span data-stu-id="43756-141">Compiles all the C# files in the current directory producing a debug version of *File2.dll*.</span></span> <span data-ttu-id="43756-142">Логотипы и предупреждения не отображаются:</span><span class="sxs-lookup"><span data-stu-id="43756-142">No logo and no warnings are displayed:</span></span>

```console
csc /target:library /out:File2.dll /warn:0 /nologo /debug *.cs
```

- <span data-ttu-id="43756-143">Компиляция всех файлов C# в текущем каталоге в файл *Something.xyz* (библиотеку DLL):</span><span class="sxs-lookup"><span data-stu-id="43756-143">Compiles all the C# files in the current directory to *Something.xyz* (a DLL):</span></span>

```console
csc /target:library /out:Something.xyz *.cs
```

## <a name="differences-between-c-compiler-and-c-compiler-output"></a><span data-ttu-id="43756-144">Различия между выходными данными компилятора C# и компилятора C++</span><span class="sxs-lookup"><span data-stu-id="43756-144">Differences between C# compiler and C++ compiler output</span></span>
<span data-ttu-id="43756-145">В результате вызова компилятора C# файлы объектов (*OBJ*-файлы) не создаются; выходные файлы создаются непосредственно.</span><span class="sxs-lookup"><span data-stu-id="43756-145">There are no object (*.obj*) files created as a result of invoking the C# compiler; output files are created directly.</span></span> <span data-ttu-id="43756-146">По этой причине компилятору C# не требуется компоновщик.</span><span class="sxs-lookup"><span data-stu-id="43756-146">As a result of this, the C# compiler does not need a linker.</span></span>

## <a name="see-also"></a><span data-ttu-id="43756-147">См. также</span><span class="sxs-lookup"><span data-stu-id="43756-147">See also</span></span>
 <span data-ttu-id="43756-148">[Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="43756-148">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 <span data-ttu-id="43756-149">[Параметры компилятора C# в алфавитном порядке](../../../csharp/language-reference/compiler-options/listed-alphabetically.md) </span><span class="sxs-lookup"><span data-stu-id="43756-149">[C# Compiler Options Listed Alphabetically](../../../csharp/language-reference/compiler-options/listed-alphabetically.md) </span></span>  
 <span data-ttu-id="43756-150">[Параметры компилятора C#, упорядоченные по категориям](../../../csharp/language-reference/compiler-options/listed-by-category.md) </span><span class="sxs-lookup"><span data-stu-id="43756-150">[C# Compiler Options Listed by Category](../../../csharp/language-reference/compiler-options/listed-by-category.md) </span></span>  
 <span data-ttu-id="43756-151">[Main() и аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/index.md) </span><span class="sxs-lookup"><span data-stu-id="43756-151">[Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) </span></span>  
 <span data-ttu-id="43756-152">[Аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="43756-152">[Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md) </span></span>  
 <span data-ttu-id="43756-153">[Практическое руководство. Отображение аргументов командной строки](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="43756-153">[How to: Display Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md) </span></span>  
 <span data-ttu-id="43756-154">[Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md) </span><span class="sxs-lookup"><span data-stu-id="43756-154">[How to: Access Command-Line Arguments Using foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md) </span></span>  
 [<span data-ttu-id="43756-155">Значения, возвращаемые методом main()</span><span class="sxs-lookup"><span data-stu-id="43756-155">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)

