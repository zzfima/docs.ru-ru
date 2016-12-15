---
title: "Оператор using (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "using - оператор [C#]"
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
caps.latest.revision: 31
caps.handback.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Оператор using (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Предоставляет удобный синтаксис, обеспечивающий правильное использование объектов <xref:System.IDisposable>.  
  
## Пример  
 В следующем примере показано, как использовать оператор using.  
  
 [!code-cs[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## Заметки  
 <xref:System.IO.File> и <xref:System.Drawing.Font> являются примерами управляемых типов, имеющих доступ к неуправляемым ресурсам \(в этом случае файл обрабатывает контексты устройств\).  Существует много других видов неуправляемых ресурсов и типов библиотек классов, которые их инкапсулируют.  Все эти типы должны реализовать интерфейс <xref:System.IDisposable>.  
  
 Как правило, при использовании объекта `IDisposable` его следует объявить и создать в операторе `using`.  Оператор `using` соответствующим образом вызывает метод <xref:System.IDisposable.Dispose%2A> в объекте и \(если он используется как описано выше\) приводит к выводу объекта из области действия сразу после вызова <xref:System.IDisposable.Dispose%2A>.  В рамках блока `using` объект доступе только для чтения и не может быть изменен или переназначен.  
  
 Оператор `using` гарантирует вызов метода <xref:System.IDisposable.Dispose%2A>, даже если при вызове методов в объекте происходит исключение.  Такого же результата можно достичь при размещении объекта в блоке try и последующем вызове метода <xref:System.IDisposable.Dispose%2A> в блоке finally; фактически, это способ преобразования оператора `using` компилятором.  Приведенный ранее пример кода во время компиляции расширяется до следующего кода \(при создании ограниченной области действия для объекта обратите внимание на дополнительные фигурные скобки\).  
  
 [!code-cs[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
  
 Несколько экземпляров типа могут быть объявлены в операторе `using`, как показано в следующем примере.  
  
 [!code-cs[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 Можно создать объект ресурсов, а затем передать переменную в оператор `using`, однако этот способ не является рекомендованным.  В этом случае после того, как элемент управления выводится из блока `using`, объект остается в области действия, даже если он больше не сможет обращаться к неуправляемым ресурсам.  Другими словами, он больше не будет полностью инициализирован.  При попытке использовать объект вне блока `using` возникает риск вызова исключения.  По этой причине предпочтительно создать объект в операторе `using` и ограничить область его действия блоком `using`.  
  
 [!code-cs[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Директива using](../../../csharp/language-reference/keywords/using-directive.md)   
 [Garbage Collection](../Topic/Garbage%20Collection.md)   
 [Implementing a Dispose Method](../Topic/Implementing%20a%20Dispose%20Method.md)