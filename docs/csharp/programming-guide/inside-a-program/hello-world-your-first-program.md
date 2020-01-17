---
title: Руководство по программированию на C#. Создание первой программы Hello World с помощью Visual Studio в Windows или Mac
ms.date: 09/12/2019
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 910fa4af1b4e45ce627b589a06910dc168490047
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712147"
---
# <a name="hello-world----your-first-program"></a><span data-ttu-id="6cc25-102">Hello World — создаем первую программу</span><span class="sxs-lookup"><span data-stu-id="6cc25-102">Hello World -- Your first program</span></span>

<span data-ttu-id="6cc25-103">В этой статье вы будете использовать Visual Studio для создания традиционной программы "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="6cc25-103">In this article, you'll use Visual Studio to create the traditional "Hello World!"</span></span> <span data-ttu-id="6cc25-104">в C#.</span><span class="sxs-lookup"><span data-stu-id="6cc25-104">program.</span></span> <span data-ttu-id="6cc25-105">Visual Studio — это профессиональная интегрированная среда разработки (IDE) с множеством функций, предназначенных для разработки в среде .NET.</span><span class="sxs-lookup"><span data-stu-id="6cc25-105">Visual Studio is a professional Integrated Development Environment (IDE) with many features designed for .NET development.</span></span> <span data-ttu-id="6cc25-106">Для создания этой программы вы будете использовать лишь некоторые функции Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6cc25-106">You'll use only a few of the features in Visual Studio to create this program.</span></span> <span data-ttu-id="6cc25-107">См. дополнительные сведения о [начале работы с Visual C#](/visualstudio/ide/quickstart-csharp-console).</span><span class="sxs-lookup"><span data-stu-id="6cc25-107">To learn more about Visual Studio, see [Getting Started with Visual C#](/visualstudio/ide/quickstart-csharp-console).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="create-a-new-application"></a><span data-ttu-id="6cc25-108">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="6cc25-108">Create a new application</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[<span data-ttu-id="6cc25-109">Windows</span><span class="sxs-lookup"><span data-stu-id="6cc25-109">Windows</span></span>](#tab/windows)

<span data-ttu-id="6cc25-110">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6cc25-110">Start Visual Studio.</span></span> <span data-ttu-id="6cc25-111">В Windows вы увидите следующее изображение:</span><span class="sxs-lookup"><span data-stu-id="6cc25-111">You'll see the following image on Windows:</span></span>

![Экран приветствия Visual Studio в Windows](./media/hello-world-your-first-program/visual-studio-windows-start-screen.png)

<span data-ttu-id="6cc25-113">Выберите **Создать проект** в правом нижнем углу изображения.</span><span class="sxs-lookup"><span data-stu-id="6cc25-113">Select **Create a new project** in the lower right corner of the image.</span></span> <span data-ttu-id="6cc25-114">В Visual Studio отображается диалоговое окно **Новый проект**:</span><span class="sxs-lookup"><span data-stu-id="6cc25-114">Visual Studio displays the **New Project** dialog:</span></span>

![Экран нового проекта Visual Studio в Windows](./media/hello-world-your-first-program/visual-studio-windows-new-project.png)

> [!NOTE]
> <span data-ttu-id="6cc25-116">Если вы запустили Visual Studio впервые, список **Последние шаблоны проектов** будет пустым.</span><span class="sxs-lookup"><span data-stu-id="6cc25-116">If this is the first time you've started Visual Studio, the **Recent project templates** list is empty.</span></span>

<span data-ttu-id="6cc25-117">В диалоговом окне "Новый проект" выберите "Консольное приложение (.NET Core)" и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6cc25-117">On the new project dialog, choose "Console App (.NET Core)" and then press **Next**.</span></span> <span data-ttu-id="6cc25-118">Присвойте проекту имя, например "HelloWorld", а затем нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="6cc25-118">Give your project a name, such as "HelloWorld", then press **Create**.</span></span>

