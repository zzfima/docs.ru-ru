---
title: "Практическое руководство. Реализация формы, в которой выполняется фоновая операция | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "фоновые операции"
  - "фоновые задачи"
  - "фоновые потоки"
  - "BackgroundWorker - компонент"
  - "компоненты [Windows Forms], асинхронный"
  - "формы, фоновые операции"
  - "формы, многопоточность"
  - "работа с потоками [Windows Forms], фоновые операции"
  - "работа с потоками [Windows Forms], формы"
ms.assetid: 9f483f93-1613-4be1-a021-b4934e9c78f3
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Реализация формы, в которой выполняется фоновая операция
В примере ниже программа создает форму, которая вычисляет числа Фибоначчи.  Вычисление выполняется в потоке, отдельном от потока пользовательского интерфейса, поэтому в ходе вычисления пользовательский интерфейс продолжает выполняться без задержек.  
  
 В Visual Studio предусмотрена расширенная поддержка этой задачи.  
  
 См. также [Пошаговое руководство. Реализация формы, в которой выполняется фоновая операция](http://msdn.microsoft.com/library/b2zk6580\(v=vs.110\)).  
  
## Пример  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Drawing и System.Windows.Forms.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение скомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Отказоустойчивость  
  
> [!CAUTION]
>  При использовании любой многопоточности существует потенциальная возможность возникновения серьезных ошибок.  Перед реализацией любого решения, в котором используется многопоточность, ознакомьтесь с разделом [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md).  
  
## См. также  
 <xref:System.ComponentModel.BackgroundWorker>   
 <xref:System.ComponentModel.DoWorkEventArgs>   
 [Event\-based Asynchronous Pattern Overview](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)   
 [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md)