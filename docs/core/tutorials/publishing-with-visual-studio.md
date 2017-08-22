---
title: "Публикация приложения Hello World с помощью Visual Studio 2017"
description: "При публикации создается набор файлов, которые необходимы для запуска приложения."
keywords: ".NET, .NET Core, консольное приложение, публикация, развертывание"
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a19545d3-24af-4a32-9778-cfb5ae938287
ms.translationtype: HT
ms.sourcegitcommit: e0271ba3392ce8861dc916714af8c16d4581ce4f
ms.openlocfilehash: 025e132cd5b6a44e98a1270e24ba6b2f9f12812c
ms.contentlocale: ru-ru
ms.lasthandoff: 08/14/2017

---

# <a name="publish-your-hello-world-application-with-visual-studio-2017"></a>Публикация приложения Hello World с помощью Visual Studio 2017

Изучая руководство [Создание приложения Hello World на C# с помощью .NET Core в Visual Studio 2017](with-visual-studio.md) или [Создание приложения Hello World на Visual Basic с помощью .NET Core в Visual Studio 2017](vb-with-visual-studio.md), вы создали консольное приложение Hello World. В следующем руководстве [Отладка приложения Hello World на C# в Visual Studio 2017](debugging-with-visual-studio.md) вы протестировали его с помощью отладчика Visual Studio. Теперь вы уверены, что приложение работает правильно, и его можно опубликовать для выполнения другими пользователями. При публикации создается набор файлов, которые необходимы для запуска приложения. Чтобы развернуть приложение, скопируйте эти файлы на целевой компьютер.

Действия для публикации и запуска приложения. 

1. Убедитесь, что в Visual Studio настроен режим сборки для версии выпуска. При необходимости измените конфигурацию сборки на панели инструментов, указав конфигурацию **Выпуск** вместо конфигурации **Отладка**.

   ![Панель инструментов Visual Studio](media/publishing-with-visual-studio/toolbar.png)

1. Щелкните проект **HelloWorld** (не решение HelloWorld) правой кнопкой мыши и выберите **Опубликовать**. Также можно выбрать **Публикация HelloWorld** из раздела **Сборка** в главном меню Visual Studio.

   ![Панель инструментов Visual Studio](media/publishing-with-visual-studio/publish1.png)


   ![Панель инструментов Visual Studio](media/publishing-with-visual-studio/publishwindow.png)

1. Откройте окно консоли. Например, в текстовом поле **Введите здесь текст для поиска** на панели задач Windows введите `Command Prompt` (или `cmd` для краткости), а затем откройте окно консоли с помощью приложения **командной строки** или клавиши ВВОД, если оно выделено в результатах поиска.

1. Перейдите к опубликованному приложению в подкаталоге `bin\release\PublishOutput` проекта приложения. Как показано на следующем рисунке, опубликованные выходные данные включают следующие четыре файла:

      * *HelloWorld.deps.json*
      * *HelloWorld.dll*
      * *HelloWorld.pdb* (необязателен для развертывания)
      * *HelloWorld.runtimeconfig.json*

   Файл *HelloWorld.pdb* содержит отладочные символы. Этот файл не нужно распространять вместе с приложением, но желательно сохранить его на случай, если придется выполнять отладку опубликованной версии приложения.

   ![Окно консоли с опубликованными файлами](media/publishing-with-visual-studio/publishedfiles.png)

В ходе публикации создается платформенно-зависимое развертывание. При таком развертывании опубликованное приложение будет выполняться на любой платформе, поддерживаемой .NET Core, при условии, что платформа .NET Core установлена в системе. Пользователи могут запускать приложение командой `dotnet HelloWorld.dll` из окна консоли.

Дополнительные сведения о публикации и развертывании приложений .NET Core см. в статье [Развертывание приложений .NET Core](../../core/deploying/index.md).

