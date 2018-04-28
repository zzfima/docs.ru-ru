---
title: 'Начало работы с F # в коде Visual Studio'
description: 'Сведения об использовании языка F # с кодом Visual Studio и suite Ionide подключаемого модуля.'
author: cartermp
ms.author: phcart
ms.date: 02/28/2018
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 43fed76a57bd7749a7f22a2039ad625e3d26d132
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="59387-103">Начало работы с F # в коде Visual Studio</span><span class="sxs-lookup"><span data-stu-id="59387-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="59387-104">Вы можете написать F # в [кода Visual Studio](https://code.visualstudio.com) с [Ionide подключаемый модуль](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), чтобы получить прекрасные возможности кросс платформенных, простое интегрированной среды разработки (среде разработки Integrade) с технологией IntelliSense и базовый код Рефакторинг.</span><span class="sxs-lookup"><span data-stu-id="59387-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), to get a great cross-platform, lightweight IDE (Integrade Development Enivronment) experience with IntelliSense and basic code refactorings.</span></span>  <span data-ttu-id="59387-105">Посетите [Ionide.io](http://ionide.io) для получения дополнительных сведений о наборе подключаемого модуля.</span><span class="sxs-lookup"><span data-stu-id="59387-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin suite.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="59387-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="59387-106">Prerequisites</span></span>

