---
title: Создание приложения Hello World с помощью .NET Core в Visual Studio
description: Узнайте, как создать свое первое консольное приложение .NET Core с помощью C# или Visual Basic в Visual Studio.
author: BillWagner
ms.author: wiwagn
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: ba996e4add1cfe44681154b00a6530b1f3e70b37
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713998"
---
# <a name="tutorial-create-your-first-net-core-console-application-in-visual-studio-2019"></a><span data-ttu-id="c7277-103">Учебник. Создание первого консольного приложения .NET Core в Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c7277-103">Tutorial: Create your first .NET Core console application in Visual Studio 2019</span></span>

<span data-ttu-id="c7277-104">В этой статье приводятся пошаговые инструкции по созданию и запуску консольного приложения Hello World .NET Core в Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="c7277-104">This article provides a step-by-step introduction to create and run a Hello World .NET Core console application in Visual Studio 2019.</span></span> <span data-ttu-id="c7277-105">Приложение Hello World традиционно используется для ознакомления начинающих с новым языком программирования.</span><span class="sxs-lookup"><span data-stu-id="c7277-105">A Hello World application is traditionally used to introduce beginners to a new programming language.</span></span> <span data-ttu-id="c7277-106">Эта программа просто отображает фразу "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="c7277-106">This program simply displays the phrase "Hello World!"</span></span> <span data-ttu-id="c7277-107">"Hello World!".</span><span class="sxs-lookup"><span data-stu-id="c7277-107">on the screen.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c7277-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c7277-108">Prerequisites</span></span>

