---
title: "Dynamic Source Code Generation and Compilation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Code Document Object Model"
  - "System.CodeDom namespace"
  - "language-independent source code modeling"
  - "CodeDOM"
  - "multiple languages supported by CodeDOM"
  - "source code in multiple languages"
  - "languages, multiple language support by CodeDOM"
ms.assetid: d077a3e8-bd81-4bdf-b6a3-323857ea30fb
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Dynamic Source Code Generation and Compilation
В среду .NET Framework включен механизм, который называется моделью объектов документов кода \(CodeDOM\), позволяющий разработчикам программ, генерирующих исходный код, создавать код на нескольких языках программирования во время выполнения на основе единой модели, предоставляющей код для визуализации.  
  
 Для представления исходного кода элементы CodeDOM связываются друг с другом, образуя структуру данных, известную как граф CodeDOM, которая моделирует структуру некоторого исходного кода.  
  
 Пространство имен `System.CodeDom` определяет типы, с помощью которых логическая структура исходного кода может быть представлена независимо от конкретного языка программирования.  Пространство имен `System.CodeDom.Compiler` определяет типы, используемые для генерации исходного кода из графов CodeDOM и для управления компиляцией исходного кода на поддерживаемых языках.  Набор поддерживаемых языков может быть расширен разработчиками или поставщиками компиляторов.  
  
 Независимое от языка моделирование исходного кода может быть полезно, если программа должна создавать исходный код для модели программы на нескольких языках или если конечный язык заранее не определен.  Например, некоторые конструкторы используют модель CodeDOM в качестве интерфейса абстракции от языка для получения исходного кода на требуемом языке программирования, если имеется поддержка CodeDOM для этого языка.  
  
 В платформе .NET Framework содержатся генераторы кода и компиляторы для языков [C\#](frlrfMicrosoftCSharpCSharpCodeProviderClassTopic), [JScript](frlrfMicrosoftJScriptJScriptCodeProviderClassTopic) и [Visual Basic](frlrfMicrosoftVisualBasicVBCodeProviderClassTopic).  
  
## В этом подразделе  
 [Использование CodeDOM](../../../docs/framework/reflection-and-codedom/using-the-codedom.md)  
 Описываются общие случаи применения, а также демонстрируется создание простого графа объектов с использованием CodeDOM.  
  
 [Генерация исходного кода и компиляция программы из графа CodeDOM](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)  
 Описываются способы генерации исходного кода и его компиляции внешним компилятором с использованием классов, определенных в пространстве имен `System.CodeDom.Compiler`.  
  
 [How to: Create an XML Documentation File Using CodeDOM](../../../docs/framework/reflection-and-codedom/how-to-create-an-xml-documentation-file-using-codedom.md)  
 Описывается использование CodeDOM для создания кода с комментариями к XML\-документации и компилирования созданного кода для создания XML\-документации.  
  
 [How to: Create a Class Using CodeDOM](../../../docs/framework/reflection-and-codedom/how-to-create-a-class-using-codedom.md)  
 Описывается использование CodeDOM для создания класса, содержащего поля, свойства, метод, конструктор и точку входа.  
  
## Ссылка  
 <xref:System.CodeDom>  
 Определяет элементы, представляющие элементы кода на языках программирования, предназначенных для общеязыковой среды выполнения.  
  
 <xref:System.CodeDom.Compiler>  
 Определяет интерфейсы для генерации и компиляции кода во время выполнения.  
  
## Связанные подразделы  
 [CodeDOM Quick Reference](http://msdn.microsoft.com/ru-ru/c77b8bfd-0a32-4e36-b59a-4f687f32c524)  
 Предоставляет разработчикам быстрый способ поиска элементов CodeDOM, представляющих элементы исходного кода.