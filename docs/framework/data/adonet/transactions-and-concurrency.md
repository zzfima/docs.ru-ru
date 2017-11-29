---
title: "Транзакции и параллельность"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4e06f54ed27a555daa30f16f452cd03c8e188a0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="transactions-and-concurrency"></a>Транзакции и параллельность
Транзакция состоит из одной команды или группы команд, которые выполняются как пакет. Транзакции позволяют объединить несколько операций в одну единицу работы. Если в какой-либо точке транзакции возникает ошибка, может быть выполнен откат всех обновлений к их состоянию до начала транзакции.  
  
 Для обеспечения согласованности данных транзакция должна соответствовать свойствам ACID (атомарность, согласованность, изоляция и устойчивость). Большая часть систем реляционных баз данных, таких как Microsoft SQL Server, поддерживает транзакции, предоставляя блокировку, ведение журнала и средства управления транзакцией при выполнении клиентским приложением операций обновления, вставки или удаления.  
  
> [!NOTE]
>  Транзакции, которые задействуют множество ресурсов, могут снизить параллелизм, если слишком долго удерживают блокировки. Поэтому транзакции следует делать как можно короче.  
  
 В том случае, если в транзакции участвует несколько таблиц одной базы данных или одного сервера, явные транзакции в хранимых процедурах часто выполняются лучше. Транзакции можно создавать в хранимых процедурах SQL Server с использованием инструкций Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION` и `ROLLBACK TRANSACTION`. Дополнительные сведения см. в электронной документации по SQL Server.  
  
 Если для выполнения транзакций требуются различные диспетчеры ресурсов, например для транзакций между [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] и Oracle, необходимо использовать распределенную транзакцию.  
  
## <a name="in-this-section"></a>Содержание  
 [Локальные транзакции](../../../../docs/framework/data/adonet/local-transactions.md)  
 Демонстрирует выполнение транзакций на базе данных.  
  
 [Распределенные транзакции](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 Описывает выполнение распределенных транзакций в ADO.NET.  
  
 [Интеграция System.Transactions с SQL Server](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 Описывает интеграцию <xref:System.Transactions> с [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] для работы с распределенными транзакциями.  
  
 [Оптимистический параллелизм](../../../../docs/framework/data/adonet/optimistic-concurrency.md)  
 Описывается оптимистичный и пессимистичный параллелизм и проверка на выявление нарушений параллелизма.  
  
## <a name="see-also"></a>См. также  
 [Основные сведения о транзакциях](../../../../docs/framework/data/transactions/transaction-fundamentals.md)  
 [Подключение к источнику данных](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [Команды и параметры](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
