---
title: "Локальные транзакции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8ae3712f-ef5e-41a1-9ea9-b3d0399439f1
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f9b1280f3a05a42a2f713adf993bb439245c95a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="local-transactions"></a>Локальные транзакции
В [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] транзакции используются для связи нескольких задач, чтобы они выполнялись как одно целое. Например, пусть приложение выполняет две задачи. Во-первых, оно заносит в таблицу сведения о заказе. Во-вторых, обновляет таблицу, содержащую список товаров на складе, списывая заказанные элементы. При сбое любой задачи, затем оба будет выполнен откат изменений.  
  
## <a name="determining-the-transaction-type"></a>Определение типа транзакции  
 Транзакция считается локальной транзакции при состоит из одной фазы и обрабатывается непосредственно базой данных. Транзакция считается распределенных транзакций при координируемой монитором транзакций и используется для разрешения транзакций резервные механизмы (например, двухфазную фиксацию).  
  
 Для выполнения локальных транзакций каждый поставщик данных платформы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] имеет свой собственный объект `Transaction`. Если требуется выполнить транзакцию в базе данных SQL Server, выбирается транзакция <xref:System.Data.SqlClient>. Для транзакции Oracle используйте поставщик <xref:System.Data.OracleClient>. Кроме того, существует новый класс <xref:System.Data.Common.DbTransaction>, доступный для написания независимого от поставщика кода с использованием транзакций.  
  
> [!NOTE]
>  Транзакции наиболее эффективны, когда выполняются на сервере. При работе с базой данных SQL Server, интенсивно использующей явные транзакции, следует рассмотреть возможность их записи в виде хранимых процедур при помощи инструкции Transact-SQL BEGIN TRANSACTION. Дополнительные сведения о выполнении транзакций на сервере см. в электронной документации по SQL Server.  
  
## <a name="performing-a-transaction-using-a-single-connection"></a>Выполнение транзакций с использованием одного соединения  
 В [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] транзакции управляются объектом `Connection`. Инициировать транзакцию можно с помощью метода `BeginTransaction`. После начала транзакции при помощи свойства `Transaction` объекта `Command` к ней можно прикрепить команду. Затем в зависимости от успеха или ошибки компонентов транзакции можно зафиксировать или откатить изменения, сделанные в источнике данных.  
  
> [!NOTE]
>  Метод `EnlistDistributedTransaction` не должен использоваться для локальной транзакции.  
  
 Область действия транзакции ограничена соединением. В следующем примере выполняется явная транзакция, состоящая из двух отдельных команд в блоке `try`. Команды выполняют инструкции INSERT для таблицы Production.ScrapReason в образце базы данных [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] AdventureWorks, которые будут зафиксированы при отсутствии исключений. При возникновении исключения код в блоке `catch` произведет откат транзакции. При отмене транзакции или обрыве соединения до выполнения транзакции она откатывается автоматически.  
  
## <a name="example"></a>Пример  
 Чтобы осуществить транзакцию, выполните указанные ниже действия.  
  
1.  Вызовите метод <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> объекта <xref:System.Data.SqlClient.SqlConnection> для отметки начала транзакции. Метод <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> возвращает ссылку на транзакцию. Эта ссылка назначается объектам <xref:System.Data.SqlClient.SqlCommand>, прикрепленным к транзакции.  
  
2.  Присвойте объект `Transaction` свойству <xref:System.Data.SqlClient.SqlCommand.Transaction%2A> объекта <xref:System.Data.SqlClient.SqlCommand>. Исключение вызывается, если команда выполняется при соединении с активной транзакцией, а объект `Transaction` не был назначен свойству `Transaction` объекта `Command`.  
  
3.  Выполните требуемые команды.  
  
4.  Для выполнения транзакции вызовите метод <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> объекта <xref:System.Data.SqlClient.SqlTransaction>, для завершения транзакции вызовите метод <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A>. Транзакция откатывается, если соединение закрывается или пропадает до выполнения метода <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> либо <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A>.  
  
 Следующий пример кода демонстрирует транзакционную логику, используемую [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] с Microsoft SQL Server.  
  
 [!code-csharp[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Транзакции и параллелизм](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [Распределенные транзакции](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 [Интеграция System.Transactions с SQL Server](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
