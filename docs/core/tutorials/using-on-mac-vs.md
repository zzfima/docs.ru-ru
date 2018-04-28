---
title: Начало работы с .NET Core в macOS с помощью Visual Studio для Mac
description: В этом разделе рассматривается создание простого консольного приложения с помощью Visual Studio для Mac и .NET Core.
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.topic: get-started-article
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 97a9c62280f09f244028c066a04350a59dd0400d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="getting-started-with-net-core-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="25504-103">Начало работы с .NET Core в macOS с помощью Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="25504-103">Getting started with .NET Core on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="25504-104">Visual Studio для Mac предоставляет полнофункциональную интегрированную среду для разработки приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="25504-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="25504-105">В этом разделе рассматривается создание простого консольного приложения с помощью Visual Studio для Mac и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="25504-105">This topic walks you through building a simple console application using Visual Studio for Mac and .NET Core.</span></span>

> [!NOTE]
> <span data-ttu-id="25504-106">Ваш отзыв очень важен.</span><span class="sxs-lookup"><span data-stu-id="25504-106">Your feedback is highly valued.</span></span> <span data-ttu-id="25504-107">Вы можете отправить отзыв о Visual Studio для Mac команде разработчиков двумя способами:</span><span class="sxs-lookup"><span data-stu-id="25504-107">There are a two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
> * <span data-ttu-id="25504-108">В Visual Studio для Mac выберите пункт **Справка** > **Сообщить о проблеме** в меню или элемент **Сообщить о проблеме** на экране приветствия. При этом открывается окно для заполнения отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="25504-108">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="25504-109">Отслеживать свои отзывы можно на портале [сообщества разработчиков](https://developercommunity.visualstudio.com/spaces/8/index.html).</span><span class="sxs-lookup"><span data-stu-id="25504-109">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="25504-110">Чтобы внести предложение, выберите пункт **Справка** > **Отправить предложение** в меню или элемент **Отправить предложение** на экране приветствия. При этом открывается [веб-страница UserVoice Visual Studio для Mac](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).</span><span class="sxs-lookup"><span data-stu-id="25504-110">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac UserVoice webpage](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="25504-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="25504-111">Prerequisites</span></span>

<span data-ttu-id="25504-112">См. раздел с перечислением [необходимых компонентов для .NET Core в Mac](../../core/macos-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="25504-112">See the [Prerequisites for .NET Core on Mac](../../core/macos-prerequisites.md) topic.</span></span>

## <a name="getting-started"></a><span data-ttu-id="25504-113">Начало работы</span><span class="sxs-lookup"><span data-stu-id="25504-113">Getting started</span></span>

<span data-ttu-id="25504-114">Если вы уже установили необходимые компоненты и Visual Studio для Mac, пропустите этот раздел и перейдите к разделу [Создание проекта](#creating-a-project).</span><span class="sxs-lookup"><span data-stu-id="25504-114">If you've already installed the prerequisites and Visual Studio for Mac, skip this section and proceed to [Creating a project](#creating-a-project).</span></span> <span data-ttu-id="25504-115">Выполните следующие действия, чтобы установить необходимые компоненты и Visual Studio для Mac:</span><span class="sxs-lookup"><span data-stu-id="25504-115">Follow these steps to install the prerequisites and Visual Studio for Mac:</span></span>

<span data-ttu-id="25504-116">Скачайте [установщик Visual Studio для Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="25504-116">Download the [Visual Studio for Mac installer](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span> <span data-ttu-id="25504-117">Запустите установщик.</span><span class="sxs-lookup"><span data-stu-id="25504-117">Run the installer.</span></span> <span data-ttu-id="25504-118">Прочитайте и примите условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="25504-118">Read and accept the license agreement.</span></span> <span data-ttu-id="25504-119">Во время установки у вас будет возможность установить Xamarin — технологию разработки кроссплатформенных мобильных приложений.</span><span class="sxs-lookup"><span data-stu-id="25504-119">During the install, you're provided the opportunity to install Xamarin, a cross-platform mobile app development technology.</span></span> <span data-ttu-id="25504-120">Установка Xamarin и связанных ее компонентов является необязательным шагом для разработки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="25504-120">Installing Xamarin and its related components is optional for .NET Core development.</span></span> <span data-ttu-id="25504-121">Пошаговые инструкции по установке Visual Studio для Mac см. в разделе [Введение в Visual Studio для Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="25504-121">For a walk-through of the Visual Studio for Mac install process, see [Introducing Visual Studio for Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/).</span></span> <span data-ttu-id="25504-122">После завершения установки запустите интегрированную среду разработки Visual Studio для Mac.</span><span class="sxs-lookup"><span data-stu-id="25504-122">When the install is complete, start the Visual Studio for Mac IDE.</span></span>

## <a name="creating-a-project"></a><span data-ttu-id="25504-123">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="25504-123">Creating a project</span></span>

1. <span data-ttu-id="25504-124">На экране приветствия выберите **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="25504-124">Select **New Project** on the Welcome screen.</span></span>

   ![Кнопка "Создать проект" на экране приветствия в Visual Studio для Mac](./media/using-on-mac-vs/vsmac1.png)

1. <span data-ttu-id="25504-126">В узле **.NET Core** диалогового окна **Создание проекта** выберите **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="25504-126">In the **New Project** dialog, select **App** under the **.NET Core** node.</span></span> <span data-ttu-id="25504-127">Выберите шаблон **Консольное приложение** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="25504-127">Select the **Console Application** template followed by **Next**.</span></span>

   ![Список шаблонов для создания проектов](./media/using-on-mac-vs/vsmac2.png)

1. <span data-ttu-id="25504-129">Введите "HelloWorld" в поле **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="25504-129">Type "HelloWorld" for the **Project Name**.</span></span> <span data-ttu-id="25504-130">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="25504-130">Select **Create**.</span></span>

   ![Диалоговое окно настройки нового консольного приложения](./media/using-on-mac-vs/vsmac3.png)

1. <span data-ttu-id="25504-132">Подождите, пока восстанавливаются зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="25504-132">Wait while the project's dependencies are restored.</span></span> <span data-ttu-id="25504-133">В проекте присутствует один файл C# — *Program.cs*, который содержит класс `Program` с методом `Main`.</span><span class="sxs-lookup"><span data-stu-id="25504-133">The project has a single C# file, *Program.cs*, containing a `Program` class with a `Main` method.</span></span> <span data-ttu-id="25504-134">Оператор `Console.WriteLine` выведет сообщение "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="25504-134">The `Console.WriteLine` statement will output "Hello World!"</span></span> <span data-ttu-id="25504-135">в консоли при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="25504-135">to the console when the app is run.</span></span>

   ![Главное окно с открытым файлом Program.cs](./media/using-on-mac-vs/vsmac4.png)

## <a name="run-the-application"></a><span data-ttu-id="25504-137">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="25504-137">Run the application</span></span>

<span data-ttu-id="25504-138">Запустите приложение в режиме отладки с помощью клавиши <kbd>F5</kbd> или в режиме выпуска с помощью сочетания клавиш <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="25504-138">Run the app in Debug mode using <kbd>F5</kbd> or in Release mode using <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span></span>

![В области вывода приложения отображается "Hello World!"](./media/using-on-mac-vs/vsmac5.png)

## <a name="next-step"></a><span data-ttu-id="25504-140">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="25504-140">Next step</span></span>

<span data-ttu-id="25504-141">Раздел [Создание полноценного решения .NET Core на macOS с помощью Visual Studio для Mac](using-on-mac-vs-full-solution.md) описывает, как выполнить сборку полноценного решения .NET Core, включающего многоразовую библиотеку и модульное тестирование.</span><span class="sxs-lookup"><span data-stu-id="25504-141">The [Building a complete .NET Core solution on macOS using Visual Studio for Mac](using-on-mac-vs-full-solution.md) topic shows you how to build a complete .NET Core solution that includes a reusable library and unit testing.</span></span>
