---
title: "Начало работы с .NET Core в macOS с помощью Visual Studio для Mac | Документы Майкрософт"
description: "В этом разделе рассматривается создание простого консольного приложения с помощью Visual Studio для Mac и .NET Core."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 03/16/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8902e849-dd17-42c0-8264-cc7ae3927a0c
translationtype: Human Translation
ms.sourcegitcommit: ff143583ba62fc1d82561e739a75107e50ebee88
ms.openlocfilehash: ed8787d72647f18544bde8ed721cf37f31fbb5fe
ms.lasthandoff: 03/20/2017

---

# <a name="getting-started-with-net-core-on-macos-using-visual-studio-for-mac"></a>Начало работы с .NET Core в macOS с помощью Visual Studio для Mac

Visual Studio для Mac предоставляет полнофункциональную интегрированную среду для разработки приложений .NET Core. В этом разделе рассматривается создание простого консольного приложения с помощью Visual Studio для Mac и .NET Core.

> [!NOTE]
> Программное обеспечение Visual Studio для Mac находится на этапе предварительной версии. Как и в случае со всеми предварительными версиями продуктов Майкрософт, нам крайне важно узнать ваше мнение. Вы можете отправить отзыв о Visual Studio для Mac команде разработчиков двумя способами:
> * В Visual Studio для Mac выберите пункт **Справка > Сообщить о проблеме** в меню или элемент **Сообщить о проблеме** на экране приветствия. При этом открывается окно для заполнения отчета об ошибках.
> * Чтобы внести предложение, выберите пункт **Справка > Отправить предложение** в меню или элемент **Отправить предложение** на экране приветствия. При этом открывается [веб-страница UserVoice Visual Studio для Mac](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).

## <a name="prerequisites"></a>Предварительные требования

[.NET Core и OpenSSL](https://www.microsoft.com/net/core#macos)

Дополнительные сведения о необходимых компонентах см. в разделе [Необходимые компоненты для .NET Core на Mac](../../core/macos-prerequisites.md).

## <a name="getting-started"></a>Начало работы

Если вы уже установили необходимые компоненты и Visual Studio для Mac, пропустите этот раздел и перейдите к разделу [Создание проекта](#creating-a-project). Выполните следующие действия, чтобы установить необходимые компоненты и Visual Studio для Mac:

1. Скачайте и установите [.NET Core и OpenSSL](https://www.microsoft.com/net/core#macos).

1. Скачайте [установщик Visual Studio для Mac](https://www.visualstudio.com/vs/visual-studio-mac/). Запустите установщик. Прочитайте и примите условия лицензионного соглашения. Во время установки у вас будет возможность установить Xamarin — технологию разработки кроссплатформенных мобильных приложений. Установка Xamarin и связанных ее компонентов является необязательным шагом для разработки .NET Core. Пошаговые инструкции по установке Visual Studio для Mac см. в разделе [Введение в Visual Studio для Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/). После завершения установки запустите интегрированную среду разработки Visual Studio для Mac.

## <a name="creating-a-project"></a>Создание проекта

1. На экране приветствия выберите **Создать проект**.

   ![Кнопка "Создать проект" на экране приветствия в Visual Studio для Mac](./media/using-on-mac-vs/vsmac1.png)

1. В узле **.NET Core** диалогового окна **Создание проекта** выберите **Приложение**. Выберите шаблон **Консольное приложение** и нажмите кнопку **Далее**.

   ![Список шаблонов для создания проектов](./media/using-on-mac-vs/vsmac2.png)

1. Введите "HelloWorld" в поле **Имя проекта**. Выберите **Создать**.

   ![Диалоговое окно настройки нового консольного приложения](./media/using-on-mac-vs/vsmac3.png)

1. Подождите, пока восстанавливаются зависимости проекта. В проекте присутствует один файл C# — *Program.cs*, который содержит класс `Program` с методом `Main`. Оператор `Console.WriteLine` выведет сообщение "Hello World!" в консоли при запуске приложения.

   ![Главное окно с открытым файлом Program.cs](./media/using-on-mac-vs/vsmac4.png)

## <a name="run-the-application"></a>Запуск приложения

Запустите приложение в режиме отладки с помощью клавиши <kbd>F5</kbd> или в режиме выпуска с помощью сочетания клавиш <kbd>CTRL</kbd>+<kbd>F5</kbd>.

![В области вывода приложения отображается "Hello World!"](./media/using-on-mac-vs/vsmac5.png)

## <a name="next-step"></a>Дальнейшие действия

Раздел [Создание полноценного решения .NET Core на macOS с помощью Visual Studio для Mac](using-on-mac-vs-full-solution.md) описывает, как выполнить сборку полноценного решения .NET Core, включающего многоразовую библиотеку и модульное тестирование.

