---
title: "Отладка приложения Hello World на C# в Visual Studio 2017"
description: "Сведения об отладке приложения Hello World, написанного на C#, в Visual Studio 2017."
keywords: ".NET Core, консольное приложение .NET Core, отладка .NET Core"
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: cb213625-cc60-438b-9b9e-49aed0e4a974
ms.translationtype: HT
ms.sourcegitcommit: e0271ba3392ce8861dc916714af8c16d4581ce4f
ms.openlocfilehash: 19744773d18f6ea43e4b4a7518405b60e6b53acf
ms.contentlocale: ru-ru
ms.lasthandoff: 08/14/2017

---

# <a name="debug-your-hello-world-application-with-visual-studio-2017"></a><span data-ttu-id="9e097-104">Отладка приложения Hello World в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="9e097-104">Debug your Hello World application with Visual Studio 2017</span></span>

<span data-ttu-id="9e097-105">Изучая руководство [Создание приложения Hello World на C# с помощью .NET Core в Visual Studio 2017](.\with-visual-studio.md) или [Создание приложения Hello World на Visual Basic с помощью .NET Core в Visual Studio 2017](vb-with-visual-studio.md), вы создали и запустили простое консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="9e097-105">So far, you've followed the steps in [Build a C# Hello World Application with .NET Core in Visual Studio 2017](.\with-visual-studio.md) or [Build a Visual Basic Hello World Application with .NET Core in Visual Studio 2017](vb-with-visual-studio.md) to create and run a simple console application.</span></span> <span data-ttu-id="9e097-106">После создания и компиляции приложения можно приступить к тестированию.</span><span class="sxs-lookup"><span data-stu-id="9e097-106">Once you've written and compiled your application, you can begin testing it.</span></span> <span data-ttu-id="9e097-107">Visual Studio включает широкий набор инструментальных средств, которые можно использовать для тестирования приложений и устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="9e097-107">Visual Studio includes a comprehensive set of debugging tools that you can use when testing and troubleshooting your application.</span></span>

## <a name="debugging-in-debug-mode"></a><span data-ttu-id="9e097-108">Отладка в режиме отладки</span><span class="sxs-lookup"><span data-stu-id="9e097-108">Debugging in Debug mode</span></span>

<span data-ttu-id="9e097-109">В Visual Studio по умолчанию используются две конфигурации сборки — *Отладка* и *Выпуск*.</span><span class="sxs-lookup"><span data-stu-id="9e097-109">*Debug* and *Release* are two of Visual Studio's default build configurations.</span></span> <span data-ttu-id="9e097-110">Используемая конфигурация сборки отображается на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="9e097-110">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="9e097-111">На следующем рисунке показана панель инструментов Visual Studio с активным режимом **отладки**.</span><span class="sxs-lookup"><span data-stu-id="9e097-111">The following toolbar image shows that Visual Studio is configured to compile your application in **Debug** mode.</span></span>

   ![Панель инструментов Visual Studio](./media/debugging-with-visual-studio/toolbar1.png)

<span data-ttu-id="9e097-113">Тестирование всегда следует начинать с режима отладки.</span><span class="sxs-lookup"><span data-stu-id="9e097-113">You should always begin by testing your program in Debug mode.</span></span> <span data-ttu-id="9e097-114">В режиме отладки компилятор отключает большинство инструментов оптимизации и предоставляет более подробные сведения о процессе сборки.</span><span class="sxs-lookup"><span data-stu-id="9e097-114">Debug mode turns off most compiler optimizations and provides richer information during the build process.</span></span>

## <a name="setting-a-breakpoint"></a><span data-ttu-id="9e097-115">Задание точки останова</span><span class="sxs-lookup"><span data-stu-id="9e097-115">Setting a breakpoint</span></span>

<span data-ttu-id="9e097-116">Запустите программу в режиме отладки и попробуйте использовать некоторые функции отладки:</span><span class="sxs-lookup"><span data-stu-id="9e097-116">Run your program in Debug mode and try a few debugging features:</span></span>

1. <span data-ttu-id="9e097-117">*Точка останова* приостанавливает выполнение приложения на инструкции, *предшествующей* той строке, в которой установлена точка останова.</span><span class="sxs-lookup"><span data-stu-id="9e097-117">A *breakpoint* temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span> 

# <a name="ctabcsharp"></a>[<span data-ttu-id="9e097-118">C#</span><span class="sxs-lookup"><span data-stu-id="9e097-118">C#</span></span>](#tab/csharp)
   <span data-ttu-id="9e097-119">Установите точку останова в строке `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");`. Для этого щелкните в левом поле этой строки в окне редактирования кода или выберите эту строку и затем пункт меню **Отладка** > **Точка останова**.</span><span class="sxs-lookup"><span data-stu-id="9e097-119">Set a breakpoint on the line that reads `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");` by clicking in the left margin of the code window on that line or by choosing the **Debug** > **Toggle Breakpoint** menu item with the line selected.</span></span> <span data-ttu-id="9e097-120">Как видно на следующем рисунке, строку с точкой останова Visual Studio обозначает подсветкой текста и красным кругом в ее левом поле.</span><span class="sxs-lookup"><span data-stu-id="9e097-120">As the following figure shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red circle in its left margin.</span></span>

   ![Окно приложения Visual Studio с установленной точкой останова](./media/debugging-with-visual-studio/setbreakpoint.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="9e097-122">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e097-122">Visual Basic</span></span>](#tab/visual-basic)
   <span data-ttu-id="9e097-123">Установите точку останова в строке `Console.WriteLine(vbCrLf + $"Hello, {name}, on {currentDate:d} at {currentDate:t}!")`. Для этого щелкните в левом поле этой строки в окне редактирования кода или выберите эту строку и затем пункт меню **Отладка** > **Точка останова**.</span><span class="sxs-lookup"><span data-stu-id="9e097-123">Set a breakpoint on the line that reads `Console.WriteLine(vbCrLf + $"Hello, {name}, on {currentDate:d} at {currentDate:t}!")` by clicking in the left margin of the code window on that line or by choosing the **Debug** > **Toggle Breakpoint** menu item with the line selected.</span></span> <span data-ttu-id="9e097-124">Как видно на следующем рисунке, строку с точкой останова Visual Studio обозначает подсветкой текста и красным кругом в ее левом поле.</span><span class="sxs-lookup"><span data-stu-id="9e097-124">As the following figure shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red circle in its left margin.</span></span>

   <a name="visual-studio-program-window-with-breakpoint-setmediadebugging-with-visual-studiovb-setbreakpointpng"></a>![Окно приложения Visual Studio с установленной точкой останова](./media/debugging-with-visual-studio/vb-setbreakpoint.png)
---

1. <span data-ttu-id="9e097-126">Запустите программу в режиме отладки. Для этого нажмите кнопку **HelloWorld** с зеленой стрелкой на панели инструментов, нажмите клавишу F5 или выберите пункт меню **Отладка** > **Начать отладку**.</span><span class="sxs-lookup"><span data-stu-id="9e097-126">Run the program in Debug mode by selecting the **HelloWorld** button with the green arrow on the toolbar, pressing F5, or choosing **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="9e097-127">Когда программа запросит имя, введите любую строку в окне консоли и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="9e097-127">Enter a string in the console window when the program prompts for a name and press Enter.</span></span>

1. <span data-ttu-id="9e097-128">Выполнение программы остановится, когда будет достигнута точка останова, то есть перед выполнением метода `Console.WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="9e097-128">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="9e097-129">В окне **Видимые** отображаются значения всех переменных, которые используются рядом с текущей строкой.</span><span class="sxs-lookup"><span data-stu-id="9e097-129">The **Autos** window displays the values of variables that are used around the current line.</span></span> <span data-ttu-id="9e097-130">В окне **Локальные** (которое можно открыть, выбрав вкладку **Локальные**) отображаются значения переменных, которые определены в текущем выполняемом методе.</span><span class="sxs-lookup"><span data-stu-id="9e097-130">The **Locals** window (which you can view by clicking the **Locals** tab) displays the values of variables that are defined in the currently executing method.</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="9e097-131">C#</span><span class="sxs-lookup"><span data-stu-id="9e097-131">C#</span></span>](#tab/csharp)
   ![Окно приложения Visual Studio](./media/debugging-with-visual-studio/break.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="9e097-133">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e097-133">Visual Basic</span></span>](#tab/visual-basic)
   <a name="visual-studio-application-windowmediadebugging-with-visual-studiovb-breakpng"></a>![Окно приложения Visual Studio](./media/debugging-with-visual-studio/vb-break.png)
---

1. <span data-ttu-id="9e097-135">Вы можете изменить значения переменных и посмотреть, как это повлияет на работу программы.</span><span class="sxs-lookup"><span data-stu-id="9e097-135">You can change the value of the variables to see how it affects your program.</span></span> <span data-ttu-id="9e097-136">Если **окно интерпретации** не отображается, откройте его, выбрав пункт меню **Отладка** > **Окна** > **Интерпретация**.</span><span class="sxs-lookup"><span data-stu-id="9e097-136">If the **Immediate Window** is not visible, display it by choosing the **Debug** > **Windows** > **Immediate** menu item.</span></span> <span data-ttu-id="9e097-137">**Окно интерпретации** позволяет взаимодействовать с приложением, которое вы отлаживаете.</span><span class="sxs-lookup"><span data-stu-id="9e097-137">The **Immediate Window** lets you interact with the application you're debugging.</span></span>

1. <span data-ttu-id="9e097-138">Вы можете изменять значения переменных и отслеживать изменения.</span><span class="sxs-lookup"><span data-stu-id="9e097-138">You can interactively change the values of variables.</span></span> <span data-ttu-id="9e097-139">Введите `name = "Gracie"` в **окно интерпретации** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="9e097-139">Enter `name = "Gracie"` in the **Immediate Window** and press the Enter key.</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="9e097-140">C#</span><span class="sxs-lookup"><span data-stu-id="9e097-140">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="9e097-141">Введите `date = new DateTime(2016,11,01,11,59,00)` в **окно интерпретации** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="9e097-141">Enter `date = new DateTime(2016,11,01,11,59,00)` in the **Immediate Window** and press the Enter key.</span></span>

   <span data-ttu-id="9e097-142">В **окне интерпретации** отображается значение строковой переменной и свойства значения @System.DateTime.</span><span class="sxs-lookup"><span data-stu-id="9e097-142">The **Immediate Window** displays the value of the string variable and the properties of the @System.DateTime value.</span></span> <span data-ttu-id="9e097-143">Кроме того, значения переменных обновляются в окнах **Видимые** и **Локальные**.</span><span class="sxs-lookup"><span data-stu-id="9e097-143">In addition, the value of the variables is updated in the **Autos** and **Locals** windows.</span></span>

   ![Окно "Видимые" и окно интерпретации](./media/debugging-with-visual-studio/autosimmediate.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="9e097-145">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e097-145">Visual Basic</span></span>](#tab/visual-basic)
1. <span data-ttu-id="9e097-146">Введите `currentDate = new DateTime(2016,11,01,11,59,00)` в **окно интерпретации** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="9e097-146">Enter `currentDate = new DateTime(2016,11,01,11,59,00)` in the **Immediate Window** and press the Enter key.</span></span>

<!-- The **Immediate Window** displays the value of the string variable and the properties of the @System.DateTime value. In addition, the value of the variables is updated in the **Autos** and **Locals** windows.

   ![Autos window and Immediate Window](./media/debugging-with-visual-studio/vb-autosimmediate.png)
-->
---

1. <span data-ttu-id="9e097-147">Возобновите выполнение программы, нажав кнопку **Продолжить** на панели инструментов или выбрав пункт меню **Отладка** > **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="9e097-147">Continue program execution by selecting the **Continue** button in the toolbar or by selecting the **Debug** > **Continue** menu item.</span></span> <span data-ttu-id="9e097-148">Значения, отображаемые в окне консоли, соответствуют изменениям, произведенным в **окне интерпретации**.</span><span class="sxs-lookup"><span data-stu-id="9e097-148">The values displayed in the console window correspond to the changes you made in the **Immediate Window**.</span></span>

   ![Окно консоли с набранным значением "Jack" в ответ на вопрос "What is your name?", за которым следует надпись "Hello Gracie" и дата и время "11/1/2016 11:59am"](./media/debugging-with-visual-studio/changed.png)

1. <span data-ttu-id="9e097-150">Нажмите любую клавишу, чтобы выйти из приложения и закрыть режим отладки.</span><span class="sxs-lookup"><span data-stu-id="9e097-150">Press any key to exit the application and end Debug mode.</span></span>

## <a name="setting-a-conditional-breakpoint"></a><span data-ttu-id="9e097-151">Установка условной точки останова</span><span class="sxs-lookup"><span data-stu-id="9e097-151">Setting a conditional breakpoint</span></span>

<span data-ttu-id="9e097-152">Ваша программа отображает строку, которую вводит пользователь.</span><span class="sxs-lookup"><span data-stu-id="9e097-152">Your program displays the string that the user enters.</span></span> <span data-ttu-id="9e097-153">Что произойдет, если пользователь ничего не введет?</span><span class="sxs-lookup"><span data-stu-id="9e097-153">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="9e097-154">Это можно проверить с помощью одной из полезных функций отладки — *условной точки останова*. Условная точка останова прерывает выполнение программы, если соблюдены одно или несколько условий.</span><span class="sxs-lookup"><span data-stu-id="9e097-154">You can test this with a useful debugging feature, the *conditional breakpoint*, which breaks program execution when one or more conditions are met.</span></span>

<span data-ttu-id="9e097-155">Чтобы проверить поведение программы в случае, когда пользователь не вводит текст, задайте условную точку останова следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9e097-155">To set a conditional breakpoint and test what happens when the user fails to enter a string, do the following:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="9e097-156">C#</span><span class="sxs-lookup"><span data-stu-id="9e097-156">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="9e097-157">Щелкните правой кнопкой мыши красную точку, обозначающую точку останова.</span><span class="sxs-lookup"><span data-stu-id="9e097-157">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="9e097-158">В контекстном меню выберите **Условия**. Откроется диалоговое окно **Параметры точки останова**.</span><span class="sxs-lookup"><span data-stu-id="9e097-158">On the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="9e097-159">Установите флажок **Условия**.</span><span class="sxs-lookup"><span data-stu-id="9e097-159">Check the box for **Conditions**.</span></span>

   ![Панель параметров точки останова](./media/debugging-with-visual-studio/breakpointsettings.png)

1. <span data-ttu-id="9e097-161">В поле **Выражение условия** замените "e.g. x == 5" на следующее условие:</span><span class="sxs-lookup"><span data-stu-id="9e097-161">For the **Conditional Expression** replace "e.g. x == 5" with the following:</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="9e097-162">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e097-162">Visual Basic</span></span>](#tab/visual-basic)
1. <span data-ttu-id="9e097-163">Щелкните правой кнопкой мыши красную точку, обозначающую точку останова.</span><span class="sxs-lookup"><span data-stu-id="9e097-163">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="9e097-164">В контекстном меню выберите **Условия**. Откроется диалоговое окно **Параметры точки останова**.</span><span class="sxs-lookup"><span data-stu-id="9e097-164">On the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="9e097-165">Установите флажок **Условия**.</span><span class="sxs-lookup"><span data-stu-id="9e097-165">Check the box for **Conditions**.</span></span>

   ![Панель параметров точки останова](./media/debugging-with-visual-studio/vb-breakpointsettings.png)

1. <span data-ttu-id="9e097-167">В поле **Условное выражение** замените "e.g. x = 5" на следующее условие:</span><span class="sxs-lookup"><span data-stu-id="9e097-167">For the **Conditional Expression** replace "e.g. x = 5" with the following:</span></span>

   ```vb
   String.IsNullOrEmpty(name)
   ```
---

   <span data-ttu-id="9e097-168">Вы проверяете условие в коде, которое заключается в том, что вызов метода `String.IsNullOrEmpty(name)` возвращает `true`, либо потому, что переменной *name* не присвоено значение, либо потому, что ее значение является пустой строкой ("").</span><span class="sxs-lookup"><span data-stu-id="9e097-168">You're testing for a code condition, that the `String.IsNullOrEmpty(name)` method call is `true` either because *name* has not been assigned a value or because its value is an empty string ("").</span></span> <span data-ttu-id="9e097-169">Также можно указать *количество обращений* (в этом случае выполнение программы будет прерываться до тех пор, пока не будет достигнуто заданное количество обращений) или *условие фильтра* (в этом случае выполнение программы будет прерываться на основе таких атрибутов, как идентификатор потока, имя процесса и имя потока).</span><span class="sxs-lookup"><span data-stu-id="9e097-169">You can also specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="9e097-170">Нажмите кнопку **Закрыть**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="9e097-170">Select the **Close** button to close the dialog.</span></span>

1. <span data-ttu-id="9e097-171">Запустите программу в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="9e097-171">Run the program in Debug mode.</span></span>

1. <span data-ttu-id="9e097-172">Когда в окне консоли появится предложение ввести имя, просто нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="9e097-172">In the console window, press the Enter key when prompted to enter your name.</span></span>

1. <span data-ttu-id="9e097-173">Так как указанное нами условие соблюдается (`name` имеет значение `null` или <xref:System.String.Empty?displayProperty=fullName>), выполнение программы будет остановлено при достижении точки останова, то есть перед выполнением метода `Console.WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="9e097-173">Because the condition we specified, `name` is either `null` or <xref:System.String.Empty?displayProperty=fullName>, has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="9e097-174">Выберите окно **Локальные**, в котором отображаются значения локальных переменных для текущего выполняемого метода (в нашем примере это метод `Main`).</span><span class="sxs-lookup"><span data-stu-id="9e097-174">Select the **Locals** window, which shows the values of variables that are local to the currently executing method, which is the `Main` method in your program.</span></span> <span data-ttu-id="9e097-175">Обратите внимание, что переменная `name` имеет значение `""` или <xref:System.String.Empty?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="9e097-175">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=fullName>.</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="9e097-176">C#</span><span class="sxs-lookup"><span data-stu-id="9e097-176">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="9e097-177">Убедитесь в том, что переменная содержит пустую строку, введя следующую инструкцию в **окне интерпретации**.</span><span class="sxs-lookup"><span data-stu-id="9e097-177">Confirm the value is an empty string by entering the following statement in the **Immediate Window**.</span></span> <span data-ttu-id="9e097-178">Результат равен `true`.</span><span class="sxs-lookup"><span data-stu-id="9e097-178">The result is `true`.</span></span>

   ```csharp
   ? name == String.Empty
   ```

   ![Значение true в окне интерпретации после выполнения инструкции](./media/debugging-with-visual-studio/emptystring.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="9e097-180">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e097-180">Visual Basic</span></span>](#tab/visual-basic)
1. <span data-ttu-id="9e097-181">Убедитесь в том, что переменная содержит пустую строку, введя следующую инструкцию в **окне интерпретации**.</span><span class="sxs-lookup"><span data-stu-id="9e097-181">Confirm the value is an empty string by entering the following statement in the **Immediate Window**.</span></span> <span data-ttu-id="9e097-182">Результат равен `true`.</span><span class="sxs-lookup"><span data-stu-id="9e097-182">The result is `true`.</span></span>

   ```vb
   ? String.IsNullOrEmpty(name)
   ```
  ![Значение true в окне интерпретации после выполнения инструкции](./media/debugging-with-visual-studio/vb-emptystring.png)
---

1. <span data-ttu-id="9e097-184">Нажмите кнопку **Продолжить** на панели инструментов, чтобы возобновить выполнение программы.</span><span class="sxs-lookup"><span data-stu-id="9e097-184">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="9e097-185">Нажмите любую клавишу, чтобы закрыть окно консоли и закрыть режим отладки.</span><span class="sxs-lookup"><span data-stu-id="9e097-185">Press any key to close the console window and exit Debug mode.</span></span>

1. <span data-ttu-id="9e097-186">Снимите точку останова. Для этого щелкните точку в левом поле окна изменения кода или установите курсор в строку с точкой останова и выберите пункт меню **Отладка > Точка останова**.</span><span class="sxs-lookup"><span data-stu-id="9e097-186">Clear the breakpoint by clicking on the dot in the left margin of the code window or by choosing the **Debug > Toggle Breakpoint** menu item with the row selected.</span></span>

---
## <a name="stepping-through-a-program"></a><span data-ttu-id="9e097-187">Пошаговое выполнение программы</span><span class="sxs-lookup"><span data-stu-id="9e097-187">Stepping through a program</span></span>

<span data-ttu-id="9e097-188">Visual Studio позволяет выполнять программу пошагово, отслеживая результат ее выполнения.</span><span class="sxs-lookup"><span data-stu-id="9e097-188">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="9e097-189">Обычно для использования этой функции задают точку останова и затем пошагово выполняют небольшой фрагмент программного кода.</span><span class="sxs-lookup"><span data-stu-id="9e097-189">Ordinarily, you'd set a breakpoint and use this feature to follow program flow though a small part of your program code.</span></span> <span data-ttu-id="9e097-190">Так как наша программа невелика, давайте пошагово выполним всю программу. Для этого сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="9e097-190">Since your program is small, you can step through the entire program by doing the following:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="9e097-191">C#</span><span class="sxs-lookup"><span data-stu-id="9e097-191">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="9e097-192">В строке меню выберите **Отладка** > **Выполнять по шагам** или нажмите клавишу F11.</span><span class="sxs-lookup"><span data-stu-id="9e097-192">On the menu bar, choose **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="9e097-193">Следующая выполняемая строка будет выделена, и рядом с ней появится стрелка.</span><span class="sxs-lookup"><span data-stu-id="9e097-193">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   ![Окно Visual Studio](./media/debugging-with-visual-studio/stepinto1.png)

   <span data-ttu-id="9e097-195">На этом этапе в окне **Видимые** будет показано, что в программе определена всего одна переменная — `args`.</span><span class="sxs-lookup"><span data-stu-id="9e097-195">At this point, the **Autos** window shows that your program has defined only one variable, `args`.</span></span> <span data-ttu-id="9e097-196">Так как в программу не передавались аргументы командной строки, значением этой переменной является пустой массив строк.</span><span class="sxs-lookup"><span data-stu-id="9e097-196">Because you haven't passed any command-line arguments to the program, its value is an empty string array.</span></span> <span data-ttu-id="9e097-197">Кроме того, Visual Studio открыла пустое окно консоли.</span><span class="sxs-lookup"><span data-stu-id="9e097-197">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="9e097-198">Выберите **Отладка** > **Выполнять по шагам** или нажмите клавишу F11.</span><span class="sxs-lookup"><span data-stu-id="9e097-198">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="9e097-199">Будет выделена следующая выполняемая строка.</span><span class="sxs-lookup"><span data-stu-id="9e097-199">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="9e097-200">Как показано на рисунке, на выполнение кода от предыдущей до текущей инструкции потребовалось менее одной миллисекунды.</span><span class="sxs-lookup"><span data-stu-id="9e097-200">As the figure shows, it has taken less than one millisecond to execute the code between the last statement and this one.</span></span> <span data-ttu-id="9e097-201">По-прежнему определена только одна переменная `args`. Окно консоли остается пустым.</span><span class="sxs-lookup"><span data-stu-id="9e097-201">`args` remains the only declared variable, and the console window remains blank.</span></span>

   ![Окно Visual Studio](./media/debugging-with-visual-studio/stepinto2.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="9e097-203">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e097-203">Visual Basic</span></span>](#tab/visual-basic)
1. <span data-ttu-id="9e097-204">В строке меню выберите **Отладка** > **Выполнять по шагам** или нажмите клавишу F11.</span><span class="sxs-lookup"><span data-stu-id="9e097-204">On the menu bar, choose **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="9e097-205">Следующая выполняемая строка будет выделена, и рядом с ней появится стрелка.</span><span class="sxs-lookup"><span data-stu-id="9e097-205">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   ![Окно Visual Studio](./media/debugging-with-visual-studio/vb-stepinto1.png)

   <span data-ttu-id="9e097-207">Так как на этом этапе вы не передали в программу аргументы командной строки, в окне **Видимые** указано, что значением переменной `args` является пустой массив строк.</span><span class="sxs-lookup"><span data-stu-id="9e097-207">At this point, because you haven't passed any command-line arguments to the program, the **Autos** window shows that the value of the `args` variable is an empty string array.</span></span> <span data-ttu-id="9e097-208">Кроме того, Visual Studio открыла пустое окно консоли.</span><span class="sxs-lookup"><span data-stu-id="9e097-208">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="9e097-209">Выберите **Отладка** > **Выполнять по шагам** или нажмите клавишу F11.</span><span class="sxs-lookup"><span data-stu-id="9e097-209">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="9e097-210">Будет выделена следующая выполняемая строка.</span><span class="sxs-lookup"><span data-stu-id="9e097-210">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="9e097-211">Как показано на рисунке, на выполнение кода от предыдущей до текущей инструкции потребовалось менее одной миллисекунды.</span><span class="sxs-lookup"><span data-stu-id="9e097-211">As the figure shows, it has taken less than one millisecond to execute the code between the last statement and this one.</span></span> <span data-ttu-id="9e097-212">По-прежнему определена только одна переменная `args`. Окно консоли остается пустым.</span><span class="sxs-lookup"><span data-stu-id="9e097-212">`args` remains the only declared variable, and the console window remains blank.</span></span>

   ![Окно Visual Studio](./media/debugging-with-visual-studio/vb-stepinto2.png)
---

1. <span data-ttu-id="9e097-214">Выберите **Отладка** > **Выполнять по шагам** или нажмите клавишу F11.</span><span class="sxs-lookup"><span data-stu-id="9e097-214">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="9e097-215">Visual Studio подсвечивает инструкцию, которая содержит присваивание значения переменной `name`.</span><span class="sxs-lookup"><span data-stu-id="9e097-215">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="9e097-216">В окне **Видимые** показано, что `name` имеет значение `null` (в C#) или `Nothing` (в Visual Basic), а в окне консоли появилась строка "What is your name?" (Введите имя).</span><span class="sxs-lookup"><span data-stu-id="9e097-216">The **Autos** window shows that `name` is `null` (in C#) or `Nothing` (in Visual Basic), and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="9e097-217">Ответьте на этот запрос, введя строку в окно консоли и нажав клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="9e097-217">Respond to the prompt by entering a string in the console window and pressing Enter.</span></span> <span data-ttu-id="9e097-218">Консоль никак не отреагирует на это, и введенная строка не будет отображаться в окне консоли, но метод <xref:System.Console.ReadLine%2A?displayProperty=fullName> получит введенные входные данные.</span><span class="sxs-lookup"><span data-stu-id="9e097-218">The console is unresponsive, and the string you enter isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=fullName> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="9e097-219">Выберите **Отладка** > **Выполнять по шагам** или нажмите клавишу F11.</span><span class="sxs-lookup"><span data-stu-id="9e097-219">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="9e097-220">Visual Studio подсвечивает оператор, который содержит присваивание значения переменной `date` (в C#) или `currentDate` (в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="9e097-220">Visual Studio highlights the statement that includes the `date` (in C#) or `currentDate` (in Visual Basic) variable assignment.</span></span> <span data-ttu-id="9e097-221">В окне **Видимые** отображается значение свойства <xref:System.DateTime.Now?displayProperty=fullName> и значение, полученное в результате вызова метода <xref:System.Console.ReadLine%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="9e097-221">The **Autos** window shows the <xref:System.DateTime.Now?displayProperty=fullName> property value and the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="9e097-222">Также в окне консоли появится строка, введенная в ответ на запрос консоли для ввода данных.</span><span class="sxs-lookup"><span data-stu-id="9e097-222">The console window also displays the string entered when the console prompted for input.</span></span>

1. <span data-ttu-id="9e097-223">Выберите **Отладка** > **Выполнять по шагам** или нажмите клавишу F11.</span><span class="sxs-lookup"><span data-stu-id="9e097-223">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="9e097-224">В окне **Видимые** отображается значение переменной `date`, которому было присвоено свойство <xref:System.DateTime.Now?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="9e097-224">The **Autos** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=fullName> property.</span></span> <span data-ttu-id="9e097-225">В окне консоли изменений не произошло.</span><span class="sxs-lookup"><span data-stu-id="9e097-225">The console window is unchanged.</span></span>

1. <span data-ttu-id="9e097-226">Выберите **Отладка** > **Выполнять по шагам** или нажмите клавишу F11.</span><span class="sxs-lookup"><span data-stu-id="9e097-226">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="9e097-227">Visual Studio вызывает метод <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="9e097-227">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=fullName> method.</span></span> <span data-ttu-id="9e097-228">Значения переменных `date` (или `currentDate`) и `name` отображаются в окне **Видимые**, а в окне консоли отображается форматированная строка.</span><span class="sxs-lookup"><span data-stu-id="9e097-228">The values of the `date` (or `currentDate`) and `name` variables appear in the **Autos** window, and the console window displays the formatted string.</span></span>

1. <span data-ttu-id="9e097-229">Выберите **Отладка** > **Выйти из режима пошагового выполнения** или нажмите SHIFT+F11.</span><span class="sxs-lookup"><span data-stu-id="9e097-229">Select **Debug** > **Step Out** or press Shift and the F11 key.</span></span> <span data-ttu-id="9e097-230">Пошаговое выполнение на этом прекратится.</span><span class="sxs-lookup"><span data-stu-id="9e097-230">This stops step-by-step execution.</span></span> <span data-ttu-id="9e097-231">В окне консоли отображается сообщение с предложением нажать любую клавишу для выхода.</span><span class="sxs-lookup"><span data-stu-id="9e097-231">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="9e097-232">Нажмите любую клавишу, чтобы закрыть окно консоли и закрыть режим отладки.</span><span class="sxs-lookup"><span data-stu-id="9e097-232">Press any key to close the console window and exit Debug mode.</span></span>

## <a name="building-a-release-version"></a><span data-ttu-id="9e097-233">Сборка версии в режиме выпуска</span><span class="sxs-lookup"><span data-stu-id="9e097-233">Building a Release version</span></span>

<span data-ttu-id="9e097-234">После сборки приложения в режиме отладки следует скомпилировать и протестировать приложение в режиме выпуска.</span><span class="sxs-lookup"><span data-stu-id="9e097-234">Once you've tested the Debug build of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="9e097-235">При сборке в режиме выпуска компилятор использует методы оптимизации, которые иногда могут негативно повлиять на поведение приложения.</span><span class="sxs-lookup"><span data-stu-id="9e097-235">The Release version incorporates compiler optimizations that can sometimes negatively affect the behavior of an application.</span></span> <span data-ttu-id="9e097-236">Например, оптимизации компилятора для повышения производительности могут привести к состоянию конкуренции в асинхронных и многопоточных приложениях.</span><span class="sxs-lookup"><span data-stu-id="9e097-236">For example, compiler optimizations that are designed to improve performance can create race conditions in asynchronous or multithreaded applications.</span></span>

<span data-ttu-id="9e097-237">Чтобы собрать и протестировать консольное приложение в режиме выпуска, переключите конфигурацию сборки из режима **Отладка** в режим **Выпуск** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="9e097-237">To build and test the Release version of your console application, change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

![Изображение](./media/debugging-with-visual-studio/toolbar2.png)

<span data-ttu-id="9e097-239">Если нажать клавишу F5 или выбрать пункт **Собрать решение** в меню **Сборка**, Visual Studio скомпилирует версию консольного приложения в режиме выпуска, которую можно протестировать.</span><span class="sxs-lookup"><span data-stu-id="9e097-239">When you press F5 or choose **Build Solution** from the **Build** menu, Visual Studio compiles the Release version of your console application.</span></span> <span data-ttu-id="9e097-240">Приложение, собранное в режиме выпуска, можно протестировать точно так же, как и в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="9e097-240">You can test it as you did the Debug version of the application.</span></span>

<span data-ttu-id="9e097-241">Завершив отладку приложения, вы можете опубликовать развертываемую версию своего приложения.</span><span class="sxs-lookup"><span data-stu-id="9e097-241">Once you've finished debugging your application, the next step is to publish a deployable version of your application.</span></span> <span data-ttu-id="9e097-242">Дополнительные сведения см. в разделе [Публикация приложения Hello World в Visual Studio 2017](./publishing-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="9e097-242">For information on how to do this, see [Publish the Hello World application with Visual Studio 2017](./publishing-with-visual-studio.md).</span></span>

