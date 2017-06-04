---
title: "Компонент BackgroundWorker | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "асинхронная модель"
  - "фоновые операции"
  - "фоновые задачи"
  - "BackgroundWorker - компонент"
  - "компоненты [Windows Forms], асинхронный"
  - "формы, фоновые операции"
  - "формы, многопоточность"
  - "работа с потоками [Windows Forms], фоновые операции"
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Компонент BackgroundWorker
Компонент `BackgroundWorker` позволяет форме или элементу управления выполнить операцию в асинхронном режиме.  
  
## В этом подразделе  
 [Общие сведения о компоненте BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 Описание компонента `BackgroundWorker`, который обеспечивает возможность выполнения длительных операций в асинхронном \(фоновом\) режиме в потоке, отличном от основного потока пользовательского интерфейса приложения.  
  
 [Пример. Фоновое выполнение операции](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 Демонстрация использования компонента `BackgroundWorker` в конструкторе для выполнения длительной операции в отдельном потоке.  
  
 [Практическое руководство. Фоновое выполнение операции](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 Демонстрация использования компонента `BackgroundWorker` для выполнения длительной операции в отдельном потоке.  
  
 [Пошаговое руководство. Реализация формы, в которой выполняется фоновая операция](../../../../docs/framework/winforms/controls/walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 Создание приложения с помощью конструктора, выполняющего математические вычисления в асинхронном режиме.  
  
 [Практическое руководство. Реализация формы, в которой выполняется фоновая операция](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 Создание приложения, выполняющего математические вычисления в асинхронном режиме.  
  
 [Практическое руководство. Фоновая загрузка файла](../../../../docs/framework/winforms/controls/how-to-download-a-file-in-the-background.md)  
 Демонстрация использования компонента `BackgroundWorker` для загрузки файла в отдельном потоке.  
  
## Ссылка  
 <xref:System.ComponentModel.BackgroundWorker>  
 Описание класса и ссылки на все его члены.  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 Описание типа, содержащего данные для события <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>.  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 Описание типа, содержащего данные для события <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>.  
  
## Связанные подразделы  
 [Event\-based Asynchronous Pattern Overview](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 Информация о том, каким образом асинхронная модель позволяет использовать преимущества многопоточных приложений, скрывая многие сложные проблемы, присущие многопоточной архитектуре.