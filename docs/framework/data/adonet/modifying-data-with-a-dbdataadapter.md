---
title: Изменение данных с помощью DbDataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e35c7f9e-648b-4fcc-9361-d365c3e42c9a
ms.openlocfilehash: cd1f5faa0efe141dc064f0150b94807b90e7e2b8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794823"
---
# <a name="modifying-data-with-a-dbdataadapter"></a>Изменение данных с помощью DbDataAdapter
Метод <xref:System.Data.Common.DbProviderFactory.CreateDataAdapter%2A> объекта <xref:System.Data.Common.DbProviderFactory> предоставляет объект <xref:System.Data.Common.DbDataAdapter>, являющийся строго типизированным по отношению к базовому поставщику данных, который был задан во время создания фабрики. После этого объект <xref:System.Data.Common.DbCommandBuilder> можно использовать для создания команд вставки, обновления и удаления данных из объекта <xref:System.Data.DataSet> в источнике данных.  
  
## <a name="retrieving-data-with-a-dbdataadapter"></a>Получение данных с помощью объекта DbDataAdapter  
 В этом примере демонстрируется создание строго типизированного объекта `DbDataAdapter` на основе имени поставщика и строки соединения. В коде используется метод <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A> объекта <xref:System.Data.Common.DbProviderFactory> для создания <xref:System.Data.Common.DbConnection>. После этого в коде с помощью метода <xref:System.Data.Common.DbProviderFactory.CreateCommand%2A> путем указания его свойств <xref:System.Data.Common.DbCommand> и `CommandText` создается команда `Connection` для выборки данных. Наконец, в коде с помощью метода <xref:System.Data.Common.DbDataAdapter> создается объект <xref:System.Data.Common.DbProviderFactory.CreateDataAdapter%2A> и устанавливается его свойство `SelectCommand`. Метод `Fill` объекта `DbDataAdapter` загружает эти данные в <xref:System.Data.DataTable>.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbDataAdapter#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapter/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbDataAdapter#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapter/VB/source.vb#1)]  
  
## <a name="modifying-data-with-a-dbdataadapter"></a>Изменение данных с помощью DbDataAdapter  
 В этом примере демонстрируется модификация данных в `DataTable` с использованием <xref:System.Data.Common.DbDataAdapter>, в котором применяется объект <xref:System.Data.Common.DbCommandBuilder> для формирования команд, необходимых для обновления данных в источнике данных. Значение <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A> свойства `DbDataAdapter` устанавливается для получения значений CustomerID и CompanyName из таблицы Customers. Метод <xref:System.Data.Common.DbCommandBuilder.GetInsertCommand%2A> используется для задания свойства <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, метод <xref:System.Data.Common.DbCommandBuilder.GetUpdateCommand%2A> служит для задания свойства <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A>, а метод <xref:System.Data.Common.DbCommandBuilder.GetDeleteCommand%2A> используется для задания свойства <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A>. В коде осуществляется добавление новой строки в таблицу Customers и обновление источника данных. После этого в коде находится добавленная строка путем поиска по значению CustomerID, представляющему собой первичный ключ, определенный для таблицы Customers. В коде изменяется значение CompanyName и обновляется источник данных. Наконец, строка удаляется.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbDataAdapterModify#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapterModify/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbDataAdapterModify#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapterModify/VB/source.vb#1)]  
  
## <a name="handling-parameters"></a>Обработка параметров  
 В поставщиках данных .NET Framework обработка именованием и заданием параметров и параметров-местозаполнителей выполняется по-разному. Этот синтаксис зависит от конкретного источника данных, как описано в следующей таблице.  
  
|Поставщик данных|Синтаксис именования параметров|  
|-------------------|-----------------------------|  
|`SqlClient`|Использует именованные параметры в формате `@`*имяпараметра*.|  
|`OracleClient`|Использует именованные параметры в формате `:`*имяпараметра* (или *имяпараметра*).|  
|`OleDb`|Использует маркеры позиционных параметров, указываемые знаком вопроса (`?`).|  
|`Odbc`|Использует маркеры позиционных параметров, указываемые знаком вопроса (`?`).|  
  
 Фабричная модель не помогает при создании параметризованных объектов `DbCommand` и `DbDataAdapter`. В коде необходимо будет выполнить переход к другому участку кода для создания параметров, предназначенных для используемого поставщика данных.  
  
> [!IMPORTANT]
> Полный отказ от использования параметров, зависящих от поставщика, путем применения объединения строк для непосредственного создания инструкций SQL не рекомендуется по соображениям безопасности. Если вместо параметров используется объединение строк, то приложение становится уязвимым к атакам по принципу внедрения кода SQL.  
  
## <a name="see-also"></a>См. также

- [DbProviderFactories](dbproviderfactories.md)
- [Получение класса DbProviderFactory](obtaining-a-dbproviderfactory.md)
- [DbConnection, DbCommand и DbException](dbconnection-dbcommand-and-dbexception.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
