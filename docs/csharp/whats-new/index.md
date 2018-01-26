---
title: "Новые возможности C# — руководство по C#"
description: "Как развивается язык C#"
keywords: "C#, последние функции, новые возможности, Roslyn"
author: BillWagner
ms.author: wiwagn
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.openlocfilehash: 719fbe826b0b115b19067dbaf0d04f14e6534890
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="whats-new-in-c"></a>Новые возможности C# #

Эта страница содержит план новых возможностей в каждой основной версии языка C#. Перейдя по ссылкам ниже, вы сможете получить подробные сведения по основным возможностям, добавленным в каждом выпуске.

> [!IMPORTANT]
> В некоторых возможностях используются типы и методы в *стандартной библиотеке* языка C#, например, обработка исключений. Каждая инструкция и выражение `throw` проверяется, чтобы убедиться, что вызываемый объект является производным от <xref:System.Exception>. Аналогичным образом каждая инструкция `catch` проверяется, чтобы убедиться, что перехваченный тип является производным от <xref:System.Exception>. В каждой версии могут добавляться новые требования. Чтобы использовать новейшие возможности языка в старой среде, может потребоваться установить определенные библиотеки. Эти зависимости описаны на странице для каждой конкретной версии. Дополнительные сведения о связи между языком и библиотекой, а также общие сведения о такой зависимости см. [здесь](relationships-between-language-and-library.md). 


* [C# 7.2](csharp-7-2.md).
    - На этой странице описываются новейшие функции в языке C#. C# 7.2 сейчас доступен в [Visual Studio 2017 версии 15.5](https://www.visualstudio.com/vs/whatsnew/) и в [пакете SDK для .NET Core 2.0](../../core/whats-new/index.md).

* [C# 7.1](csharp-7-1.md).
    - На этой странице описываются функции в C# 7.1. Эти функции были добавлены в [Visual Studio 2017 версии 15.3](https://www.visualstudio.com/vs/whatsnew/) и в [пакет SDK для .NET Core 2.0](../../core/whats-new/index.md).

* [C# 7](csharp-7.md)
    - На этой странице описываются функции, добавленные в C# 7. Они были добавлены в [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/), [.NET Core 1.0](../../core/whats-new/index.md) и более поздние версии.
     
* [C# 6](csharp-6.md)
    - На этой странице описываются функции, добавленные в C# 6. Эти функции доступны в Visual Studio 2015 для разработчиков Windows и в .NET Core 1.0 для разработчиков, исследующих C# на macOS и Linux.

<!--* [C# Interactive](../interactive/index.md): 
    - This page describes C# Interactive, an interactive Read Eval Print Loop (REPL) that you can use to explore the C# language. You can use it to write code interactively and see it execute immediately, without any compile or build step.
-->
* [Кроссплатформенная поддержка](../../core/index.md)
    - Благодаря поддержке .NET Core язык C# работает на многих платформах. Если вы хотите попробовать C# на macOS или на одном из множества поддерживаемых дистрибутивов Linux, узнайте больше о .NET Core.

<!--
- [.NET Compiler Platform SDK](../roslyn/index.md):
    - The .NET Compiler Platform SDK enables you to write code that performs static analysis on C# code. You can use these APIs to find potential errors, or bad practices, suggest fixes, and even implement those fixes.
-->
  
## <a name="previous-versions"></a>Предыдущие версии
Ниже перечислены основные функции, представленные в предыдущих версиях языка C# и Visual Studio .NET.  
  
 * Visual Studio .NET 2013 
     - Эта версия Visual Studio включает исправления ошибок, повышение производительности и предварительные версии технологий платформы компилятора .NET ("Roslyn"), который стал <!--Link to ../roslyn/index.md-->пакетом SDK для платформы компилятора .NET.

 * C# 5, Visual Studio .NET 2012 
     - `Async` / `await`, и атрибуты [сведений о вызывающем объекте](../programming-guide/concepts/caller-information.md).

 * C# 4, Visual Studio .NET 2010 
     - `Dynamic`, [именованные аргументы](../programming-guide/classes-and-structs/named-and-optional-arguments.md), дополнительные параметры и [ковариации и контрвариантность](../programming-guide/concepts/covariance-contravariance/index.md) в универсальных шаблонах.

 * C# 3, Visual Studio .NET 2008 
     - Инициализаторы объектов и коллекций, лямбда-выражения, методы расширений, анонимные типы, автоматические свойства, вывод локального типа `var` и [LINQ](../programming-guide/concepts/linq/index.md).

 * C# 2, Visual Studio .NET 2005 
     - Анонимные методы, универсальные шаблоны, типы, допускающие значение NULL, итераторы и приостановки, классы `static`, ковариации и контрвариантность для делегатов.

 * C# 1.1, Visual Studio .NET 2003 
     - `#line` pragma и комментарии XML-документации.

 * C# 1, Visual Studio .NET 2002 
     - Первый выпуск [C#](../csharp.md).   
