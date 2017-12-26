---
title: "Краткое руководство: использование C# в локальной среде"
description: "Это краткое руководство содержит основные сведения о выполнении кратких руководств в локальной среде."
author: billwagner
ms.author: wiwagn
ms.date: 12/07/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 4cbe66df4173854870dd6ac68c52e8c87c46c1f6
ms.sourcegitcommit: 9bee08539b1886c9d57fa3d5bd8a58dfdd7cad94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2017
---
# <a name="local-environment"></a>Локальная среда

Чтобы выполнить локально краткое руководство, сначала нужно настроить среду разработки на локальном компьютере.
В руководстве по [началу работы с .NET за 10 минут](https://www.microsoft.com/net/core) содержатся инструкции по настройке локальной среды разработки на компьютерах Mac, Windows или Linux.

Кроме того, вы можете установить [пакет SDK для .NET Core](http://dot.net/core) и [Visual Studio Code](https://code.visualstudio.com/).

## <a name="basic-application-development-flow"></a>Основная последовательность разработки приложения

Чтобы создать приложения, выполните команду [`dotnet new`](../../core/tools/dotnet-new.md). Эта команда создает файлы и ресурсы, необходимые для приложения. Во всех кратких приложениях используется тип приложения `console`.

Выполните команду [`dotnet build`](../../core/tools/dotnet-build.md), чтобы создать исполняемый файл. Затем запустите исполняемый файла с помощью команды [`dotnet run`](../../core/tools/dotnet-run.md).

## <a name="pick-your-quickstart"></a>Выбор краткого руководства

Начните с любого из следующих кратких руководств:

## <a name="numbers-in-cnumbers-in-csharp-localmd"></a>[Числа в C#](numbers-in-csharp-local.md)

В кратком руководстве [Числа в C#](numbers-in-csharp-local.md) вы узнаете, каким образом компьютер хранит числа и как выполнять вычисления с их различными типами. Вы ознакомитесь с основами округления и научитесь выполнять математические вычисления с помощью C#. 

В нем предполагается, что вы изучили руководство [Hello world](hello-world.yml).

## <a name="branches-and-loopsbranches-and-loops-localmd"></a>[Ветви и циклы](branches-and-loops-local.md)

Краткое руководство [Ветви и циклы](branches-and-loops-local.md) покажет вам общие принципы выбора различных путей выполнения кода в зависимости от значений, хранящихся в переменных. Вы узнаете, что такое поток управления, являющийся основой принятия решений и выбора различных действий в программах. 

В этом занятии начального уровня предполагается, что вы изучили руководства [Hello World](hello-world.yml) и [Числа в C#](numbers-in-csharp-local.md).

## <a name="list-collectionarrays-and-collectionsmd"></a>[Коллекция списков](arrays-and-collections.md)

Занятие [Коллекция списков](arrays-and-collections.md) содержит обзор типа "Коллекция списков", в котором хранятся последовательности данных. Вы узнаете, как добавлять и удалять элементы, выполнять их поиск и сортировать списки. Вы ознакомитесь с различными типами списков. 

В этом кратком руководстве начального уровня предполагается, что вы изучили краткие руководства, перечисленные выше.

## <a name="introduction-to-classesintroduction-to-classesmd"></a>[Общие сведения о классах](introduction-to-classes.md)

Это заключительное краткое руководство выполняется только на компьютере с использованием локальной среды разработки и .NET Core.
Вы создадите консольное приложение и изучите основные объектно-ориентированные функции языка C#.