<span data-ttu-id="6cc25-119">Проект открывается в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6cc25-119">Visual Studio opens your project.</span></span> <span data-ttu-id="6cc25-120">Он уже является базовым примером</span><span class="sxs-lookup"><span data-stu-id="6cc25-120">It's already a basic "Hello World!"</span></span> <span data-ttu-id="6cc25-121">Hello, World!</span><span class="sxs-lookup"><span data-stu-id="6cc25-121">example.</span></span> <span data-ttu-id="6cc25-122">Нажмите клавиши `Ctrl` + `F5` для запуска проекта.</span><span class="sxs-lookup"><span data-stu-id="6cc25-122">Press `Ctrl` + `F5` to run your project.</span></span> <span data-ttu-id="6cc25-123">Visual Studio выполняет сборку проекта, преобразуя исходный код в исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="6cc25-123">Visual Studio builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="6cc25-124">Затем запускается командное окно, запускающее новое приложение.</span><span class="sxs-lookup"><span data-stu-id="6cc25-124">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="6cc25-125">В окне должен отображаться следующий текст:</span><span class="sxs-lookup"><span data-stu-id="6cc25-125">You should see the following text in the window:</span></span>

```console
Hello World!

C:\Program Files\dotnet\dotnet.exe (process 11964) exited with code 0.
Press any key to close this window . . .
```

