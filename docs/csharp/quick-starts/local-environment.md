---
title: Руководство по локальной среде. Краткие руководства по локальной разработке на C#
description: Это краткое руководство содержит основные сведения о выполнении кратких руководств в локальной среде.
author: billwagner
ms.topic: article
ms.date: 12/07/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: ec70b6bca55d370d90e912793cfec82a45141c51
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="local-environment"></a>Локальная среда

Чтобы выполнить локально краткое руководство, сначала нужно настроить среду разработки на локальном компьютере.
В руководстве по [началу работы с .NET за 10 минут](https://www.microsoft.com/net/core) содержатся инструкции по настройке локальной среды разработки на компьютерах Mac, Windows или Linux.

Кроме того, вы можете установить [пакет SDK для .NET Core](http://dot.net/core) и [Visual Studio Code](https://code.visualstudio.com/).

## <a name="basic-application-development-flow"></a>Основная последовательность разработки приложения

Чтобы создать приложения, выполните команду [`dotnet new`](../../core/tools/dotnet-new.md). Эта команда создает файлы и ресурсы, необходимые для приложения. Во всех кратких приложениях используется тип приложения `console`.

Выполните команду [`dotnet build`](../../core/tools/dotnet-build.md), чтобы создать исполняемый файл. Затем запустите исполняемый файла с помощью команды [`dotnet run`](../../core/tools/dotnet-run.md).

## <a name="pick-your-quickstart"></a>Выбор краткого руководства

Начните с любого из следующих кратких руководств.

## <a name="numbers-in-cnumbers-in-csharp-localmd"></a>[Числа в C#](numbers-in-csharp-local.md)

В кратком руководстве [по числам в C#](numbers-in-csharp-local.md) вы узнаете, каким образом на компьютере хранятся числа и как выполнять вычисления с их разными типами. Вы ознакомитесь с основами округления и научитесь выполнять математические вычисления с помощью C#. 

Это руководство предполагает, что вы выполнили урок [Hello World](hello-world.yml).

## <a name="branches-and-loopsbranches-and-loops-localmd"></a>[Ветви и циклы](branches-and-loops-local.md)

В кратком руководстве [Ветви и циклы](branches-and-loops-local.md) представлены общие принципы организации ветвления кода в зависимости от значений, хранящихся в переменных. Вы узнаете, что такое поток управления, являющийся основой принятия решений и выбора различных действий в программах. 

Это руководство предполагает, что вы выполнили уроки [Hello World](hello-world.yml) и [Числа в C#](numbers-in-csharp-local.md).

## <a name="string-interpolationinterpolated-strings-localmd"></a>[Интерполяция строк](interpolated-strings-local.md)

Краткое руководство [Интерполяция строк](interpolated-strings-local.md) покажет вам, как вставлять значения в строку. Вы узнаете, как создать интерполированную строку с внедренными выражениями C# и как управлять текстовым представлением результатов выражений в итоговой строке.

Это руководство предполагает, что вы прошли уроки [Hello World](hello-world.yml), [Числа в C#](numbers-in-csharp-local.md), а также [Ветви и циклы](branches-and-loops-local.md).

## <a name="list-collectionarrays-and-collectionsmd"></a>[Коллекция списков](arrays-and-collections.md)

Занятие [Коллекция списков](arrays-and-collections.md) содержит обзор типа "Коллекция списков", в котором хранятся последовательности данных. Вы узнаете, как добавлять и удалять элементы, выполнять их поиск и сортировать списки. Вы ознакомитесь с различными типами списков. 

Это руководство предполагает, что вы прошли уроки, перечисленные выше.

## <a name="introduction-to-classesintroduction-to-classesmd"></a>[Общие сведения о классах](introduction-to-classes.md)

Это заключительное краткое руководство выполняется только на компьютере с использованием локальной среды разработки и .NET Core.
Вы создадите консольное приложение и изучите основные объектно-ориентированные функции языка C#.
