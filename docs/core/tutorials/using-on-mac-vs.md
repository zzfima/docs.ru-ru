---
title: Начало работы с .NET Core в macOS с помощью Visual Studio для Mac
description: В этом разделе рассматривается создание простого консольного приложения с помощью Visual Studio для Mac и .NET Core.
author: guardrex
ms.date: 06/12/2017
ms.custom: seodec18
ms.openlocfilehash: 471bdfdaa10b2d66c19177ae36b8bd18ce19e468
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169577"
---
# <a name="getting-started-with-net-core-on-macos-using-visual-studio-for-mac"></a>Начало работы с .NET Core в macOS с помощью Visual Studio для Mac

Visual Studio для Mac предоставляет полнофункциональную интегрированную среду для разработки приложений .NET Core. В этом разделе рассматривается создание простого консольного приложения с помощью Visual Studio для Mac и .NET Core.

> [!NOTE]
> Ваш отзыв очень важен. Вы можете отправить отзыв о Visual Studio для Mac команде разработчиков двумя способами.
> * В Visual Studio для Mac выберите пункт **Справка** > **Сообщить о проблеме** в меню или элемент **Сообщить о проблеме** на экране приветствия. При этом открывается окно для заполнения отчета об ошибках. Отслеживать свои отзывы можно на портале [сообщества разработчиков](https://developercommunity.visualstudio.com/spaces/8/index.html).
> * Чтобы внести предложение, выберите пункт **Справка** > **Отправить предложение** в меню или элемент **Отправить предложение** на экране приветствия. При этом открывается [веб-страница сообщества разработчиков Visual Studio для Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).

## <a name="prerequisites"></a>Предварительные требования

См. раздел с перечислением [необходимых компонентов для .NET Core в Mac](../../core/macos-prerequisites.md).

## <a name="getting-started"></a>Начало работы

Если вы уже установили необходимые компоненты и Visual Studio для Mac, пропустите этот раздел и перейдите к разделу [Создание проекта](#creating-a-project). Выполните следующие действия, чтобы установить необходимые компоненты и Visual Studio для Mac:

Скачайте [установщик Visual Studio для Mac](https://visualstudio.microsoft.com/vs/visual-studio-mac/). Запустите установщик. Прочитайте и примите условия лицензионного соглашения. Во время установки у вас будет возможность установить Xamarin — технологию разработки кроссплатформенных мобильных приложений. Установка Xamarin и связанных ее компонентов является необязательным шагом для разработки .NET Core. Пошаговые инструкции по установке Visual Studio для Mac см. в разделе [Введение в Visual Studio для Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/). После завершения установки запустите интегрированную среду разработки Visual Studio для Mac.

## <a name="creating-a-project"></a>Создание проекта

1. На экране приветствия выберите **Создать проект**.

   ![Кнопка "Создать проект" на экране приветствия в Visual Studio для Mac](./media/using-on-mac-vs/visual-studio-mac-new-project.png)

1. В узле **.NET Core** диалогового окна **Создание проекта** выберите **Приложение**. Выберите шаблон **Консольное приложение** и нажмите кнопку **Далее**.

   ![Список шаблонов для создания проектов](./media/using-on-mac-vs/visual-studio-mac-new-dialog.png)

1. Введите "HelloWorld" в поле **Имя проекта**. Выберите **Создать**.

   ![Диалоговое окно настройки нового консольного приложения](./media/using-on-mac-vs/visual-studio-mac-new-options.png)

1. Подождите, пока восстанавливаются зависимости проекта. В проекте присутствует один файл C# — *Program.cs*, который содержит класс `Program` с методом `Main`. Оператор `Console.WriteLine` выведет сообщение "Hello World!" в консоли при запуске приложения.

   ![Главное окно с открытым файлом Program.cs](./media/using-on-mac-vs/visual-studio-mac-editor.png)

## <a name="run-the-application"></a>Запуск приложения

Запустите приложение в режиме отладки с помощью клавиши <kbd>F5</kbd> или в режиме выпуска с помощью сочетания клавиш <kbd>CTRL</kbd>+<kbd>F5</kbd>.

![В области вывода приложения отображается "Hello World!"](./media/using-on-mac-vs/visual-studio-mac-output.png)

## <a name="next-step"></a>Дальнейшие действия

Раздел [Создание полноценного решения .NET Core на macOS с помощью Visual Studio для Mac](using-on-mac-vs-full-solution.md) описывает, как выполнить сборку полноценного решения .NET Core, включающего многоразовую библиотеку и модульное тестирование.
