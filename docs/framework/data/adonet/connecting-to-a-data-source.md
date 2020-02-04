---
title: Подключение к источнику данных
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 84dc15c0965b7ac8209bd9115d611162e57d6dda
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980253"
---
# <a name="connecting-to-a-data-source-in-adonet"></a>Подключение к источнику данных в ADO.NET
В ADO.NET для подключения к определенному источнику данных используется объект **соединения** путем предоставления необходимых сведений о проверке подлинности в строке подключения. Используемый объект **соединения** зависит от типа источника данных.  
  
 Каждый поставщик данных .NET Framework, входящий в состав .NET Framework, включает объект <xref:System.Data.Common.DbConnection>: поставщик данных .NET Framework для OLE DB содержит объект <xref:System.Data.OleDb.OleDbConnection>, поставщик данных .NET Framework для SQL Server содержит объект <xref:System.Data.SqlClient.SqlConnection>, поставщик данных .NET Framework для ODBC содержит объект <xref:System.Data.Odbc.OdbcConnection>, поставщик данных .NET Framework для Oracle содержит объект <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Установка подключения](establishing-the-connection.md)  
 Описывает использование объекта **Connection** для установления соединения с источником данных.  
  
 [События подключения](connection-events.md)  
 Описывает использование события **InfoMessage** для получения информационных сообщений из источника данных.  
  
## <a name="see-also"></a>См. также:

- [Строки подключения](connection-strings.md)
- [Объединение подключений в пул](connection-pooling.md)
- [Команды и параметры](commands-and-parameters.md)
- [Объекты DataAdapter и DataReader](dataadapters-and-datareaders.md)
- [Транзакции и параллельность](transactions-and-concurrency.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