<span data-ttu-id="6cc25-126">Нажмите любую клавишу, чтобы закрыть окно.</span><span class="sxs-lookup"><span data-stu-id="6cc25-126">Press a key to close the window.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="6cc25-127">macOS</span><span class="sxs-lookup"><span data-stu-id="6cc25-127">macOS</span></span>](#tab/macos)

<span data-ttu-id="6cc25-128">Запустите Visual Studio для Mac.</span><span class="sxs-lookup"><span data-stu-id="6cc25-128">Start Visual Studio for Mac.</span></span> <span data-ttu-id="6cc25-129">В Mac вы увидите следующее изображение:</span><span class="sxs-lookup"><span data-stu-id="6cc25-129">You'll see the following image on Mac:</span></span>

![Экран приветствия Visual Studio в Mac](./media/hello-world-your-first-program/visual-studio-mac-start-screen.png)

> [!NOTE]
> <span data-ttu-id="6cc25-131">Если вы запустили Visual Studio для Mac впервые, список **Последние проекты** будет пустым.</span><span class="sxs-lookup"><span data-stu-id="6cc25-131">If this is the first time you've started Visual Studio for Mac, the **Recent projects** list is empty.</span></span>

<span data-ttu-id="6cc25-132">Выберите **Создать** в правом верхнем углу изображения.</span><span class="sxs-lookup"><span data-stu-id="6cc25-132">Select **New** in the upper right corner of the image.</span></span> <span data-ttu-id="6cc25-133">В Visual Studio для Mac отображается диалоговое окно **Новый проект**:</span><span class="sxs-lookup"><span data-stu-id="6cc25-133">Visual Studio for Mac displays the **New Project** dialog:</span></span>

![Экран нового проекта Visual Studio в Mac](./media/hello-world-your-first-program/visual-studio-mac-new-project.png)

<span data-ttu-id="6cc25-135">В диалоговом окне "Новый проект" выберите ".NET Core" и "Консольное приложение" и затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6cc25-135">On the new project dialog, choose ".NET Core", and "Console App" and then press **Next**.</span></span> <span data-ttu-id="6cc25-136">Вам потребуется выбрать целевую платформу.</span><span class="sxs-lookup"><span data-stu-id="6cc25-136">You'll need to select the target framework.</span></span> <span data-ttu-id="6cc25-137">Значение по умолчанию подходит, поэтому нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="6cc25-137">The default is fine, so press next.</span></span> <span data-ttu-id="6cc25-138">Присвойте проекту имя, например "HelloWorld", а затем нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="6cc25-138">Give your project a name, such as "HelloWorld", then press **Create**.</span></span> <span data-ttu-id="6cc25-139">Вы можете использовать расположение проекта по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6cc25-139">You can use the default project location.</span></span> <span data-ttu-id="6cc25-140">Не добавляйте этот проект в систему управления версиями.</span><span class="sxs-lookup"><span data-stu-id="6cc25-140">Don't add this project to source control.</span></span>

<span data-ttu-id="6cc25-141">Проект открывается в Visual Studio для Mac.</span><span class="sxs-lookup"><span data-stu-id="6cc25-141">Visual Studio for Mac opens your project.</span></span> <span data-ttu-id="6cc25-142">Он уже является базовым примером</span><span class="sxs-lookup"><span data-stu-id="6cc25-142">It's already a basic "Hello World!"</span></span> <span data-ttu-id="6cc25-143">Hello, World!</span><span class="sxs-lookup"><span data-stu-id="6cc25-143">example.</span></span> <span data-ttu-id="6cc25-144">Нажмите клавиши `Ctrl` + `Fn` + `F5` для запуска проекта.</span><span class="sxs-lookup"><span data-stu-id="6cc25-144">Press `Ctrl` + `Fn` + `F5` to run your project.</span></span> <span data-ttu-id="6cc25-145">Visual Studio для Mac выполняет сборку проекта, преобразуя исходный код в исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="6cc25-145">Visual Studio for Mac builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="6cc25-146">Затем запускается командное окно, запускающее новое приложение.</span><span class="sxs-lookup"><span data-stu-id="6cc25-146">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="6cc25-147">В окне должен отображаться следующий текст:</span><span class="sxs-lookup"><span data-stu-id="6cc25-147">You should see the following text in the window:</span></span>

```console
Hello World!

Press any key to close this window . . .
```

<span data-ttu-id="6cc25-148">Нажмите клавишу, чтобы завершить сеанс.</span><span class="sxs-lookup"><span data-stu-id="6cc25-148">Press a key to end the session.</span></span>

---

## <a name="elements-of-a-c-program"></a><span data-ttu-id="6cc25-149">Элементы программы C#</span><span class="sxs-lookup"><span data-stu-id="6cc25-149">Elements of a C# program</span></span>

<span data-ttu-id="6cc25-150">Давайте рассмотрим важные части этой программы.</span><span class="sxs-lookup"><span data-stu-id="6cc25-150">Let's examine the important parts of this program.</span></span> <span data-ttu-id="6cc25-151">Первая строка содержит комментарий.</span><span class="sxs-lookup"><span data-stu-id="6cc25-151">The first line contains a comment.</span></span> <span data-ttu-id="6cc25-152">Символы `//` преобразуют остальную часть строки в комментарий.</span><span class="sxs-lookup"><span data-stu-id="6cc25-152">The characters `//` convert the rest of the line to a comment.</span></span>

[!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

<span data-ttu-id="6cc25-153">Вы можете также закомментировать блок текста, заключив его между символами `/*` и `*/`.</span><span class="sxs-lookup"><span data-stu-id="6cc25-153">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="6cc25-154">Эти действия показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6cc25-154">This is shown in the following example.</span></span>

[!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

<span data-ttu-id="6cc25-155">Консольное приложение C# должно содержать метод `Main`, в котором начинается и заканчивается управление.</span><span class="sxs-lookup"><span data-stu-id="6cc25-155">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="6cc25-156">В методе `Main` создаются объекты и выполняются другие методы.</span><span class="sxs-lookup"><span data-stu-id="6cc25-156">The `Main` method is where you create objects and execute other methods.</span></span>

<span data-ttu-id="6cc25-157">Метод `Main` является [статическим](../../language-reference/keywords/static.md) методом, расположенным внутри класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="6cc25-157">The `Main` method is a [static](../../language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="6cc25-158">В предыдущем примере "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="6cc25-158">In the previous "Hello World!"</span></span> <span data-ttu-id="6cc25-159">он размещается в классе с именем `Hello`.</span><span class="sxs-lookup"><span data-stu-id="6cc25-159">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="6cc25-160">Вы можете объявить метод `Main` одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="6cc25-160">You can declare the `Main` method in one of the following ways:</span></span>

- <span data-ttu-id="6cc25-161">Он может возвращать значение `void`.</span><span class="sxs-lookup"><span data-stu-id="6cc25-161">It can return `void`.</span></span> <span data-ttu-id="6cc25-162">Это означает, что программа не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="6cc25-162">That means your program doesn't return a value.</span></span>

[!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- <span data-ttu-id="6cc25-163">Он также может возвращать целое число.</span><span class="sxs-lookup"><span data-stu-id="6cc25-163">It can also return an integer.</span></span> <span data-ttu-id="6cc25-164">Данное целое число — это **код выхода** для приложения.</span><span class="sxs-lookup"><span data-stu-id="6cc25-164">The integer is the **exit code** for your application.</span></span>

[!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- <span data-ttu-id="6cc25-165">С любым из типов возвращаемых значений он может принимать аргументы.</span><span class="sxs-lookup"><span data-stu-id="6cc25-165">With either of the return types, it can take arguments.</span></span>

[!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

<span data-ttu-id="6cc25-166">-или-</span><span class="sxs-lookup"><span data-stu-id="6cc25-166">-or-</span></span>

[!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

<span data-ttu-id="6cc25-167">Параметр `args` метода `Main` является массивом значений типа `string`, который содержит аргументы командной строки, используемые для вызова программы.</span><span class="sxs-lookup"><span data-stu-id="6cc25-167">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span>

<span data-ttu-id="6cc25-168">Дополнительные сведения об использовании аргументов командной строки см. в примерах в разделе [Main() и аргументы командной строки](../main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="6cc25-168">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../main-and-command-args/index.md).</span></span>

## <a name="input-and-output"></a><span data-ttu-id="6cc25-169">Ввод и вывод</span><span class="sxs-lookup"><span data-stu-id="6cc25-169">Input and output</span></span>

<span data-ttu-id="6cc25-170">Программы на C#, как правило, используют службы ввода-вывода, предоставляемые библиотекой времени выполнения в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6cc25-170">C# programs generally use the input/output services provided by the run-time library of the .NET Framework.</span></span> <span data-ttu-id="6cc25-171">Инструкция `System.Console.WriteLine("Hello World!");` использует метод <xref:System.Console.WriteLine%2A>.</span><span class="sxs-lookup"><span data-stu-id="6cc25-171">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="6cc25-172">Это один из методов вывода класса <xref:System.Console> в библиотеке времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="6cc25-172">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="6cc25-173">Он отображает свой строковый параметр в стандартном потоке вывода, за которым следует новая строка.</span><span class="sxs-lookup"><span data-stu-id="6cc25-173">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="6cc25-174">Существуют и другие методы <xref:System.Console> для разных операций ввода и вывода.</span><span class="sxs-lookup"><span data-stu-id="6cc25-174">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="6cc25-175">Если вы добавите в начало программы директиву `using System;`, классы и методы <xref:System> можно использовать напрямую, не указывая их полные имена.</span><span class="sxs-lookup"><span data-stu-id="6cc25-175">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="6cc25-176">Например, можно вызвать `Console.WriteLine` вместо `System.Console.WriteLine`:</span><span class="sxs-lookup"><span data-stu-id="6cc25-176">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="6cc25-177">Дополнительные сведения о методах ввода-вывода см. в описании <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="6cc25-177">For more information about input/output methods, see <xref:System.IO>.</span></span>

## <a name="see-also"></a><span data-ttu-id="6cc25-178">См. также</span><span class="sxs-lookup"><span data-stu-id="6cc25-178">See also</span></span>

- [<span data-ttu-id="6cc25-179">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6cc25-179">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6cc25-180">Примеры и руководства</span><span class="sxs-lookup"><span data-stu-id="6cc25-180">Samples and tutorials</span></span>](../../../samples-and-tutorials/index.md)
- [<span data-ttu-id="6cc25-181">Main() и аргументы командной строки</span><span class="sxs-lookup"><span data-stu-id="6cc25-181">Main() and Command-Line Arguments</span></span>](../main-and-command-args/index.md)
- [<span data-ttu-id="6cc25-182">Начало работы с Visual C#</span><span class="sxs-lookup"><span data-stu-id="6cc25-182">Getting Started with Visual C#</span></span>](/visualstudio/ide/quickstart-csharp-console)
