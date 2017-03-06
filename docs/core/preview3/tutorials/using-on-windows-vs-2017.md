---
title: "Приступая к работе с .NET Core в Windows при помощи Visual Studio 2017 | Microsoft Docs"
description: "Getting started with .NET Core on Windows, using Visual Studio 2017 (Приступая к работе с .NET Core в Windows с помощью Visual Studio 2017)"
keywords: .NET, .NET Core
author: bleroy
ms.author: mairaw
ms.date: 01/18/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 613c65d0-f773-41b8-ba0e-83f6a82a0b30
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: cc2c2853bc31e161d1fe0de4edc71d15281c6d24

---

# <a name="getting-started-with-net-core-on-windows-using-visual-studio-2017-net-core-tools-rc4"></a>Начало работы с .NET Core в Windows с помощью Visual Studio 2017 (версия-кандидат 4 средств .NET Core)

> [!WARNING]
> Эта статья применима к версии-кандидату 4 средств .NET Core. Информацию об инструментах .NET Core (предварительная версия 2) для Visual Studio 2015 см. в статье [Начало работы с .NET Core в Windows с помощью Visual Studio 2015](../../tutorials/using-on-windows.md).

Visual Studio 2017 предоставляет полнофункциональную среду для разработки приложений .NET Core. В этом документе описаны шаги по созданию очень простого консольного приложения с помощью Visual Studio и .NET Core.

## <a name="prerequisites"></a>Предварительные требования

Чтобы обновить среду, выполните инструкции на [странице с описанием предварительных требований](../windows-prerequisites.md).

## <a name="getting-started"></a>Начало работы

Чтобы настроить Visual Studio 2017 для разработки консольного приложения .NET Core, выполните следующие действия.

1. Откройте Visual Studio, а затем в меню **Файл** выберите пункты **Создать** и **Проект**.

2. В диалоговом окне **Новый проект** в списке **Шаблоны** разверните узел **Visual C#** и выберите элемент **.NET Core**. Вы должны увидеть пять шаблонов проектов для **консольного приложения (.NET Core)**, **библиотеки классов (.NET Standard)**, **тестового проекта xUnit (.NET Core)**, **библиотеки классов (.NET Core)** и **веб-приложения на ASP.NET Core (.NET Core)**. Выберите **Консольное приложение (.NET Core)**, введите имя проекта, выберите папку и нажмите кнопку "ОК".

  ![Новый проект: консольное приложение](media/new-project-console-app.png)

3. Полученный в результате проект будет содержать один файл, созданный на языке C#, который выводит на консоль фразу "Hello World".

  ![Проект консольного приложения](media/console-app-solution.png)

Это приложение можно запустить в режиме отладки с помощью клавиши F5 или в режиме выпуска с помощью сочетания клавиш CTRL+F5. Можно также задать точки останова для прерывания выполнения и проверки переменных или приступить к написанию более интересного кода.

Удачного программирования!

## <a name="next-steps"></a>Дальнейшие действия

После этого простого вступления вы, вероятно, захотите узнать, как создавать более сложные решения с многократно используемыми библиотеками и тестами. Соответствующие инструкции вы найдете в статье [Building a complete .NET Core solution on Windows, using Visual Studio 2017](using-on-windows-vs-2017-full-solution.md) (Создание полного решения .NET Core в Windows с помощью Visual Studio 2017).



<!--HONumber=Feb17_HO2-->