- <span data-ttu-id="c7277-109">[Visual Studio 2019 версии 16.4 или более поздней](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) с установленной рабочей нагрузкой **Кроссплатформенная разработка .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="c7277-109">[Visual Studio 2019 version 16.4 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="c7277-110">Пакет SDK для .NET Core 3.1 устанавливается автоматически при выборе этой рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="c7277-110">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

<span data-ttu-id="c7277-111">Дополнительные сведения см. в разделе [Установка с помощью Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) статьи [Установка пакета SDK для .NET Core](../install/sdk.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="c7277-111">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-the-app"></a><span data-ttu-id="c7277-112">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="c7277-112">Create the app</span></span>

<span data-ttu-id="c7277-113">Ниже приведены инструкции по созданию простого консольного приложения Hello World:</span><span class="sxs-lookup"><span data-stu-id="c7277-113">The following instructions create a simple Hello World console application:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[<span data-ttu-id="c7277-114">C#</span><span class="sxs-lookup"><span data-stu-id="c7277-114">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="c7277-115">Запустите Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="c7277-115">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="c7277-116">Создайте проект консольного приложения .NET Core на C# с именем HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="c7277-116">Create a new C# .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="c7277-117">На начальном экране выберите **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="c7277-117">On the start window, choose **Create a new project**.</span></span>

      ![Кнопка "Создать проект", выбранная в начальном окне Visual Studio](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="c7277-119">На странице **Создание проекта** введите в поле поиска **консоль**.</span><span class="sxs-lookup"><span data-stu-id="c7277-119">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="c7277-120">Затем выберите **C#** в списке языков и **Все платформы** в списке платформ.</span><span class="sxs-lookup"><span data-stu-id="c7277-120">Next, choose **C#** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="c7277-121">Выберите шаблон **Консольное приложение (.NET Core)** и щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c7277-121">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![Окно "Создание проекта" с выбранными фильтрами](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="c7277-123">Если вы не видите шаблоны .NET Core, вероятно, вы не установили требуемую рабочую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="c7277-123">If you don't see the .NET Core templates, you're probably missing the required workload installed.</span></span> <span data-ttu-id="c7277-124">В сообщении **Не удается найти то, что ищете?** выберите ссылку **Установка других средств и компонентов**.</span><span class="sxs-lookup"><span data-stu-id="c7277-124">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="c7277-125">Откроется Visual Studio Installer.</span><span class="sxs-lookup"><span data-stu-id="c7277-125">The Visual Studio Installer opens.</span></span> <span data-ttu-id="c7277-126">Убедитесь, что у вас установлена рабочая нагрузка **Кроссплатформенная разработка .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="c7277-126">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="c7277-127">На странице **настройки нового проекта** введите **HelloWorld** в поле **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="c7277-127">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="c7277-128">Затем нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="c7277-128">Then, choose **Create**.</span></span>

      ![Окно настройки нового проекта с полями имени проекта, расположения и имени решения](./media/with-visual-studio/configure-new-project.png)

   <span data-ttu-id="c7277-130">Шаблон консольного приложения C# для .NET Core автоматически определяет класс `Program` с одним методом `Main`, который принимает в качестве аргумента массив <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="c7277-130">The C# Console Application template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="c7277-131">`Main` — точка входа в приложение. Это метод, который автоматически вызывается средой выполнения при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="c7277-131">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="c7277-132">Все аргументы, предоставленные в командной строке при запуске приложения, доступны через массив *args*.</span><span class="sxs-lookup"><span data-stu-id="c7277-132">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   ![Visual Studio и новый проект Hello World](./media/with-visual-studio/visual-studio-main-window.png)

# <a name="visual-basictabvb"></a>[<span data-ttu-id="c7277-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7277-134">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="c7277-135">Запустите Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="c7277-135">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="c7277-136">Создайте проект консольного приложения .NET Core на Visual Basic с именем HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="c7277-136">Create a new Visual Basic .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="c7277-137">На начальном экране выберите **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="c7277-137">On the start window, choose **Create a new project**.</span></span>

      ![Кнопка "Создать проект", выбранная в начальном окне Visual Studio](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="c7277-139">На странице **Создание проекта** введите в поле поиска **консоль**.</span><span class="sxs-lookup"><span data-stu-id="c7277-139">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="c7277-140">В списке языков выберите **Visual Basic**, а затем в списке платформ выберите **Все платформы**.</span><span class="sxs-lookup"><span data-stu-id="c7277-140">Next, choose **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="c7277-141">Выберите шаблон **Консольное приложение (.NET Core)** и щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c7277-141">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![Выбор шаблона Visual Basic для консольного приложения (.NET Framework)](./media/with-visual-studio/vb/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="c7277-143">Если вы не видите шаблоны .NET Core, вероятно, вы не установили требуемую рабочую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="c7277-143">If you don't see the .NET Core templates, you're probably missing the required workload installed.</span></span> <span data-ttu-id="c7277-144">В сообщении **Не удается найти то, что ищете?** выберите ссылку **Установка других средств и компонентов**.</span><span class="sxs-lookup"><span data-stu-id="c7277-144">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="c7277-145">Откроется Visual Studio Installer.</span><span class="sxs-lookup"><span data-stu-id="c7277-145">The Visual Studio Installer opens.</span></span> <span data-ttu-id="c7277-146">Убедитесь, что у вас установлена рабочая нагрузка **Кроссплатформенная разработка .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="c7277-146">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="c7277-147">На странице **настройки нового проекта** введите **HelloWorld** в поле **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="c7277-147">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="c7277-148">Затем нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="c7277-148">Then, choose **Create**.</span></span>

   <span data-ttu-id="c7277-149">Шаблон консольного приложения для .NET Core автоматически определяет класс `Program` с одним методом `Main`, который принимает в качестве аргумента массив <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="c7277-149">The console app template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="c7277-150">`Main` — точка входа в приложение. Это метод, который автоматически вызывается средой выполнения при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="c7277-150">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="c7277-151">Все аргументы, предоставленные в командной строке при запуске приложения, доступны в параметре `args`.</span><span class="sxs-lookup"><span data-stu-id="c7277-151">Any command-line arguments supplied when the application is launched are available in the `args` parameter.</span></span>

   ![Visual Studio и новый проект Hello World](./media/with-visual-studio/vb/visual-studio-main-window.png)

---

   <span data-ttu-id="c7277-153">Этот шаблон создает простое приложение Hello World.</span><span class="sxs-lookup"><span data-stu-id="c7277-153">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="c7277-154">Он вызывает метод <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> для отображения литеральной строки "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="c7277-154">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display the literal string "Hello World!"</span></span> <span data-ttu-id="c7277-155">в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="c7277-155">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="c7277-156">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="c7277-156">Run the app</span></span>

1. <span data-ttu-id="c7277-157">Чтобы запустить программу, выберите **HelloWorld** на панели инструментов или нажмите клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="c7277-157">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

   ![Панель инструментов Visual Studio с выбранной кнопкой запуска HelloWorld](./media/with-visual-studio/run-program.png)

   <span data-ttu-id="c7277-159">Откроется окно консоли с текстом "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="c7277-159">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="c7277-160">на экране и информацией об отладке Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c7277-160">printed on the screen and some Visual Studio debug information.</span></span>

   ![Окно консоли с приложением Hello World и надписью "Чтобы продолжить, нажмите любую клавишу"](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="c7277-162">Для закрытия консольного окна нажмите любую клавишу.</span><span class="sxs-lookup"><span data-stu-id="c7277-162">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="c7277-163">Улучшение приложения</span><span class="sxs-lookup"><span data-stu-id="c7277-163">Enhance the app</span></span>

<span data-ttu-id="c7277-164">Давайте расширим приложение. Теперь у пользователя будет запрашиваться имя, которое затем будет отображаться с датой и временем.</span><span class="sxs-lookup"><span data-stu-id="c7277-164">Enhance your application to prompt the user for their name and display it along with the date and time.</span></span> <span data-ttu-id="c7277-165">Ниже приведены инструкции по изменению и повторному запуску приложения:</span><span class="sxs-lookup"><span data-stu-id="c7277-165">The following instructions modify and run the app again:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="c7277-166">C#</span><span class="sxs-lookup"><span data-stu-id="c7277-166">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="c7277-167">Замените содержимое метода `Main` (в настоящий момент это просто строка, вызывающая `Console.WriteLine`) следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="c7277-167">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-csharp[GettingStarted#1](~/samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]

   <span data-ttu-id="c7277-168">Теперь код выдает строку "What is your name?" (Как вас зовут?)</span><span class="sxs-lookup"><span data-stu-id="c7277-168">This code displays "What is your name?"</span></span> <span data-ttu-id="c7277-169">в окно консоли и ожидает, чтобы пользователь ввел строку текста и нажал клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="c7277-169">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="c7277-170">Приложение сохраняет полученную строку в переменной с именем `name`.</span><span class="sxs-lookup"><span data-stu-id="c7277-170">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="c7277-171">Оно также получает значение свойства <xref:System.DateTime.Now?displayProperty=nameWithType>, которое содержит текущее локальное время, и присваивает его переменной с именем `date`.</span><span class="sxs-lookup"><span data-stu-id="c7277-171">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="c7277-172">Наконец, с помощью [интерполированной строки](../../csharp/language-reference/tokens/interpolated.md) эти значения выводятся в окно консоли.</span><span class="sxs-lookup"><span data-stu-id="c7277-172">Finally, it uses an [interpolated string](../../csharp/language-reference/tokens/interpolated.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="c7277-173">Скомпилируйте программу, выбрав действие **Сборка** > **Собрать решение**.</span><span class="sxs-lookup"><span data-stu-id="c7277-173">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="c7277-174">Чтобы запустить программу, выберите **HelloWorld** на панели инструментов или нажмите клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="c7277-174">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="c7277-175">В ответ на приглашение в командной строке введите имя и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="c7277-175">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![Окно консоли с измененными выходными данными программы](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="c7277-177">Для закрытия консольного окна нажмите любую клавишу.</span><span class="sxs-lookup"><span data-stu-id="c7277-177">Press any key to close the console window.</span></span>

# <a name="visual-basictabvb"></a>[<span data-ttu-id="c7277-178">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7277-178">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="c7277-179">Замените содержимое метода `Main` (в настоящий момент это просто строка, вызывающая `Console.WriteLine`) следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="c7277-179">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-vb[GettingStarted#1](~/samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]

   <span data-ttu-id="c7277-180">Теперь код выдает строку "What is your name?" (Как вас зовут?)</span><span class="sxs-lookup"><span data-stu-id="c7277-180">This code displays "What is your name?"</span></span> <span data-ttu-id="c7277-181">в окно консоли и ожидает, чтобы пользователь ввел строку текста и нажал клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="c7277-181">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="c7277-182">Приложение сохраняет полученную строку в переменной с именем `name`.</span><span class="sxs-lookup"><span data-stu-id="c7277-182">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="c7277-183">Оно также получает значение свойства <xref:System.DateTime.Now?displayProperty=nameWithType>, которое содержит текущее локальное время, и присваивает его переменной с именем `date`.</span><span class="sxs-lookup"><span data-stu-id="c7277-183">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="c7277-184">Наконец, с помощью [интерполированной строки](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) эти значения выводятся в окно консоли.</span><span class="sxs-lookup"><span data-stu-id="c7277-184">Finally, it uses an [interpolated string](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="c7277-185">Скомпилируйте программу, выбрав действие **Сборка** > **Собрать решение**.</span><span class="sxs-lookup"><span data-stu-id="c7277-185">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="c7277-186">Чтобы запустить программу, выберите **HelloWorld** на панели инструментов или нажмите клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="c7277-186">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="c7277-187">В ответ на приглашение в командной строке введите имя и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="c7277-187">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![Окно консоли с измененными выходными данными программы](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="c7277-189">Для закрытия консольного окна нажмите любую клавишу.</span><span class="sxs-lookup"><span data-stu-id="c7277-189">Press any key to close the console window.</span></span>

---

## <a name="next-steps"></a><span data-ttu-id="c7277-190">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="c7277-190">Next steps</span></span>

<span data-ttu-id="c7277-191">Работая с этой статьей, вы создали и запустили свое первое приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c7277-191">In this article, you've created and run your first .NET Core application.</span></span> <span data-ttu-id="c7277-192">На следующем шаге выполняется отладка приложения.</span><span class="sxs-lookup"><span data-stu-id="c7277-192">In the next step, you debug your app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c7277-193">Отладка приложения .NET Core Hello World на C# или Visual с помощью Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="c7277-193">Debug a .NET Core Hello World application in Visual Studio</span></span>](debugging-with-visual-studio.md)
