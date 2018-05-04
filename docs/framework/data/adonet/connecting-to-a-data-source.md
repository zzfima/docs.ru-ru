---
title: Подключение к источнику данных в ADO.NET
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 27653c3e1f14e08fc8b5e1225a441072778a0cc8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="connecting-to-a-data-source-in-adonet"></a>Подключение к источнику данных в ADO.NET
В ADO.NET используется **подключения** для подключения к определенному источнику данных путем передачи сведений о необходимости проверки подлинности в строке подключения. **Подключения** использовании объект зависит от типа источника данных.  
  
 Каждый поставщик данных .NET Framework, входящий в состав .NET Framework, включает объект <xref:System.Data.Common.DbConnection>: поставщик данных .NET Framework для OLE DB содержит объект <xref:System.Data.OleDb.OleDbConnection>, поставщик данных .NET Framework для SQL Server содержит объект <xref:System.Data.SqlClient.SqlConnection>, поставщик данных .NET Framework для ODBC содержит объект <xref:System.Data.Odbc.OdbcConnection>, поставщик данных .NET Framework для Oracle содержит объект <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Установка подключения](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 Описывает использование **подключения** объектов для установления соединения с источником данных.  
  
 [События подключения](../../../../docs/framework/data/adonet/connection-events.md)  
 Описывает использование **InfoMessage** событий для получения информационных сообщений из источника данных.  
  
## <a name="see-also"></a>См. также  
 [Строки подключения](../../../../docs/framework/data/adonet/connection-strings.md)  
 [Объединение подключений в пул](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [Команды и параметры](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Транзакции и параллельность](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
