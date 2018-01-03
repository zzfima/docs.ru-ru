---
title: "Создание транзакционного приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9fab355da61ea7445e429cfc4e336a14b588e30c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="writing-a-transactional-application"></a>Создание транзакционного приложения
Пространство имен <xref:System.Transactions> предоставляет разработчикам транзакционных приложений две модели программирования для создания транзакций. Можно использовать модель явного программирования, с помощью <xref:System.Transactions.Transaction> класса или неявное модель программирования, в котором транзакции автоматически управляются инфраструктурой, с помощью <xref:System.Transactions.TransactionScope> класса. Рекомендуется использовать модель неявной транзакции для разработки приложений. Можно найти дополнительные сведения о том, как использовать область транзакции в [реализации неявную транзакцию с помощью области транзакции](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md) раздела.  
  
 Обе модели поддерживают фиксацию транзакции при достижении программой согласованного состояния. При успешной фиксации выполненные в ходе транзакции изменения становятся постоянными. Если фиксация завершается неудачей, транзакция прерывается. Если приложение не может успешно завершить транзакцию, оно пытается прервать ее выполнение и отменить произведенные в ходе транзакции изменения.  
  
## <a name="in-this-section"></a>Содержание  
  
### <a name="creating-a-transaction"></a>Создание транзакции  
 Пространство имен <xref:System.Transactions> предоставляет две модели для создания транзакций. Эти модели рассматриваются в следующих разделах.  
  
 [Реализация неявной транзакции с использованием области транзакции](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 Описывает, как пространство имен <xref:System.Transactions> поддерживает создание неявных транзакций с использованием класса <xref:System.Transactions.TransactionScope>.  
  
 [Реализация явной транзакции с помощью класса CommittableTransaction](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 Описывает, как пространство имен <xref:System.Transactions> поддерживает создание явных транзакций с использованием класса <xref:System.Transactions.CommittableTransaction>.  
  
### <a name="escalating-transaction-management"></a>Передача управления транзакцией на следующий уровень иерархии  
 Если транзакции необходим доступ к ресурсу в другом домене приложения или требуется зачислить другой диспетчер устойчивых ресурсов, управление транзакцией автоматически передается координатору MSDTC. Распространение транзакции, описанные в [эскалации управления транзакцией](../../../../docs/framework/data/transactions/transaction-management-escalation.md) раздела.  
  
### <a name="concurrency"></a>параллелизм  
 Раздел [управление параллелизмом с DependentTransaction](../../../../docs/framework/data/transactions/managing-concurrency-with-dependenttransaction.md) показано, как можно достичь параллелизма между асинхронных задач с помощью <xref:System.Transactions.DependentTransaction> класса.  
  
### <a name="com-interop"></a>Взаимодействие с транзакциями COM+  
 Раздел [взаимодействие с Enterprise Services и транзакции COM +](../../../../docs/framework/data/transactions/interoperability-with-enterprise-services-and-com-transactions.md) показано, как сделать в распределенных транзакциях, которые взаимодействуют с транзакциями COM +.  
  
### <a name="diagnostics"></a>Диагностика  
 [Диагностические трассировки](../../../../docs/framework/data/transactions/diagnostic-traces.md) описывает, как можно использовать коды трассировки, созданные <xref:System.Transactions> инфраструктуры для устранения неполадок в приложениях.  
  
### <a name="working-within-aspnet"></a>Работа в среде ASP.NET  
 [С помощью System.Transactions в ASP.NET](../../../../docs/framework/data/transactions/using-system-transactions-in-aspnet.md) разделе описывается, как можно успешно использовать <xref:System.Transactions> внутри приложения ASP.NET.
