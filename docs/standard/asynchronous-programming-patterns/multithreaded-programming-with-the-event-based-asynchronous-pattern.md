---
title: "Multithreaded Programming with the Event-based Asynchronous Pattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Event-based Asynchronous Pattern"
  - "ProgressChangedEventArgs class"
  - "BackgroundWorker component"
  - "events [.NET Framework], asynchronous"
  - "AsyncOperationManager class"
  - "threading [.NET Framework], asynchronous features"
  - "components [.NET Framework], asynchronous"
  - "AsyncOperation class"
  - "AsyncCompletedEventArgs class"
ms.assetid: 958d6617-5e70-4b36-b5db-63c16dc35e43
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Multithreaded Programming with the Event-based Asynchronous Pattern
Существует несколько способов предоставить асинхронные функции клиентскому коду.  Асинхронная модель на основе событий задает для классов рекомендуемый способ работы в асинхронном режиме.  
  
## В этом подразделе  
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 Описывает, как асинхронная модель на основе событий позволяет использовать преимущества многопоточных приложений и устраняет многие сложности, присущие многопоточности.  
  
 [Implementing the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 Описывает стандартизированный способ упаковки класса, имеющего асинхронные функции.  
  
 [Рекомендации по реализации асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 Описывает требования для предоставления асинхронных функций в соответствии с асинхронной моделью на основе событий.  
  
 [Deciding When to Implement the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 Описывает, в каких случаях следует реализовать асинхронную модель на основе событий вместо шаблона <xref:System.IAsyncResult>.  
  
 [Walkthrough: Implementing a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 Демонстрирует, как создать компонент, реализующий асинхронную модель на основе событий.  Она реализуется с использованием вспомогательных классов из пространства имен <xref:System.ComponentModel?displayProperty=fullName>, что обеспечивает правильную работу компонента при любой модели приложения.  
  
 [How to: Use Components That Support the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 Описывает использование компонента, поддерживающего асинхронную модель на основе событий.  
  
## Ссылка  
 <xref:System.ComponentModel.AsyncOperation>  
 Описывает класс <xref:System.ComponentModel.AsyncOperation> и содержит ссылки на все его члены.  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 Описывает класс <xref:System.ComponentModel.AsyncOperationManager> и содержит ссылки на все его члены.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Описывает компонент <xref:System.ComponentModel.BackgroundWorker> и содержит ссылки на все его члены.  
  
## См. также  
 [Managed Threading Best Practices](../../../docs/standard/threading/managed-threading-best-practices.md)   
 [События](../../../docs/standard/events/index.md)   
 [Multithreading in Components](../Topic/Multithreading%20in%20Components.md)   
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)