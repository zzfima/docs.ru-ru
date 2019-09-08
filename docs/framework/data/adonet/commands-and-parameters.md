---
title: Команды и параметры
ms.date: 03/30/2017
ms.assetid: b623f810-d871-49a5-b0f5-078cc3c34db6
ms.openlocfilehash: 1d0c3adb56e5ff44b5c5e065ac040f25584a1946
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784954"
---
# <a name="commands-and-parameters"></a>Команды и параметры
После установки соединения с источником данных при помощи объекта <xref:System.Data.Common.DbCommand> можно выполнять команды и возвращать результаты из источника данных. Команду можно создать с помощью одного из используемых конструкторов команд для поставщика данных .NET Framework. Конструкторы могут принимать необязательные аргументы, например инструкцию SQL для выполнения в источнике данных, объект <xref:System.Data.Common.DbConnection> или объект <xref:System.Data.Common.DbTransaction>. Эти объекты также можно настроить как свойства команды. При помощи метода <xref:System.Data.Common.DbConnection.CreateCommand%2A> объекта `DbConnection` также можно создать команду для конкретного соединения. Инструкцию SQL, выполняемую командой, можно настроить с помощью свойства <xref:System.Data.Common.DbCommand.CommandText%2A>.  
  
 У каждого поставщика данных .NET Framework, имеющегося в платформе .NET Framework, есть объект `Command`. Поставщик данных .NET Framework для OLE DB содержит объект <xref:System.Data.OleDb.OleDbCommand>, поставщик данных .NET Framework для SQL Server - объект <xref:System.Data.SqlClient.SqlCommand>, поставщик данных .NET Framework для ODBC - объект <xref:System.Data.Odbc.OdbcCommand>, а поставщик данных .NET Framework для Oracle - объект <xref:System.Data.OracleClient.OracleCommand>.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Выполнение команды](executing-a-command.md)  
 Описание объекта ADO.NET `Command` и его использования для выполнения запросов и команд в источнике данных.  
  
 [Настройка параметров и типы данных параметров](configuring-parameters-and-parameter-data-types.md)  
 Описание работы с параметрами `Command`, включая направление, типы данных и синтаксис параметров.  
  
 [Создание команд с помощью построителей CommandBuilder](generating-commands-with-commandbuilders.md)  
 Описание использования построителей команд для автоматического формирования команд INSERT, UPDATE и DELETE для адаптера `DataAdapter`, у которого имеется команда SELECT с одной таблицей.  
  
 [Получение одного значения из базы данных](obtaining-a-single-value-from-a-database.md)  
 Описывается использование метода `ExecuteScalar` объекта `Command` для возврата из запроса к базе данных одиночного значения.  
  
 [Использование команд для изменения данных](using-commands-to-modify-data.md)  
 Описывается использование поставщика данных для выполнения хранимых процедур или инструкций языка описания данных DDL.  
  
## <a name="see-also"></a>См. также

- [Объекты DataAdapter и DataReader](dataadapters-and-datareaders.md)
- [Наборы данных, таблицы данных и объекты DataView](./dataset-datatable-dataview/index.md)
- [Подключение к источнику данных](connecting-to-a-data-source.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
