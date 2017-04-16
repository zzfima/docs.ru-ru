---
title: "Создание транзакционного приложения  | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Создание транзакционного приложения 
Пространство имен <xref:System.Transactions> предоставляет разработчикам транзакционных приложений две модели программирования для создания транзакций.Можно использовать модель явного программирования, применяя класс <xref:System.Transactions.Transaction>, или модель неявного программирования, в которой транзакции автоматически управляются инфраструктурой, применяя класс <xref:System.Transactions.TransactionScope>.Для разработки рекомендуется использовать модель неявного программирования транзакций.Дополнительные сведения об использовании области транзакции см. в разделе [Реализация неявной транзакции с использованием области транзакции ](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md).  
  
 Обе модели поддерживают фиксацию транзакции при достижении программой согласованного состояния.При успешной фиксации выполненные в ходе транзакции изменения становятся постоянными.Если фиксация завершается неудачей, транзакция прерывается.Если приложение не может успешно завершить транзакцию, оно пытается прервать ее выполнение и отменить произведенные в ходе транзакции изменения.  
  
## В этом разделе  
  
### Создание транзакции  
 Пространство имен <xref:System.Transactions> предоставляет две модели для создания транзакций.Эти модели рассматриваются в следующих разделах.  
  
 [Реализация неявной транзакции с использованием области транзакции ](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 Описывает, как пространство имен <xref:System.Transactions> поддерживает создание неявных транзакций с использованием класса <xref:System.Transactions.TransactionScope>.  
  
 [Реализация явной транзакции с помощью класса CommittableTransaction ](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 Описывает, как пространство имен <xref:System.Transactions> поддерживает создание явных транзакций с использованием класса <xref:System.Transactions.CommittableTransaction>.  
  
### Передача управления транзакцией на следующий уровень иерархии  
 Если транзакции необходим доступ к ресурсу в другом домене приложения или требуется прикрепить другой диспетчер устойчивых ресурсов, управление транзакцией автоматически передается координатору MSDTC.Порядок передачи транзакции на следующий уровень иерархии рассматривается в разделе [Передача управления транзакцией на следующий уровень иерархии ](../../../../docs/framework/data/transactions/transaction-management-escalation.md).  
  
### Параллелизм  
 В разделе [Управление параллелизмом с помощью класса DependentTransaction ](../../../../docs/framework/data/transactions/managing-concurrency-with-dependenttransaction.md) описывается порядок обеспечения параллельного выполнения асинхронных задач с помощью класса <xref:System.Transactions.DependentTransaction>.  
  
### Взаимодействие с транзакциями COM\+  
 В разделе [Взаимодействие с транзакциями Enterprise Services и COM\+ ](../../../../docs/framework/data/transactions/interoperability-with-enterprise-services-and-com-transactions.md) описывается порядок обеспечения взаимодействия распределенных транзакций с транзакциями COM\+.  
  
### Диагностика  
 В разделе [Диагностическая трассировка ](../../../../docs/framework/data/transactions/diagnostic-traces.md) описывается порядок использования кодов трассировки, создаваемых инфраструктурой <xref:System.Transactions>, для устранения неполадок приложений.  
  
### Работа в среде ASP.NET  
 В разделе [Использование инфраструктуры System.Transactions в среде ASP.NET](../../../../docs/framework/data/transactions/using-system-transactions-in-aspnet.md) описывается, как можно успешно использовать инфраструктуру <xref:System.Transactions> в приложении ASP.NET.