---
title: Использование библиотеки .NET Standard в Visual Studio
description: Создайте приложение .NET Core, которое вызывает члены из другой библиотеки классов, в Visual Studio 2019.
ms.date: 12/20/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: ec9c6f992bcd4a76e2f70018f3facca42b7b660c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714071"
---
# <a name="consume-a-net-standard-library-in-visual-studio"></a><span data-ttu-id="c7e53-103">Использование библиотеки .NET Standard в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c7e53-103">Consume a .NET Standard library in Visual Studio</span></span>

<span data-ttu-id="c7e53-104">После того, как вы создали библиотеку классов .NET Standard, протестировали ее и построили окончательную версию, следующий шаг — сделать ее доступной для вызывающих объектов.</span><span class="sxs-lookup"><span data-stu-id="c7e53-104">Once you've created a .NET Standard class library, tested it, and built a release version of the library, the next step is to make it available to callers.</span></span> <span data-ttu-id="c7e53-105">Для этого существуют два способа:</span><span class="sxs-lookup"><span data-stu-id="c7e53-105">You can do this in two ways:</span></span>

- <span data-ttu-id="c7e53-106">Если вся библиотека будет использоваться в одном решении (например, она является компонентом крупного приложения), достаточно включить библиотеку в проект этого решения.</span><span class="sxs-lookup"><span data-stu-id="c7e53-106">If the library will be used by a single solution (for example, if it's a component in a single large application), you can include it as a project in your solution.</span></span>
- <span data-ttu-id="c7e53-107">Если же библиотеку нужно сделать общедоступной, ее следует предоставлять как пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="c7e53-107">If the library will be publicly available, you can distribute it as a NuGet package.</span></span>

<span data-ttu-id="c7e53-108">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="c7e53-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="c7e53-109">добавить консольное приложение в свое решение, которое ссылается на проект библиотеки .NET Standard;</span><span class="sxs-lookup"><span data-stu-id="c7e53-109">Add a console app to your solution that references a .NET Standard library project.</span></span>
> - <span data-ttu-id="c7e53-110">создать пакет NuGet, содержащий проект библиотеки .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="c7e53-110">Create a NuGet package that contains a .NET Standard library project.</span></span>

## <a name="add-a-console-app-to-your-solution"></a><span data-ttu-id="c7e53-111">Добавление консольного приложения в решение</span><span class="sxs-lookup"><span data-stu-id="c7e53-111">Add a console app to your solution</span></span>

<span data-ttu-id="c7e53-112">Ранее в [Тестирование библиотеки .NET Standard с помощью .NET Core в Visual Studio 2017](testing-library-with-visual-studio.md) вы включали модульные тесты в решение библиотеки классов. Теперь в это решение можно точно так же включить новое приложение.</span><span class="sxs-lookup"><span data-stu-id="c7e53-112">Just as you included unit tests in the same solution as your class library in [Test a .NET Standard library in Visual Studio](testing-library-with-visual-studio.md), you can include your application as part of that solution.</span></span> <span data-ttu-id="c7e53-113">Например, библиотеку классов можно использовать в консольном приложении, которое будет предлагать пользователю ввести строку и определять, является ли первый символ этой строки символом верхнего регистра:</span><span class="sxs-lookup"><span data-stu-id="c7e53-113">For example, you can use your class library in a console application that prompts the user to enter a string and reports whether its first character is uppercase:</span></span>

1. <span data-ttu-id="c7e53-114">Откройте решение`ClassLibraryProjects`, созданное при работе со статьей [Создание библиотеки .NET Standard на C# с помощью пакета SDK для .NET Core в Visual Studio 2017](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="c7e53-114">Open the `ClassLibraryProjects` solution you created in the [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md) article.</span></span>

1. <span data-ttu-id="c7e53-115">Добавьте к решению новое консольное приложение .NET Core под названием "Демонстрация".</span><span class="sxs-lookup"><span data-stu-id="c7e53-115">Add a new .NET Core console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="c7e53-116">Щелкните решение в **Обозревателе решений** правой кнопкой мыши и выберите **Добавить** > **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="c7e53-116">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="c7e53-117">На странице **Добавить новый проект** введите в поле поиска **консоль**.</span><span class="sxs-lookup"><span data-stu-id="c7e53-117">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="c7e53-118">Выберите **C#** или **Visual Basic** из списка языков, а затем — **Все платформы** из списка платформ.</span><span class="sxs-lookup"><span data-stu-id="c7e53-118">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="c7e53-119">Выберите шаблон **Консольное приложение (.NET Core)** и щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c7e53-119">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="c7e53-120">На странице **Настроить новый проект** введите **Демонстрация** в поле **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="c7e53-120">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="c7e53-121">Затем нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="c7e53-121">Then, choose **Create**.</span></span>

1. <span data-ttu-id="c7e53-122">В окне **Обозреватель решений** щелкните правой кнопкой мыши проект **ShowCase** и выберите команду **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="c7e53-122">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![Контекстное меню проекта с пунктом "Назначить запускаемым проектом" в Visual Studio](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="c7e53-124">Изначально у этого проекта нет доступа к библиотеке классов.</span><span class="sxs-lookup"><span data-stu-id="c7e53-124">Initially, your project doesn't have access to your class library.</span></span> <span data-ttu-id="c7e53-125">Чтобы позволить приложению вызывать методы из библиотеки классов, создайте ссылку на библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="c7e53-125">To allow it to call methods in your class library, you create a reference to the class library.</span></span> <span data-ttu-id="c7e53-126">В окне **Обозреватель решений** щелкните правой кнопкой мыши узел **Зависимости** проекта `ShowCase` и выберите команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="c7e53-126">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node and select **Add Reference**.</span></span>

   ![Контекстное меню с пунктом "Добавить ссылку" в Visual Studio](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="c7e53-128">В диалоговом окне **Диспетчер ссылок** выберите проект библиотеки классов **StringLibrary**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c7e53-128">In the **Reference Manager** dialog, select **StringLibrary**, your class library project, and select the **OK** button.</span></span>

   ![Диалоговое окно "Диспетчер ссылок" с выбранной StringLibrary](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. <span data-ttu-id="c7e53-130">В окне кода замените весь код файла *Program.cs* или *Program.vb* следующим текстом:</span><span class="sxs-lookup"><span data-stu-id="c7e53-130">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code:</span></span>

   [!code-csharp[UsingClassLib#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]
   [!code-vb[UsingClassLib#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   <span data-ttu-id="c7e53-131">В этом коде используется переменная `row` для сохранения количества строк данных, записываемых в окно консоли.</span><span class="sxs-lookup"><span data-stu-id="c7e53-131">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="c7e53-132">Всякий раз, когда оно достигает значения 25 или превышает его, код очищает окно консоли и отображается сообщение для пользователя.</span><span class="sxs-lookup"><span data-stu-id="c7e53-132">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="c7e53-133">Сама программа предлагает пользователю ввести строку.</span><span class="sxs-lookup"><span data-stu-id="c7e53-133">The program prompts the user to enter a string.</span></span> <span data-ttu-id="c7e53-134">Она сообщает, начинается ли строка с символа верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="c7e53-134">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="c7e53-135">Если пользователь нажимает клавишу ВВОД, не введя никакой строки, приложение закрывается и окно консоли и завершает свою работу.</span><span class="sxs-lookup"><span data-stu-id="c7e53-135">If the user presses the Enter key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="c7e53-136">При необходимости можно изменить режим на панели инструментов, чтобы скомпилировать **отладочную** версию проекта `ShowCase`.</span><span class="sxs-lookup"><span data-stu-id="c7e53-136">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="c7e53-137">Скомпилируйте и запустите программу, нажав зеленую стрелку на кнопке **ShowCase**.</span><span class="sxs-lookup"><span data-stu-id="c7e53-137">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![Панель инструментов проекта в Visual Studio c кнопкой отладки](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)

<span data-ttu-id="c7e53-139">Чтобы отладить и опубликовать приложение, которое использует эту библиотеку, выполните действия из статей [Отладка приложения .NET Core Hello World на C# или Visual с помощью Visual Studio 2017](debugging-with-visual-studio.md) и [Публикация приложения Hello World .NET Core в Visual Studio 2017](publishing-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="c7e53-139">You can debug and publish the application that uses this library by following the steps in [Debug your C# or Visual Basic .NET Core Hello World application using Visual Studio](debugging-with-visual-studio.md) and [Publish your .NET Core Hello World application with Visual Studio](publishing-with-visual-studio.md).</span></span>

## <a name="create-a-nuget-package"></a><span data-ttu-id="c7e53-140">Создание пакета NuGet</span><span class="sxs-lookup"><span data-stu-id="c7e53-140">Create a NuGet package</span></span>

<span data-ttu-id="c7e53-141">Библиотеку классов можно распространить и для других разработчиков, опубликовав ее в виде пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="c7e53-141">You can make your class library widely available by publishing it as a NuGet package.</span></span> <span data-ttu-id="c7e53-142">Visual Studio не поддерживает создание пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="c7e53-142">Visual Studio doesn't support the creation of NuGet packages.</span></span> <span data-ttu-id="c7e53-143">Для его создания необходимо использовать команды .NET Core CLI:</span><span class="sxs-lookup"><span data-stu-id="c7e53-143">To create one, you need to use the .NET Core CLI commands:</span></span>

1. <span data-ttu-id="c7e53-144">Откройте окно консоли.</span><span class="sxs-lookup"><span data-stu-id="c7e53-144">Open a console window.</span></span>

   <span data-ttu-id="c7e53-145">Например, введите **Командная строка** в поле поиска на панели задач Windows.</span><span class="sxs-lookup"><span data-stu-id="c7e53-145">For example, enter **Command Prompt** in the search box on the Windows task bar.</span></span> <span data-ttu-id="c7e53-146">Выберите приложение **Командной строки** для рабочего стола или нажмите **Ввод**, если оно уже выбрано в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="c7e53-146">Select the **Command Prompt** desktop app or press **Enter** if it's already selected in the search results.</span></span>

1. <span data-ttu-id="c7e53-147">Перейдите в каталог с проектом библиотеки.</span><span class="sxs-lookup"><span data-stu-id="c7e53-147">Navigate to your library's project directory.</span></span> <span data-ttu-id="c7e53-148">Этот каталог содержит исходный код и файл проекта (*StringLibrary.csproj*) или *StringLibrary.vbproj*.</span><span class="sxs-lookup"><span data-stu-id="c7e53-148">The directory contains your source code and a project file, *StringLibrary.csproj* or *StringLibrary.vbproj*.</span></span>

1. <span data-ttu-id="c7e53-149">Запустите команду [dotnet pack](../tools/dotnet-pack.md), чтобы получить пакет с расширением: *.nupkg*.</span><span class="sxs-lookup"><span data-stu-id="c7e53-149">Run the [dotnet pack](../tools/dotnet-pack.md) command to generate a package with a *.nupkg* extension:</span></span>

   ```dotnetcli
   dotnet pack --no-build
   ```

   > [!TIP]
   > <span data-ttu-id="c7e53-150">Если каталог, содержащий *dotnet.exe*, не находится в системном пути, найдите расположение этого файла, введя `where dotnet.exe` в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="c7e53-150">If the directory that contains *dotnet.exe* is not in your PATH, you can find its location by entering `where dotnet.exe` in the console window.</span></span>

<span data-ttu-id="c7e53-151">Дополнительные сведения о создании пакетов NuGet см. в статье [Как создать пакет NuGet с помощью средств интерфейса командной строки (CLI) .NET Core](../deploying/creating-nuget-packages.md).</span><span class="sxs-lookup"><span data-stu-id="c7e53-151">For more information on creating NuGet packages, see [How to Create a NuGet Package with Cross Platform Tools](../deploying/creating-nuget-packages.md).</span></span>
