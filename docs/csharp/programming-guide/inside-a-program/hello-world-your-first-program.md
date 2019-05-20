---
title: Руководство по программированию на C#. Создание первой программы Hello World
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 62aaf8785b0dfb646ea804dab6918940f1e33346
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635280"
---
# <a name="hello-world----your-first-program-c-programming-guide"></a><span data-ttu-id="66387-102">Руководство по программированию на C#. Создание первой программы Hello World</span><span class="sxs-lookup"><span data-stu-id="66387-102">Hello World -- Your first program (C# Programming Guide)</span></span>

<span data-ttu-id="66387-103">В следующей процедуре создается версия традиционной программы "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="66387-103">The following procedure creates a C# version of the traditional "Hello World!"</span></span> <span data-ttu-id="66387-104">в C#.</span><span class="sxs-lookup"><span data-stu-id="66387-104">program.</span></span> <span data-ttu-id="66387-105">Программа отображает строку `Hello World!`</span><span class="sxs-lookup"><span data-stu-id="66387-105">The program displays the string `Hello World!`</span></span>

<span data-ttu-id="66387-106">Дополнительные примеры основных понятий см. в разделе [Приступая к работе с Visual C# и Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="66387-106">For more examples of introductory concepts, see [Getting Started with Visual C# and Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-and-run-a-console-application"></a><span data-ttu-id="66387-107">Создание и запуск консольного приложения</span><span class="sxs-lookup"><span data-stu-id="66387-107">To create and run a console application</span></span>

1. <span data-ttu-id="66387-108">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66387-108">Start Visual Studio.</span></span>

2. <span data-ttu-id="66387-109">В строке меню выберите **Файл**, **Создать**, **Проект**.</span><span class="sxs-lookup"><span data-stu-id="66387-109">On the menu bar, choose **File**, **New**, **Project**.</span></span>

     <span data-ttu-id="66387-110">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="66387-110">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="66387-111">Последовательно разверните узлы **Установленные**, **Шаблоны** и **Visual C#**, а затем выберите **Консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="66387-111">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>

4. <span data-ttu-id="66387-112">В текстовом поле **Имя** введите имя проекта и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="66387-112">In the **Name** box, specify a name for your project, and then choose the **OK** button.</span></span>

     <span data-ttu-id="66387-113">В **обозревателе решений** появится новый проект.</span><span class="sxs-lookup"><span data-stu-id="66387-113">The new project appears in **Solution Explorer**.</span></span>

5. <span data-ttu-id="66387-114">Если файл Program.cs не открыт в **редакторе кода**, откройте контекстное меню для **Program.cs** в **обозревателе решений** и нажмите кнопку **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="66387-114">If Program.cs isn't open in the **Code Editor**, open the shortcut menu for **Program.cs** in **Solution Explorer**, and then choose **View Code**.</span></span>

6. <span data-ttu-id="66387-115">Замените содержимое Program.cs кодом из этого примера.</span><span class="sxs-lookup"><span data-stu-id="66387-115">Replace the contents of Program.cs with the following code.</span></span>

     [!code-csharp[csProgGuide#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#21)]

7. <span data-ttu-id="66387-116">Нажмите клавишу F5, чтобы запустить проект.</span><span class="sxs-lookup"><span data-stu-id="66387-116">Choose the F5 key to run the project.</span></span> <span data-ttu-id="66387-117">Откроется окно командной строки, содержащее строку `Hello World!`</span><span class="sxs-lookup"><span data-stu-id="66387-117">A Command Prompt window appears that contains the line `Hello World!`</span></span>

<span data-ttu-id="66387-118">Далее рассматриваются важные части этой программы.</span><span class="sxs-lookup"><span data-stu-id="66387-118">Next, the important parts of this program are examined.</span></span>

## <a name="comments"></a><span data-ttu-id="66387-119">Комментарии</span><span class="sxs-lookup"><span data-stu-id="66387-119">Comments</span></span>

<span data-ttu-id="66387-120">Первая строка содержит комментарий.</span><span class="sxs-lookup"><span data-stu-id="66387-120">The first line contains a comment.</span></span> <span data-ttu-id="66387-121">Символы `//` преобразуют остальную часть строки в комментарий.</span><span class="sxs-lookup"><span data-stu-id="66387-121">The characters `//` convert the rest of the line to a comment.</span></span>

 [!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

<span data-ttu-id="66387-122">Вы можете также закомментировать блок текста, заключив его между символами `/*` и `*/`.</span><span class="sxs-lookup"><span data-stu-id="66387-122">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="66387-123">Эти действия показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="66387-123">This is shown in the following example.</span></span>

 [!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

## <a name="main-method"></a><span data-ttu-id="66387-124">Main - метод</span><span class="sxs-lookup"><span data-stu-id="66387-124">Main method</span></span>

<span data-ttu-id="66387-125">Консольное приложение C# должно содержать метод `Main`, в котором начинается и заканчивается управление.</span><span class="sxs-lookup"><span data-stu-id="66387-125">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="66387-126">В методе `Main` создаются объекты и выполняются другие методы.</span><span class="sxs-lookup"><span data-stu-id="66387-126">The `Main` method is where you create objects and execute other methods.</span></span>

<span data-ttu-id="66387-127">Метод `Main` является [статическим](../../../csharp/language-reference/keywords/static.md) методом, расположенным внутри класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="66387-127">The `Main` method is a [static](../../../csharp/language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="66387-128">В предыдущем примере "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="66387-128">In the previous "Hello World!"</span></span> <span data-ttu-id="66387-129">он размещается в классе с именем `Hello`.</span><span class="sxs-lookup"><span data-stu-id="66387-129">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="66387-130">Вы можете объявить метод `Main` одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="66387-130">You can declare the `Main` method in one of the following ways:</span></span>

- <span data-ttu-id="66387-131">Он может возвращать значение `void`.</span><span class="sxs-lookup"><span data-stu-id="66387-131">It can return `void`.</span></span>

     [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- <span data-ttu-id="66387-132">Он также может возвращать целое число.</span><span class="sxs-lookup"><span data-stu-id="66387-132">It can also return an integer.</span></span>

     [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- <span data-ttu-id="66387-133">С любым из типов возвращаемых значений он может принимать аргументы.</span><span class="sxs-lookup"><span data-stu-id="66387-133">With either of the return types, it can take arguments.</span></span>

     [!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

     <span data-ttu-id="66387-134">- или -</span><span class="sxs-lookup"><span data-stu-id="66387-134">-or-</span></span>

     [!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

<span data-ttu-id="66387-135">Параметр `args` метода `Main` является массивом значений типа `string`, который содержит аргументы командной строки, используемые для вызова программы.</span><span class="sxs-lookup"><span data-stu-id="66387-135">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span> <span data-ttu-id="66387-136">В отличие от C++, массив не содержит имя исполняемого файла (EXE).</span><span class="sxs-lookup"><span data-stu-id="66387-136">Unlike in C++, the array does not include the name of the executable (exe) file.</span></span>

<span data-ttu-id="66387-137">Дополнительные сведения об использовании командной строки см. в примерах в описании [Main() и аргументов командной строки](../../../csharp/programming-guide/main-and-command-args/index.md) и практическом руководстве по [ созданию и использованию сборок с помощью командной строки](../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="66387-137">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) and [How to: Create and Use Assemblies Using the Command Line](../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span></span>

<span data-ttu-id="66387-138">Вызов <xref:System.Console.ReadKey%2A> в конце метода `Main` предотвращает закрытие окна консоли, чтобы вы успели прочитать выходные данные, когда запускаете программу в режиме отладки с помощью клавиши F5.</span><span class="sxs-lookup"><span data-stu-id="66387-138">The call to <xref:System.Console.ReadKey%2A> at the end of the `Main` method prevents the console window from closing before you have a chance to read the output when you run your program in debug mode, by pressing F5.</span></span>

## <a name="input-and-output"></a><span data-ttu-id="66387-139">Ввод и вывод</span><span class="sxs-lookup"><span data-stu-id="66387-139">Input and output</span></span>

<span data-ttu-id="66387-140">Программы на C#, как правило, используют службы ввода-вывода, предоставляемые библиотекой времени выполнения в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="66387-140">C# programs generally use the input/output services provided by the run-time library of the .NET Framework.</span></span> <span data-ttu-id="66387-141">Инструкция `System.Console.WriteLine("Hello World!");` использует метод <xref:System.Console.WriteLine%2A>.</span><span class="sxs-lookup"><span data-stu-id="66387-141">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="66387-142">Это один из методов вывода класса <xref:System.Console> в библиотеке времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="66387-142">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="66387-143">Он отображает свой строковый параметр в стандартном потоке вывода, за которым следует новая строка.</span><span class="sxs-lookup"><span data-stu-id="66387-143">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="66387-144">Существуют и другие методы <xref:System.Console> для разных операций ввода и вывода.</span><span class="sxs-lookup"><span data-stu-id="66387-144">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="66387-145">Если вы добавите в начало программы директиву `using System;`, классы и методы <xref:System> можно использовать напрямую, не указывая их полные имена.</span><span class="sxs-lookup"><span data-stu-id="66387-145">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="66387-146">Например, можно вызвать `Console.WriteLine` вместо `System.Console.WriteLine`:</span><span class="sxs-lookup"><span data-stu-id="66387-146">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>

 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

 [!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="66387-147">Дополнительные сведения о методах ввода-вывода см. в описании <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="66387-147">For more information about input/output methods, see <xref:System.IO>.</span></span>

## <a name="command-line-compilation-and-execution"></a><span data-ttu-id="66387-148">Компиляция и выполнение из командной строки</span><span class="sxs-lookup"><span data-stu-id="66387-148">Command-line compilation and execution</span></span>

<span data-ttu-id="66387-149">Программу "Hello World!" можно скомпилировать,</span><span class="sxs-lookup"><span data-stu-id="66387-149">You can compile the "Hello World!"</span></span> <span data-ttu-id="66387-150">используя командную строку вместо интегрированной среды разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66387-150">program by using the command line instead of the Visual Studio Integrated Development Environment (IDE).</span></span>

### <a name="to-compile-and-run-from-a-command-prompt"></a><span data-ttu-id="66387-151">Компиляция и выполнение программы из командной строки</span><span class="sxs-lookup"><span data-stu-id="66387-151">To compile and run from a command prompt</span></span>

1. <span data-ttu-id="66387-152">Вставьте код из предыдущей процедуры в любой текстовый редактор и сохраните файл как текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="66387-152">Paste the code from the preceding procedure into any text editor, and then save the file as a text file.</span></span> <span data-ttu-id="66387-153">Назовите файл `Hello.cs`.</span><span class="sxs-lookup"><span data-stu-id="66387-153">Name the file `Hello.cs`.</span></span> <span data-ttu-id="66387-154">Для файлов исходного кода C# используется расширение `.cs`.</span><span class="sxs-lookup"><span data-stu-id="66387-154">C# source code files use the extension `.cs`.</span></span>

2. <span data-ttu-id="66387-155">Выполните одно из следующих действий, чтобы открыть окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="66387-155">Perform one of the following steps to open a command-prompt window:</span></span>

    - <span data-ttu-id="66387-156">В меню **Пуск** Windows 10 введите `Developer Command Prompt` в строке поиска, а затем выберите пункт **Командная строка разработчика для VS 2017**.</span><span class="sxs-lookup"><span data-stu-id="66387-156">In Windows 10, on the **Start** menu, search for `Developer Command Prompt`, and then tap or choose **Developer Command Prompt for VS 2017**.</span></span>

         <span data-ttu-id="66387-157">Откроется окно "Командная строка разработчика".</span><span class="sxs-lookup"><span data-stu-id="66387-157">A Developer Command Prompt window appears.</span></span>

    - <span data-ttu-id="66387-158">В Windows 7 откройте меню **Пуск**, разверните папку текущей версии Visual Studio, откройте контекстное меню **Инструменты Visual Studio** и выберите пункт **Командная строка разработчика для VS 2017**.</span><span class="sxs-lookup"><span data-stu-id="66387-158">In Windows 7, open the **Start** menu, expand the folder for the current version of Visual Studio, open the shortcut menu for **Visual Studio Tools**, and then choose **Developer Command Prompt for VS 2017**.</span></span>

         <span data-ttu-id="66387-159">Откроется окно "Командная строка разработчика".</span><span class="sxs-lookup"><span data-stu-id="66387-159">A Developer Command Prompt window appears.</span></span>

    - <span data-ttu-id="66387-160">Включите сборки из командной строки из стандартного окна командной строки.</span><span class="sxs-lookup"><span data-stu-id="66387-160">Enable command-line builds from a standard Command Prompt window.</span></span>

         <span data-ttu-id="66387-161">См. практическое руководство по [ настройке переменных среды для командной строки Visual Studio](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="66387-161">See [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span></span>

3. <span data-ttu-id="66387-162">В окне командной строки перейдите к папке, содержащей файл `Hello.cs`.</span><span class="sxs-lookup"><span data-stu-id="66387-162">In the command-prompt window, navigate to the folder that contains your `Hello.cs` file.</span></span>

4. <span data-ttu-id="66387-163">Введите следующую команду для компиляции `Hello.cs`.</span><span class="sxs-lookup"><span data-stu-id="66387-163">Enter the following command to compile `Hello.cs`.</span></span>

     `csc Hello.cs`

     <span data-ttu-id="66387-164">Если для программы не выдаются ошибки компиляции, создается исполняемый файл с именем `Hello.exe`.</span><span class="sxs-lookup"><span data-stu-id="66387-164">If your program has no compilation errors, an executable file that is named `Hello.exe` is created.</span></span>

5. <span data-ttu-id="66387-165">В окне командной строки введите следующую команду, чтобы запустить программу:</span><span class="sxs-lookup"><span data-stu-id="66387-165">In the command-prompt window, enter the following command to run the program:</span></span>

     `Hello`

 <span data-ttu-id="66387-166">Дополнительные сведения о компиляторе C# и его параметрах см. в разделе [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md).</span><span class="sxs-lookup"><span data-stu-id="66387-166">For more information about the C# compiler and its options, see [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="66387-167">См. также</span><span class="sxs-lookup"><span data-stu-id="66387-167">See also</span></span>

- [<span data-ttu-id="66387-168">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="66387-168">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="66387-169">Структура программы C#</span><span class="sxs-lookup"><span data-stu-id="66387-169">Inside a C# Program</span></span>](../../../csharp/programming-guide/inside-a-program/index.md)
- [<span data-ttu-id="66387-170">Строки</span><span class="sxs-lookup"><span data-stu-id="66387-170">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
- [<span data-ttu-id="66387-171">Примеры и руководства</span><span class="sxs-lookup"><span data-stu-id="66387-171">Samples and tutorials</span></span>](../../../samples-and-tutorials/index.md)
- [<span data-ttu-id="66387-172">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="66387-172">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="66387-173">Main() и аргументы командной строки</span><span class="sxs-lookup"><span data-stu-id="66387-173">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)
- [<span data-ttu-id="66387-174">Начало работы с Visual C# и Visual Basic</span><span class="sxs-lookup"><span data-stu-id="66387-174">Getting Started with Visual C# and Visual Basic</span></span>](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)
