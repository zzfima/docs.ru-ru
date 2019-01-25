---
title: Подключение к источнику данных в ADO.NET
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 20cf22e1c9b9bf18dd3109cb9589c05a6c27d4d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701746"
---
# <a name="connecting-to-a-data-source-in-adonet"></a>Подключение к источнику данных в ADO.NET
В ADO.NET используется **подключения** объекта для подключения к определенному источнику данных, указав необходимые данные для аутентификации в строке подключения. **Подключения** объектом, который используется зависит от типа источника данных.  
  
 Каждый поставщик данных .NET Framework, входящий в состав .NET Framework, включает объект <xref:System.Data.Common.DbConnection>: поставщик данных .NET Framework для OLE DB содержит объект <xref:System.Data.OleDb.OleDbConnection>, поставщик данных .NET Framework для SQL Server содержит объект <xref:System.Data.SqlClient.SqlConnection>, поставщик данных .NET Framework для ODBC содержит объект <xref:System.Data.Odbc.OdbcConnection>, поставщик данных .NET Framework для Oracle содержит объект <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Установка подключения](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 Описывает использование **подключения** объектов для установления соединения с источником данных.  
  
 [События подключения](../../../../docs/framework/data/adonet/connection-events.md)  
 Описывает использование **InfoMessage** событий для получения информационных сообщений из источника данных.  
  
## <a name="see-also"></a>См. также
- [Строки подключения](../../../../docs/framework/data/adonet/connection-strings.md)
- [Объединение подключений в пул](../../../../docs/framework/data/adonet/connection-pooling.md)
- [Команды и параметры](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [Транзакции и параллельность](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
