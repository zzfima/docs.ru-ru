---
title: Начало работы с .NET Core в macOS с помощью Visual Studio для Mac
description: В этом разделе рассматривается создание простого консольного приложения с помощью Visual Studio для Mac и .NET Core.
author: mairaw
ms.date: 07/11/2019
ms.custom: seodec18
ms.openlocfilehash: feaed88e902080c5c3b07578b78f8437489a690c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428587"
---
# <a name="get-started-with-net-core-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="ee277-103">Начало работы с .NET Core в macOS с помощью Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="ee277-103">Get started with .NET Core on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="ee277-104">Visual Studio для Mac предоставляет полнофункциональную интегрированную среду для разработки приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ee277-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="ee277-105">В этом разделе рассматривается создание простого консольного приложения с помощью Visual Studio для Mac и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ee277-105">This topic walks you through building a simple console application using Visual Studio for Mac and .NET Core.</span></span>

> [!NOTE]
> <span data-ttu-id="ee277-106">Ваш отзыв очень важен.</span><span class="sxs-lookup"><span data-stu-id="ee277-106">Your feedback is highly valued.</span></span> <span data-ttu-id="ee277-107">Вы можете отправить отзыв о Visual Studio для Mac команде разработчиков двумя способами.</span><span class="sxs-lookup"><span data-stu-id="ee277-107">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> * <span data-ttu-id="ee277-108">В Visual Studio для Mac выберите пункт **Справка** > **Сообщить о проблеме** в меню или элемент **Сообщить о проблеме** на экране приветствия. При этом открывается окно для заполнения отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="ee277-108">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="ee277-109">Отслеживать свои отзывы можно на портале [сообщества разработчиков](https://developercommunity.visualstudio.com/spaces/8/index.html).</span><span class="sxs-lookup"><span data-stu-id="ee277-109">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="ee277-110">Чтобы внести предложение, выберите пункт **Справка** > **Отправить предложение** в меню или элемент **Отправить предложение** на экране приветствия. При этом открывается [веб-страница сообщества разработчиков Visual Studio для Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span><span class="sxs-lookup"><span data-stu-id="ee277-110">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ee277-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="ee277-111">Prerequisites</span></span>

<span data-ttu-id="ee277-112">См. статью [Зависимости и требования для .NET Core](../install/dependencies.md?tabs=netcore30&pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="ee277-112">See the [.NET Core dependencies and requirements](../install/dependencies.md?tabs=netcore30&pivots=os-macos) topic.</span></span>

<span data-ttu-id="ee277-113">Просмотрите статью о [поддержке .NET Core](/visualstudio/mac/net-core-support) и убедитесь в том, что вы используете поддерживаемую версию .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ee277-113">Check the [.NET Core Support](/visualstudio/mac/net-core-support) article to ensure you're using a supported version of .NET Core.</span></span>

## <a name="get-started"></a><span data-ttu-id="ee277-114">Начало работы</span><span class="sxs-lookup"><span data-stu-id="ee277-114">Get started</span></span>

<span data-ttu-id="ee277-115">Если вы уже установили необходимые компоненты и Visual Studio для Mac, пропустите этот раздел и перейдите к разделу [Создание проекта](#creating-a-project).</span><span class="sxs-lookup"><span data-stu-id="ee277-115">If you've already installed the prerequisites and Visual Studio for Mac, skip this section and proceed to [Creating a project](#creating-a-project).</span></span> <span data-ttu-id="ee277-116">Выполните следующие действия, чтобы установить необходимые компоненты и Visual Studio для Mac:</span><span class="sxs-lookup"><span data-stu-id="ee277-116">Follow these steps to install the prerequisites and Visual Studio for Mac:</span></span>

<span data-ttu-id="ee277-117">Скачайте [установщик Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="ee277-117">Download the [Visual Studio for Mac installer](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="ee277-118">Запустите установщик.</span><span class="sxs-lookup"><span data-stu-id="ee277-118">Run the installer.</span></span> <span data-ttu-id="ee277-119">Прочитайте и примите условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="ee277-119">Read and accept the license agreement.</span></span> <span data-ttu-id="ee277-120">Во время установки выберите вариант с установкой .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ee277-120">During the install, select the option to install .NET Core.</span></span> <span data-ttu-id="ee277-121">У вас будет возможность установить Xamarin — технологию разработки кроссплатформенных мобильных приложений.</span><span class="sxs-lookup"><span data-stu-id="ee277-121">You're provided the opportunity to install Xamarin, a cross-platform mobile app development technology.</span></span> <span data-ttu-id="ee277-122">Установка Xamarin и связанных ее компонентов является необязательным шагом для разработки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ee277-122">Installing Xamarin and its related components is optional for .NET Core development.</span></span> <span data-ttu-id="ee277-123">Пошаговые инструкции по установке Visual Studio для Mac см. в документации по [Visual Studio для Mac](/visualstudio/mac/).</span><span class="sxs-lookup"><span data-stu-id="ee277-123">For a walk-through of the Visual Studio for Mac install process, see [Visual Studio for Mac documentation](/visualstudio/mac/).</span></span> <span data-ttu-id="ee277-124">После завершения установки запустите интегрированную среду разработки Visual Studio для Mac.</span><span class="sxs-lookup"><span data-stu-id="ee277-124">When the install is complete, start the Visual Studio for Mac IDE.</span></span>

## <a name="creating-a-project"></a><span data-ttu-id="ee277-125">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="ee277-125">Creating a project</span></span>

1. <span data-ttu-id="ee277-126">Нажмите кнопку **Создать** в окне запуска.</span><span class="sxs-lookup"><span data-stu-id="ee277-126">Select **New** on the Start Window.</span></span>

   ![Кнопка "Создать" на экране запуска Visual Studio для Mac](./media/using-on-mac-vs/visual-studio-mac-new-project.png)

1. <span data-ttu-id="ee277-128">В узле **.NET Core** диалогового окна **Создание проекта** выберите **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="ee277-128">In the **New Project** dialog, select **App** under the **.NET Core** node.</span></span> <span data-ttu-id="ee277-129">Выберите шаблон **Консольное приложение** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ee277-129">Select the **Console Application** template followed by **Next**.</span></span>

   ![Список шаблонов для создания проектов](./media/using-on-mac-vs/visual-studio-mac-new-dialog.png)

1. <span data-ttu-id="ee277-131">Если у вас установлено несколько версий .NET Core, выберите нужную версию для своего проекта.</span><span class="sxs-lookup"><span data-stu-id="ee277-131">If you have more than one version of .NET Core installed, select the target framework for your project.</span></span>

1. <span data-ttu-id="ee277-132">Введите "HelloWorld" в поле **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="ee277-132">Type "HelloWorld" for the **Project Name**.</span></span> <span data-ttu-id="ee277-133">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="ee277-133">Select **Create**.</span></span>

   ![Диалоговое окно настройки нового консольного приложения](./media/using-on-mac-vs/visual-studio-mac-new-options.png)

1. <span data-ttu-id="ee277-135">Подождите, пока восстанавливаются зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="ee277-135">Wait while the project's dependencies are restored.</span></span> <span data-ttu-id="ee277-136">В проекте присутствует один файл C# — *Program.cs*, который содержит класс `Program` с методом `Main`.</span><span class="sxs-lookup"><span data-stu-id="ee277-136">The project has a single C# file, *Program.cs*, containing a `Program` class with a `Main` method.</span></span> <span data-ttu-id="ee277-137">Оператор `Console.WriteLine` выведет сообщение "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="ee277-137">The `Console.WriteLine` statement will output "Hello World!"</span></span> <span data-ttu-id="ee277-138">в консоли при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="ee277-138">to the console when the app is run.</span></span>

   ![Главное окно с открытым файлом Program.cs](./media/using-on-mac-vs/visual-studio-mac-editor.png)

## <a name="run-the-application"></a><span data-ttu-id="ee277-140">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="ee277-140">Run the application</span></span>

<span data-ttu-id="ee277-141">Запустите приложение в режиме отладки, нажав клавиши ⌘ ↵ (Command + ВВОД), или в режиме выпуска, нажав клавиши ⌥ ⌘ ↵ (Option + Command + ВВОД).</span><span class="sxs-lookup"><span data-stu-id="ee277-141">Run the app in Debug mode using ⌘ ↵ (command + enter) or in Release mode using ⌥ ⌘ ↵ (option + command + enter).</span></span>

![В области вывода приложения отображается "Hello World!"](./media/using-on-mac-vs/visual-studio-mac-output.png)

## <a name="next-step"></a><span data-ttu-id="ee277-143">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="ee277-143">Next step</span></span>

<span data-ttu-id="ee277-144">Раздел [Создание полноценного решения .NET Core на macOS с помощью Visual Studio для Mac](using-on-mac-vs-full-solution.md) описывает, как выполнить сборку полноценного решения .NET Core, включающего многоразовую библиотеку и модульное тестирование.</span><span class="sxs-lookup"><span data-stu-id="ee277-144">The [Building a complete .NET Core solution on macOS using Visual Studio for Mac](using-on-mac-vs-full-solution.md) topic shows you how to build a complete .NET Core solution that includes a reusable library and unit testing.</span></span>
