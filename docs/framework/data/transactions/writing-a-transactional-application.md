---
title: Создание транзакционного приложения
ms.date: 03/30/2017
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
ms.openlocfilehash: 048df434ff0ada2ab5f8c7473913f6c34c05d1a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793495"
---
# <a name="writing-a-transactional-application"></a>Создание транзакционного приложения
Пространство имен <xref:System.Transactions> предоставляет разработчикам транзакционных приложений две модели программирования для создания транзакций. Вы можете использовать модель явного программирования с помощью <xref:System.Transactions.Transaction> класса или модель неявного программирования, в котором транзакции автоматически управляются инфраструктурой, с помощью <xref:System.Transactions.TransactionScope> класса. Корпорация Майкрософт рекомендует использовать модель неявной транзакции для разработки приложений. Можно найти дополнительные сведения об использовании области транзакции в [реализация неявной транзакции с использованием области транзакции](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md) раздела.  
  
 Обе модели поддерживают фиксацию транзакции при достижении программой согласованного состояния. При успешной фиксации выполненные в ходе транзакции изменения становятся постоянными. Если фиксация завершается неудачей, транзакция прерывается. Если приложение не может успешно завершить транзакцию, оно пытается прервать ее выполнение и отменить произведенные в ходе транзакции изменения.  
  
## <a name="in-this-section"></a>В этом разделе  
  
### <a name="creating-a-transaction"></a>Создание транзакции  
 Пространство имен <xref:System.Transactions> предоставляет две модели для создания транзакций. Эти модели рассматриваются в следующих разделах.  
  
 [Реализация неявной транзакции с использованием области транзакции](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 Описывает, как пространство имен <xref:System.Transactions> поддерживает создание неявных транзакций с использованием класса <xref:System.Transactions.TransactionScope>.  
  
 [Реализация явной транзакции с помощью класса CommittableTransaction](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 Описывает, как пространство имен <xref:System.Transactions> поддерживает создание явных транзакций с использованием класса <xref:System.Transactions.CommittableTransaction>.  
  
### <a name="escalating-transaction-management"></a>Передача управления транзакцией на следующий уровень иерархии  
 Если транзакции необходим доступ к ресурсу в другом домене приложения или требуется зачислить другой диспетчер устойчивых ресурсов, управление транзакцией автоматически передается координатору MSDTC. Распространение транзакций рассматривается в [эскалации управления транзакцией](../../../../docs/framework/data/transactions/transaction-management-escalation.md) раздела.  
  
### <a name="concurrency"></a>параллелизм  
 Раздел [управление параллелизмом с помощью класса DependentTransaction](../../../../docs/framework/data/transactions/managing-concurrency-with-dependenttransaction.md) демонстрирует, как можно достичь параллелизма между асинхронных задач с помощью <xref:System.Transactions.DependentTransaction> класса.  
  
### <a name="com-interop"></a>Взаимодействие с транзакциями COM+  
 Раздел [взаимодействие с транзакциями COM + Enterprise Services и](../../../../docs/framework/data/transactions/interoperability-with-enterprise-services-and-com-transactions.md) показано, как сделать взаимодействия с транзакциями COM + распределенных транзакций.  
  
### <a name="diagnostics"></a>Диагностика  
 [Диагностическая трассировка](../../../../docs/framework/data/transactions/diagnostic-traces.md) описывается, как можно использовать коды трассировки, создаваемых <xref:System.Transactions> инфраструктуры для устранения неполадок в приложениях.  
  
### <a name="working-within-aspnet"></a>Работа в среде ASP.NET  
 [Использование System.Transactions в ASP.NET](../../../../docs/framework/data/transactions/using-system-transactions-in-aspnet.md) разделе описывается, как можно успешно использовать <xref:System.Transactions> внутри приложения ASP.NET.