<span data-ttu-id="59387-107">Необходимо иметь [git установлен](https://git-scm.com/download) и доступна на путь, чтобы сделать использование шаблонов проектов в Ionide.</span><span class="sxs-lookup"><span data-stu-id="59387-107">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates in Ionide.</span></span>  <span data-ttu-id="59387-108">Убедитесь, что он правильно установлен, введя `git --version` командной строки и нажав клавишу **ввод**.</span><span class="sxs-lookup"><span data-stu-id="59387-108">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="59387-109">macOS</span><span class="sxs-lookup"><span data-stu-id="59387-109">macOS</span></span>](#tab/macos)

<span data-ttu-id="59387-110">Использует Ionide [моно](http://www.mono-project.com).</span><span class="sxs-lookup"><span data-stu-id="59387-110">Ionide uses [Mono](http://www.mono-project.com).</span></span>  <span data-ttu-id="59387-111">Самый простой способ установить Mono на macOS — через Homebrew.</span><span class="sxs-lookup"><span data-stu-id="59387-111">The easiest way to install Mono on macOS is via Homebrew.</span></span>  <span data-ttu-id="59387-112">Просто введите следующую команду в окне терминала:</span><span class="sxs-lookup"><span data-stu-id="59387-112">Simply type the following into your terminal:</span></span>

```
brew install mono
```

<span data-ttu-id="59387-113">Необходимо также установить [пакета SDK для .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="59387-113">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="59387-114">Linux</span><span class="sxs-lookup"><span data-stu-id="59387-114">Linux</span></span>](#tab/linux)

<span data-ttu-id="59387-115">В Linux, также использует Ionide [моно](https://www.mono-project.com).</span><span class="sxs-lookup"><span data-stu-id="59387-115">On Linux, Ionide also uses [Mono](https://www.mono-project.com).</span></span> <span data-ttu-id="59387-116">Если вы на Debian и Ubuntu, можно использовать следующее:</span><span class="sxs-lookup"><span data-stu-id="59387-116">If you're on Debian or Ubuntu, you can use the following:</span></span>

```
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="59387-117">Необходимо также установить [пакета SDK для .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="59387-117">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="59387-118">Windows</span><span class="sxs-lookup"><span data-stu-id="59387-118">Windows</span></span>](#tab/windows)

<span data-ttu-id="59387-119">Если вы в Windows, необходимо [установить Visual Studio с поддержкой F #](get-started-visual-studio.md#installing-f).</span><span class="sxs-lookup"><span data-stu-id="59387-119">If you're on Windows, you must [install Visual Studio with F# support](get-started-visual-studio.md#installing-f).</span></span> <span data-ttu-id="59387-120">При этом устанавливаются все необходимые компоненты для записи, компиляции и выполнения кода F #.</span><span class="sxs-lookup"><span data-stu-id="59387-120">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="59387-121">Необходимо также установить [пакета SDK для .NET Core](https://www.microsoft.com/net/download/).</span><span class="sxs-lookup"><span data-stu-id="59387-121">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

## <a name="installing-visual-studio-code-and-the-ionide-plugin"></a><span data-ttu-id="59387-122">Установка Visual Studio Code и подключаемый модуль Ionide</span><span class="sxs-lookup"><span data-stu-id="59387-122">Installing Visual Studio Code and the Ionide plugin</span></span>

<span data-ttu-id="59387-123">Можно установить Visual Studio код из [code.visualstudio.com](https://code.visualstudio.com) веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="59387-123">You can install Visual Studio Code from the [code.visualstudio.com](https://code.visualstudio.com) website.</span></span> <span data-ttu-id="59387-124">После этого можно найти подключаемый модуль Ionide двумя способами:</span><span class="sxs-lookup"><span data-stu-id="59387-124">After that, there are two ways to find the Ionide plugin:</span></span>

1. <span data-ttu-id="59387-125">Использовать палитру команд (Ctrl + Shift + P в Windows, ⌘ + Shift + P на macOS Ctrl + Shift + P в Linux) и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="59387-125">Use the Command Palette (Ctrl+Shift+P on Windows, ⌘+Shift+P on macOS, Ctrl+Shift+P on Linux) and type the following:</span></span>

    ```
    >ext install Ionide
    ```

2. <span data-ttu-id="59387-126">Щелкните значок расширения и выполните поиск «Ionide»:</span><span class="sxs-lookup"><span data-stu-id="59387-126">Click the Extensions icon and search for "Ionide":</span></span>

    ![](media/getting-started-vscode/vscode-ext.png)

<span data-ttu-id="59387-127">Только для поддержки F # в коде Visual Studio требуется подключаемый модуль [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="59387-127">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="59387-128">Тем не менее, можно также установить [Ionide ИМИТАЦИИ](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) и получить [ПОДДЕЛАТЬ](https://fsharp.github.io/FAKE/) поддержки и [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) для получения [Paket](https://fsprojects.github.io/Paket/) поддержки.</span><span class="sxs-lookup"><span data-stu-id="59387-128">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) and to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="59387-129">ПОДДЕЛАТЬ и Paket средства сообщества дополнительные F # для создания проектов и управление зависимостями, соответственно.</span><span class="sxs-lookup"><span data-stu-id="59387-129">FAKE and Paket are additonal F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="59387-130">Создание первого проекта с Ionide</span><span class="sxs-lookup"><span data-stu-id="59387-130">Creating your first project with Ionide</span></span>

<span data-ttu-id="59387-131">Чтобы создать новый проект F #, откройте кода Visual Studio в новую папку (можно назвать его любым).</span><span class="sxs-lookup"><span data-stu-id="59387-131">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

![](media/getting-started-vscode/vscode-open-dir.png)

<span data-ttu-id="59387-132">Затем откройте в палитру команд (Ctrl + Shift + P в Windows, ⌘ + Shift + P на macOS Ctrl + Shift + P в Linux) и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="59387-132">Next, open the Command Palette (Ctrl+Shift+P on Windows, ⌘+Shift+P on macOS, Ctrl+Shift+P on Linux) and type the following:</span></span>

```
>f#: New Project
```

<span data-ttu-id="59387-133">Это работает на основе [FORGE](https://github.com/fsharp-editing/Forge) проекта.</span><span class="sxs-lookup"><span data-stu-id="59387-133">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>  <span data-ttu-id="59387-134">Результат должен быть примерно таким:</span><span class="sxs-lookup"><span data-stu-id="59387-134">You should see something like this:</span></span>

![](media/getting-started-vscode/vscode-new-proj.png)

> [!NOTE]
<span data-ttu-id="59387-135">Если вы не видите выше, обновите шаблоны, выполнив следующую команду в палитру команд: `>F#: Refresh Project Templates`.</span><span class="sxs-lookup"><span data-stu-id="59387-135">If you don't see the above, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="59387-136">Выберите «F #: новый проект», нажав **ввод**, которой вы перейдете этот шаг:</span><span class="sxs-lookup"><span data-stu-id="59387-136">Select "F#: New Project" by hitting **Enter**, which will take you to this step:</span></span>

![](media/getting-started-vscode/vscode-proj-type.png)

<span data-ttu-id="59387-137">Это будет выбрать шаблон для определенного типа проекта.</span><span class="sxs-lookup"><span data-stu-id="59387-137">This will select a template for a specific type of project.</span></span>  <span data-ttu-id="59387-138">Существует довольно много вариантов, например [FsLab](https://fslab.org) шаблон для обработки и анализа данных или [Suave](https://suave.io) шаблона для веб-программирования.</span><span class="sxs-lookup"><span data-stu-id="59387-138">There are quite a few options here, such as an [FsLab](https://fslab.org) template for Data Science or [Suave](https://suave.io) template for Web Programming.</span></span>  <span data-ttu-id="59387-139">В этой статье используется `classlib` шаблона, поэтому выделения и нажмите кнопку **ввод**.</span><span class="sxs-lookup"><span data-stu-id="59387-139">This article uses the `classlib` template, so highlight that and hit **Enter**.</span></span>  <span data-ttu-id="59387-140">Затем будет достигнут следующий шаг:</span><span class="sxs-lookup"><span data-stu-id="59387-140">You will then reach the following step:</span></span>

![](media/getting-started-vscode/vscode-new-dir.png)

<span data-ttu-id="59387-141">Это позволяет при необходимости создания проекта в другом каталоге.</span><span class="sxs-lookup"><span data-stu-id="59387-141">This lets you create the project in a different directory, if you like.</span></span>  <span data-ttu-id="59387-142">Не указывайте его сейчас.</span><span class="sxs-lookup"><span data-stu-id="59387-142">Leave it blank for now.</span></span>  <span data-ttu-id="59387-143">Он будет создан проект в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="59387-143">It will create the project in the current directory.</span></span>  <span data-ttu-id="59387-144">После нажатия клавиши **ввод**, будет достигнут следующий шаг:</span><span class="sxs-lookup"><span data-stu-id="59387-144">Once you press **Enter**, you will reach the following step:</span></span>

![](media/getting-started-vscode/vscode-proj-name.png)

<span data-ttu-id="59387-145">Это позволяет имя проекта.</span><span class="sxs-lookup"><span data-stu-id="59387-145">This lets you name your project.</span></span>  <span data-ttu-id="59387-146">F # использует [случае Pascal](http://c2.com/cgi/wiki?PascalCase) для имен проектов.</span><span class="sxs-lookup"><span data-stu-id="59387-146">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span>  <span data-ttu-id="59387-147">В этой статье используется `ClassLibraryDemo` как имя.</span><span class="sxs-lookup"><span data-stu-id="59387-147">This article uses `ClassLibraryDemo` as the name.</span></span>  <span data-ttu-id="59387-148">Как только вы ввели имя для проекта, нажмите **ввод**.</span><span class="sxs-lookup"><span data-stu-id="59387-148">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="59387-149">Если были выполнены действия предыдущего шага, вы должны получить Visual Studio код рабочей области с левой стороны выглядит примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="59387-149">If you followed the previous step steps, you should get the Visual Studio Code Workspace on the left-hand side to look something like this:</span></span>

![](media/getting-started-vscode/vscode-new-proj-explorer.png)

<span data-ttu-id="59387-150">Этот шаблон создает некоторые моменты, которые вы найдете полезные:</span><span class="sxs-lookup"><span data-stu-id="59387-150">This template generates a few things you'll find useful:</span></span>

1. <span data-ttu-id="59387-151">F # сам проект, под `ClassLibraryDemo` папки.</span><span class="sxs-lookup"><span data-stu-id="59387-151">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="59387-152">Правильной структуры каталогов для добавления пакетов через [ `Paket` ](https://fsprojects.github.io/Paket/).</span><span class="sxs-lookup"><span data-stu-id="59387-152">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="59387-153">Кросс платформенных создания скрипта с [ `FAKE` ](https://fsharp.github.io/FAKE/).</span><span class="sxs-lookup"><span data-stu-id="59387-153">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="59387-154">`paket.exe` Исполняемый файл, в которой можно получить пакеты и разрешить зависимости для вас.</span><span class="sxs-lookup"><span data-stu-id="59387-154">The `paket.exe` executable which can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="59387-155">Объект `.gitignore` файл, если вы хотите добавить этот проект с системой управления версиями, основанных на Git.</span><span class="sxs-lookup"><span data-stu-id="59387-155">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="59387-156">Написание кода</span><span class="sxs-lookup"><span data-stu-id="59387-156">Writing some code</span></span>

<span data-ttu-id="59387-157">Откройте *ClassLibraryDemo* папки.</span><span class="sxs-lookup"><span data-stu-id="59387-157">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="59387-158">Вы увидите следующие файлы:</span><span class="sxs-lookup"><span data-stu-id="59387-158">You should see the following files:</span></span>

1. <span data-ttu-id="59387-159">`ClassLibraryDemo.fs`, файле реализации F # с помощью класса, определенного.</span><span class="sxs-lookup"><span data-stu-id="59387-159">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="59387-160">`CassLibraryDemo.fsproj`, F # файл проекта используется для построения данного проекта.</span><span class="sxs-lookup"><span data-stu-id="59387-160">`CassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="59387-161">`Script.fsx`, в файл скрипта F # который загружает исходный файл.</span><span class="sxs-lookup"><span data-stu-id="59387-161">`Script.fsx`, an F# script file which loads the source file.</span></span>
4. <span data-ttu-id="59387-162">`paket.references`, в файл Paket, который указывает зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="59387-162">`paket.references`, a Paket file which specifies the project dependencies.</span></span>

<span data-ttu-id="59387-163">Откройте `Script.fsx`и добавьте следующий код в конце:</span><span class="sxs-lookup"><span data-stu-id="59387-163">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="59387-164">Эта функция преобразует слова в форму [Pig латиница](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="59387-164">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span>  <span data-ttu-id="59387-165">Следующим шагом является оценка с помощью F # интерактивный (FSI).</span><span class="sxs-lookup"><span data-stu-id="59387-165">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="59387-166">Выделите всей функции (должна быть 11 строк).</span><span class="sxs-lookup"><span data-stu-id="59387-166">Highlight the entire function (it should be 11 lines long).</span></span>  <span data-ttu-id="59387-167">Как только он выделяется, удерживайте **Alt** ключа и нажмите кнопку **ввод**.</span><span class="sxs-lookup"><span data-stu-id="59387-167">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span>  <span data-ttu-id="59387-168">Вы заметите всплывающее ниже окна и будет выглядеть примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="59387-168">You'll notice a window pop up below, and it should show something like this:</span></span>

![](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="59387-169">Это сделали три действия:</span><span class="sxs-lookup"><span data-stu-id="59387-169">This did three things:</span></span>

1. <span data-ttu-id="59387-170">Он запущен процесс FSI.</span><span class="sxs-lookup"><span data-stu-id="59387-170">It started the FSI process.</span></span>
2. <span data-ttu-id="59387-171">Выделенный вами код передаваемых FSI процесса.</span><span class="sxs-lookup"><span data-stu-id="59387-171">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="59387-172">Процесс FSI вычисляется код, отправляемых по.</span><span class="sxs-lookup"><span data-stu-id="59387-172">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="59387-173">Из-за отправляемых по [функция](../language-reference/functions/index.md), теперь можно вызвать этой функции с FSI!</span><span class="sxs-lookup"><span data-stu-id="59387-173">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span>  <span data-ttu-id="59387-174">В интерактивном окне введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="59387-174">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="59387-175">Должен появиться следующий результат:</span><span class="sxs-lookup"><span data-stu-id="59387-175">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="59387-176">Теперь попробуем с первой буквой гласные.</span><span class="sxs-lookup"><span data-stu-id="59387-176">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="59387-177">Введите следующий текст:</span><span class="sxs-lookup"><span data-stu-id="59387-177">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="59387-178">Должен появиться следующий результат:</span><span class="sxs-lookup"><span data-stu-id="59387-178">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="59387-179">По-видимому, функция работает, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="59387-179">The function appears to be working as expected.</span></span>  <span data-ttu-id="59387-180">Итак, просто написал первой функции F # в Visual Studio Code и его для оценки FSI.</span><span class="sxs-lookup"><span data-stu-id="59387-180">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

>[!NOTE]
<span data-ttu-id="59387-181">Как можно заметить, в строках в FSI завершаются `;;`.</span><span class="sxs-lookup"><span data-stu-id="59387-181">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span>  <span data-ttu-id="59387-182">Это происходит потому FSI позволяет вводить несколько строк.</span><span class="sxs-lookup"><span data-stu-id="59387-182">This is because FSI allows you to enter multiple lines.</span></span>  <span data-ttu-id="59387-183">`;;` В конце позволяет FSI знать, когда код будет завершено.</span><span class="sxs-lookup"><span data-stu-id="59387-183">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="59387-184">Объясняется в коде</span><span class="sxs-lookup"><span data-stu-id="59387-184">Explaining the code</span></span>

<span data-ttu-id="59387-185">Если вы не уверены, что фактически выполняет код, вот пошаговые.</span><span class="sxs-lookup"><span data-stu-id="59387-185">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="59387-186">Как видите, `toPigLatin` является функция, которая принимает word в качестве входных данных и преобразует его в Латинской Pig слова.</span><span class="sxs-lookup"><span data-stu-id="59387-186">As you can see, `toPigLatin` is a function which takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span>  <span data-ttu-id="59387-187">Для этого правила таковы:</span><span class="sxs-lookup"><span data-stu-id="59387-187">The rules for this are as follows:</span></span>

<span data-ttu-id="59387-188">Если первый символ, слово, которое начинается с гласные, добавьте в конец слова «yay».</span><span class="sxs-lookup"><span data-stu-id="59387-188">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span>  <span data-ttu-id="59387-189">Если он не начинается с гласные, переместите первого знака в конец слова и «один» добавьте к нему.</span><span class="sxs-lookup"><span data-stu-id="59387-189">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="59387-190">Возможно, вы заметили в FSI следующие:</span><span class="sxs-lookup"><span data-stu-id="59387-190">You may have noticed the following in FSI:</span></span>

```
val toPigLatin : word:string -> string
```

<span data-ttu-id="59387-191">Том, что `toPigLatin` является функция, которая принимает `string` в качестве входного (называется `word`) и возвращает другой `string`.</span><span class="sxs-lookup"><span data-stu-id="59387-191">This states that `toPigLatin` is a function which takes in a `string` as input (called `word`), and returns another `string`.</span></span>  <span data-ttu-id="59387-192">Это называется [сигнатура типа функции](https://fsharpforfunandprofit.com/posts/function-signatures/), основные части F #, который является ключом к пониманию кода F #.</span><span class="sxs-lookup"><span data-stu-id="59387-192">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span>  <span data-ttu-id="59387-193">Можно также заметить при наведении указателя на функцию в Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="59387-193">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="59387-194">В теле функции вы увидите двух отдельных частей:</span><span class="sxs-lookup"><span data-stu-id="59387-194">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="59387-195">Внутренние функции, называемой `isVowel`, которое определяет, если данный символ (`c`) является гласные путем проверки, если он соответствует одному из указанных шаблонов через [соответствие шаблону](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="59387-195">An inner function, called `isVowel`, which determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="59387-196">[ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) Выражение, которое проверяет, если первый символ является гласные и создает значение, возвращаемое из входных символов на основе Если первый символ был гласные или нет:</span><span class="sxs-lookup"><span data-stu-id="59387-196">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression which checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="59387-197">Поток `toPigLatin` таким образом:</span><span class="sxs-lookup"><span data-stu-id="59387-197">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="59387-198">Проверьте, является ли первый символ слова входной гласные.</span><span class="sxs-lookup"><span data-stu-id="59387-198">Check if the first character of the input word is a vowel.</span></span>  <span data-ttu-id="59387-199">Если это так, приложите «yay» до конца слова.</span><span class="sxs-lookup"><span data-stu-id="59387-199">If it is, attach "yay" to the end of the word.</span></span>  <span data-ttu-id="59387-200">В противном случае переместите первого знака в конец слова и «один» добавьте к нему.</span><span class="sxs-lookup"><span data-stu-id="59387-200">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="59387-201">Нет заключительную Обратите внимание, об этом: нет нет явных инструкций для возврата из функции, в отличие от многих других языков здесь.</span><span class="sxs-lookup"><span data-stu-id="59387-201">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span>  <span data-ttu-id="59387-202">Это происходит потому F # основано на выражении, и последнего выражения в теле функции является возвращаемым значением.</span><span class="sxs-lookup"><span data-stu-id="59387-202">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span>  <span data-ttu-id="59387-203">Поскольку `if..then..else` сам по себе является выражением, тело `then` блока или в теле `else` блок будет возвращаться в зависимости от входного значения.</span><span class="sxs-lookup"><span data-stu-id="59387-203">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="59387-204">Перемещение кода скрипта в файле реализации</span><span class="sxs-lookup"><span data-stu-id="59387-204">Moving your script code into the implementation file</span></span>

<span data-ttu-id="59387-205">Предыдущие разделы этой статьи показано общих первым шагом в написании кода F #: функцию начальной записи и выполнить его в интерактивном режиме с FSI.</span><span class="sxs-lookup"><span data-stu-id="59387-205">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span>  <span data-ttu-id="59387-206">Это называется разработка REPL, где REPL означает «Цикла оценки печати чтения».</span><span class="sxs-lookup"><span data-stu-id="59387-206">This is known as REPL-driven development, where REPL stands for "Read-Evaluate-Print Loop".</span></span>  <span data-ttu-id="59387-207">Это отличный способ поэкспериментировать с функциональные возможности, пока не получится, что-либо работы.</span><span class="sxs-lookup"><span data-stu-id="59387-207">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="59387-208">Следующий этап разработки на основе REPL является перемещение рабочий код в файле реализации F #.</span><span class="sxs-lookup"><span data-stu-id="59387-208">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span>  <span data-ttu-id="59387-209">Он затем может компилироваться компилятором F # в сборку, которая может быть выполнена.</span><span class="sxs-lookup"><span data-stu-id="59387-209">It can then be compiled by the F# compiler into an assembly which can be executed.</span></span>

<span data-ttu-id="59387-210">Чтобы начать, откройте `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="59387-210">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="59387-211">Вы заметите, что определенный код уже существует.</span><span class="sxs-lookup"><span data-stu-id="59387-211">You'll notice that some code is already in there.</span></span>  <span data-ttu-id="59387-212">Продолжить и удалить определение класса, но убедитесь в том оставить [ `namespace` ](../language-reference/namespaces.md) объявление в начале.</span><span class="sxs-lookup"><span data-stu-id="59387-212">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="59387-213">Создайте новый [ `module` ](../language-reference/modules.md) вызывается `PigLatin` и скопируйте `toPigLatin` функции в нее таким образом:</span><span class="sxs-lookup"><span data-stu-id="59387-213">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="59387-214">Это один из многих способов, которые можно организовать функций в коде F # и общий подход, если требуется вызов кода из C# или проекты Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="59387-214">This is one of the many ways you can organize functions in F# code, and a common approach if you also want to call your code from C# or Visual Basic projects.</span></span>

<span data-ttu-id="59387-215">Затем откройте `Script.fsx` файл еще раз и удалить весь `toPigLatin` работать, но не забудьте сохранить следующие две строки в файле:</span><span class="sxs-lookup"><span data-stu-id="59387-215">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="59387-216">Первая строка необходим для сценариев для загрузки FSI `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="59387-216">The first line is needed for FSI scripting to load `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="59387-217">Вторая строка — удобный: пропуск он необязателен, но вам будет нужно ввести `open ClassLibraryDemo` в окне с FSI, если вы хотите подключить `ToPigLatin` модуля в область действия.</span><span class="sxs-lookup"><span data-stu-id="59387-217">The second line is a convenience: omitting it is optional, but you will need to type `open ClassLibraryDemo` in an FSI window if you wish to bring the `ToPigLatin` module into scope.</span></span>

<span data-ttu-id="59387-218">Затем в окне «FSI» вызовите функцию с `PigLatin` модуля, определенного ранее:</span><span class="sxs-lookup"><span data-stu-id="59387-218">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="59387-219">Готово!</span><span class="sxs-lookup"><span data-stu-id="59387-219">Success!</span></span>  <span data-ttu-id="59387-220">Получить те же результаты, но теперь загружаются из файла реализации F #.</span><span class="sxs-lookup"><span data-stu-id="59387-220">You get the same results as before, but now loaded from an F# implementation file.</span></span>  <span data-ttu-id="59387-221">Здесь основное отличие заключается в том, что исходными файлами F # компилируются в сборки, которые могут быть выполнены в любом месте, не только в FSI.</span><span class="sxs-lookup"><span data-stu-id="59387-221">The major difference here is that F# source files are compiled into assemblies which can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="59387-222">Сводка</span><span class="sxs-lookup"><span data-stu-id="59387-222">Summary</span></span>

<span data-ttu-id="59387-223">В этой статье вы узнали:</span><span class="sxs-lookup"><span data-stu-id="59387-223">In this article, you've learned:</span></span>

1. <span data-ttu-id="59387-224">Как настроить Visual Studio код с Ionide.</span><span class="sxs-lookup"><span data-stu-id="59387-224">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="59387-225">Создание первого проекта F # с Ionide.</span><span class="sxs-lookup"><span data-stu-id="59387-225">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="59387-226">Инструкции по использованию скриптов F # для создания первой функции F # на Ionide, а затем выполнить его в FSI.</span><span class="sxs-lookup"><span data-stu-id="59387-226">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="59387-227">Как перенести код скрипта F # источника и затем вызвать этот код из FSI.</span><span class="sxs-lookup"><span data-stu-id="59387-227">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="59387-228">Вы теперь способны записывать гораздо большего объема кода F #, используя код Visual Studio и Ionide.</span><span class="sxs-lookup"><span data-stu-id="59387-228">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="59387-229">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="59387-229">Troubleshooting</span></span>

<span data-ttu-id="59387-230">Ниже приведены несколько способов, которые можно устранить определенные неполадки, которые вы можете столкнуться.</span><span class="sxs-lookup"><span data-stu-id="59387-230">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="59387-231">Чтобы получить возможности редактирования кода среды Ionide, F #, файлы должны быть сохранены на диск и внутри папки, который открыт в рабочей области кода Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="59387-231">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="59387-232">Если были внесены изменения в систему или установить необходимые компоненты Ionide с открытым кодом Visual Studio, перезапустите Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="59387-232">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="59387-233">Проверьте, можно использовать компилятор F # и F # interactive из командной строки без полный путь.</span><span class="sxs-lookup"><span data-stu-id="59387-233">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span>  <span data-ttu-id="59387-234">Это можно сделать, введя `fsc` в командной строке компилятора F #, и `fsi` или `fsharpi` для Visual F # средств в Windows и Mono на Mac, Linux, соответственно.</span><span class="sxs-lookup"><span data-stu-id="59387-234">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="59387-235">Если у вас есть недопустимые символы в каталогах проекта, Ionide может не работать.</span><span class="sxs-lookup"><span data-stu-id="59387-235">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="59387-236">Переименование каталогов проекта, если это так.</span><span class="sxs-lookup"><span data-stu-id="59387-236">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="59387-237">Если ни одна из команд Ionide работают, проверьте вашей [сочетания клавиш в Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) для просмотра, если их переопределение случайно.</span><span class="sxs-lookup"><span data-stu-id="59387-237">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="59387-238">Если ни один из указанных выше проблема исправлена проблема Ionide разбивается на компьютере, попробуйте удалить `ionide-fsharp` каталог на компьютере и переустановите пакет подключаемого модуля.</span><span class="sxs-lookup"><span data-stu-id="59387-238">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="59387-239">Ionide является проекта с открытым кодом создаваемый и используемый средством членами сообщества F #.</span><span class="sxs-lookup"><span data-stu-id="59387-239">Ionide is an open source project built and maintained by members of the F# community.</span></span>  <span data-ttu-id="59387-240">Следует сообщить о проблемах и вы можете принять участие в [Ionide VSCode: репозитории FSharp GitHub](https://github.com/ionide/ionide-vscode-fsharp).</span><span class="sxs-lookup"><span data-stu-id="59387-240">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="59387-241">Если имеется проблема в отчет, выполните [инструкции по получению журналов для использования при сообщение о проблеме,](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span><span class="sxs-lookup"><span data-stu-id="59387-241">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="59387-242">Также можно задать для получения дополнительных сведений из Ionide разработчиков и сообщества F # в [Ionide Gitter канала](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="59387-242">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="59387-243">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="59387-243">Next steps</span></span>

<span data-ttu-id="59387-244">Дополнительные сведения о F # и функции языка, извлечь [обзор языка F #](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="59387-244">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="59387-245">См. также</span><span class="sxs-lookup"><span data-stu-id="59387-245">See also</span></span>

[<span data-ttu-id="59387-246">Обзор языка F#</span><span class="sxs-lookup"><span data-stu-id="59387-246">Tour of F#</span></span>](../tour.md)

[<span data-ttu-id="59387-247">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="59387-247">F# Language Reference</span></span>](../language-reference/index.md)

[<span data-ttu-id="59387-248">Функции</span><span class="sxs-lookup"><span data-stu-id="59387-248">Functions</span></span>](../language-reference/functions/index.md)

[<span data-ttu-id="59387-249">Модули</span><span class="sxs-lookup"><span data-stu-id="59387-249">Modules</span></span>](../language-reference/modules.md)

[<span data-ttu-id="59387-250">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="59387-250">Namespaces</span></span>](../language-reference/namespaces.md)

[<span data-ttu-id="59387-251">Ionide VSCode: FSharp</span><span class="sxs-lookup"><span data-stu-id="59387-251">Ionide-VSCode: FSharp</span></span>](https://github.com/ionide/ionide-vscode-fsharp)
