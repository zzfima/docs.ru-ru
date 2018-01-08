---
title: "Начало работы с .NET Core в macOS с помощью Visual Studio для Mac"
description: "В этом разделе рассматривается создание простого консольного приложения с помощью Visual Studio для Mac и .NET Core."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.topic: get-started-article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8902e849-dd17-42c0-8264-cc7ae3927a0c
ms.workload: dotnetcore
ms.openlocfilehash: dad4a66fc943f4232806f7512705fc96decd1904
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="getting-started-with-net-core-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="23b47-104">Начало работы с .NET Core в macOS с помощью Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="23b47-104">Getting started with .NET Core on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="23b47-105">Visual Studio для Mac предоставляет полнофункциональную интегрированную среду для разработки приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="23b47-105">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="23b47-106">В этом разделе рассматривается создание простого консольного приложения с помощью Visual Studio для Mac и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="23b47-106">This topic walks you through building a simple console application using Visual Studio for Mac and .NET Core.</span></span>

> [!NOTE]
> <span data-ttu-id="23b47-107">Ваш отзыв очень важен.</span><span class="sxs-lookup"><span data-stu-id="23b47-107">Your feedback is highly valued.</span></span> <span data-ttu-id="23b47-108">Вы можете отправить отзыв о Visual Studio для Mac команде разработчиков двумя способами:</span><span class="sxs-lookup"><span data-stu-id="23b47-108">There are a two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
> * <span data-ttu-id="23b47-109">В Visual Studio для Mac выберите пункт **Справка** > **Сообщить о проблеме** в меню или элемент **Сообщить о проблеме** на экране приветствия. При этом открывается окно для заполнения отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="23b47-109">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="23b47-110">Отслеживать свои отзывы можно на портале [сообщества разработчиков](https://developercommunity.visualstudio.com/spaces/8/index.html).</span><span class="sxs-lookup"><span data-stu-id="23b47-110">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="23b47-111">Чтобы внести предложение, выберите пункт **Справка** > **Отправить предложение** в меню или элемент **Отправить предложение** на экране приветствия. При этом открывается [веб-страница UserVoice Visual Studio для Mac](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).</span><span class="sxs-lookup"><span data-stu-id="23b47-111">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac UserVoice webpage](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="23b47-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="23b47-112">Prerequisites</span></span>

<span data-ttu-id="23b47-113">См. раздел с перечислением [необходимых компонентов для .NET Core в Mac](../../core/macos-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="23b47-113">See the [Prerequisites for .NET Core on Mac](../../core/macos-prerequisites.md) topic.</span></span>

## <a name="getting-started"></a><span data-ttu-id="23b47-114">Начало работы</span><span class="sxs-lookup"><span data-stu-id="23b47-114">Getting started</span></span>

<span data-ttu-id="23b47-115">Если вы уже установили необходимые компоненты и Visual Studio для Mac, пропустите этот раздел и перейдите к разделу [Создание проекта](#creating-a-project).</span><span class="sxs-lookup"><span data-stu-id="23b47-115">If you've already installed the prerequisites and Visual Studio for Mac, skip this section and proceed to [Creating a project](#creating-a-project).</span></span> <span data-ttu-id="23b47-116">Выполните следующие действия, чтобы установить необходимые компоненты и Visual Studio для Mac:</span><span class="sxs-lookup"><span data-stu-id="23b47-116">Follow these steps to install the prerequisites and Visual Studio for Mac:</span></span>

<span data-ttu-id="23b47-117">Скачайте [установщик Visual Studio для Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="23b47-117">Download the [Visual Studio for Mac installer](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span> <span data-ttu-id="23b47-118">Запустите установщик.</span><span class="sxs-lookup"><span data-stu-id="23b47-118">Run the installer.</span></span> <span data-ttu-id="23b47-119">Прочитайте и примите условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="23b47-119">Read and accept the license agreement.</span></span> <span data-ttu-id="23b47-120">Во время установки у вас будет возможность установить Xamarin — технологию разработки кроссплатформенных мобильных приложений.</span><span class="sxs-lookup"><span data-stu-id="23b47-120">During the install, you're provided the opportunity to install Xamarin, a cross-platform mobile app development technology.</span></span> <span data-ttu-id="23b47-121">Установка Xamarin и связанных ее компонентов является необязательным шагом для разработки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="23b47-121">Installing Xamarin and its related components is optional for .NET Core development.</span></span> <span data-ttu-id="23b47-122">Пошаговые инструкции по установке Visual Studio для Mac см. в разделе [Введение в Visual Studio для Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="23b47-122">For a walk-through of the Visual Studio for Mac install process, see [Introducing Visual Studio for Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/).</span></span> <span data-ttu-id="23b47-123">После завершения установки запустите интегрированную среду разработки Visual Studio для Mac.</span><span class="sxs-lookup"><span data-stu-id="23b47-123">When the install is complete, start the Visual Studio for Mac IDE.</span></span>

## <a name="creating-a-project"></a><span data-ttu-id="23b47-124">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="23b47-124">Creating a project</span></span>

1. <span data-ttu-id="23b47-125">На экране приветствия выберите **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="23b47-125">Select **New Project** on the Welcome screen.</span></span>

   ![Кнопка "Создать проект" на экране приветствия в Visual Studio для Mac](./media/using-on-mac-vs/vsmac1.png)

1. <span data-ttu-id="23b47-127">В узле **.NET Core** диалогового окна **Создание проекта** выберите **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="23b47-127">In the **New Project** dialog, select **App** under the **.NET Core** node.</span></span> <span data-ttu-id="23b47-128">Выберите шаблон **Консольное приложение** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="23b47-128">Select the **Console Application** template followed by **Next**.</span></span>

   ![Список шаблонов для создания проектов](./media/using-on-mac-vs/vsmac2.png)

1. <span data-ttu-id="23b47-130">Введите "HelloWorld" в поле **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="23b47-130">Type "HelloWorld" for the **Project Name**.</span></span> <span data-ttu-id="23b47-131">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="23b47-131">Select **Create**.</span></span>

   ![Диалоговое окно настройки нового консольного приложения](./media/using-on-mac-vs/vsmac3.png)

1. <span data-ttu-id="23b47-133">Подождите, пока восстанавливаются зависимости проекта.</span><span class="sxs-lookup"><span data-stu-id="23b47-133">Wait while the project's dependencies are restored.</span></span> <span data-ttu-id="23b47-134">В проекте присутствует один файл C# — *Program.cs*, который содержит класс `Program` с методом `Main`.</span><span class="sxs-lookup"><span data-stu-id="23b47-134">The project has a single C# file, *Program.cs*, containing a `Program` class with a `Main` method.</span></span> <span data-ttu-id="23b47-135">Оператор `Console.WriteLine` выведет сообщение "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="23b47-135">The `Console.WriteLine` statement will output "Hello World!"</span></span> <span data-ttu-id="23b47-136">в консоли при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="23b47-136">to the console when the app is run.</span></span>

   ![Главное окно с открытым файлом Program.cs](./media/using-on-mac-vs/vsmac4.png)

## <a name="run-the-application"></a><span data-ttu-id="23b47-138">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="23b47-138">Run the application</span></span>

<span data-ttu-id="23b47-139">Запустите приложение в режиме отладки с помощью клавиши <kbd>F5</kbd> или в режиме выпуска с помощью сочетания клавиш <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="23b47-139">Run the app in Debug mode using <kbd>F5</kbd> or in Release mode using <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span></span>

![В области вывода приложения отображается "Hello World!"](./media/using-on-mac-vs/vsmac5.png)

## <a name="next-step"></a><span data-ttu-id="23b47-141">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="23b47-141">Next step</span></span>

<span data-ttu-id="23b47-142">Раздел [Создание полноценного решения .NET Core на macOS с помощью Visual Studio для Mac](using-on-mac-vs-full-solution.md) описывает, как выполнить сборку полноценного решения .NET Core, включающего многоразовую библиотеку и модульное тестирование.</span><span class="sxs-lookup"><span data-stu-id="23b47-142">The [Building a complete .NET Core solution on macOS using Visual Studio for Mac](using-on-mac-vs-full-solution.md) topic shows you how to build a complete .NET Core solution that includes a reusable library and unit testing.</span></span>
