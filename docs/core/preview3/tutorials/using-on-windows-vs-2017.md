---
title: "Getting started with .NET Core on Windows, using Visual Studio 2017 (Приступая к работе с .NET Core в Windows с помощью Visual Studio 2017)"
description: "Getting started with .NET Core on Windows, using Visual Studio 2017 (Приступая к работе с .NET Core в Windows с помощью Visual Studio 2017)"
keywords: .NET, .NET Core
author: bleroy
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: d743134a-08a3-4ff6-aab7-49f71f0568c3
translationtype: Human Translation
ms.sourcegitcommit: 71eab6216e116b99927dfeaa8ce3cf70bcc08a5e
ms.openlocfilehash: 4437f44523bcc4e8517de5b6be42a63439f817d7

---

# <a name="getting-started-with-net-core-on-windows-using-visual-studio-2017"></a>Getting started with .NET Core on Windows, using Visual Studio 2017 (Приступая к работе с .NET Core в Windows с помощью Visual Studio 2017)

Авторы: [Bertrand Le Roy](https://github.com/bleroy) (Бертран ле Рой) и [Phillip Carter](https://github.com/cartermp) (Филипп Картер)

Visual Studio 2017 предоставляет полнофункциональную среду для разработки приложений .NET Core. В этом документе описаны шаги по созданию очень простого консольного приложения с помощью Visual Studio и .NET Core.

## <a name="prerequisites"></a>Предварительные требования

Чтобы обновить среду, выполните инструкции на [странице с описанием предварительных требований](../windows-prerequisites.md).

## <a name="getting-started"></a>Начало работы

Чтобы настроить Visual Studio 2017 для разработки консольного приложения .NET Core, выполните следующие действия.

1. Откройте Visual Studio, а затем в меню **Файл** выберите пункты **Создать** и **Проект**.

2. В диалоговом окне **Новый проект** в списке **Шаблоны** разверните узел **Visual C#** и выберите элемент **.NET Core**. Вы должны увидеть три-четыре шаблона проектов для **консольного приложения (.NET Core)**, **проекта модульного теста (.NET Core)**, **библиотеки классов (.NET Core)** и **веб-приложения ASP.NET (.NET Core)**. Выберите **Консольное приложение (.NET Core)**, введите имя проекта, выберите папку и нажмите кнопку "ОК".

  ![Новый проект: консольное приложение](media/new-project-console-app.png)

3. Полученный в результате проект будет содержать один файл, созданный на языке C#, который выводит на консоль фразу "Hello World".

  ![Проект консольного приложения](media/console-app-solution.png)

Это приложение можно запустить в режиме отладки с помощью клавиши F5 или в режиме выпуска с помощью сочетания клавиш CTRL+F5. Можно также задать точки останова для прерывания выполнения и проверки переменных или приступить к написанию более интересного кода.

Удачного программирования!

## <a name="what-to-do-next"></a>Дальнейшие действия

После этого простого вступления вы, вероятно, захотите узнать, как создавать более сложные решения с многократно используемыми библиотеками и тестами. Соответствующие инструкции вы найдете в статье [Building a complete .NET Core solution on Windows, using Visual Studio 2017](using-on-windows-vs-2017-full-solution.md) (Создание полного решения .NET Core в Windows с помощью Visual Studio 2017).



<!--HONumber=Nov16_HO3-->


