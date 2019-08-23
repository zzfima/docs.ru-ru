---
title: Сопоставления типов данных в ADO.NET
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: ddb3c1c5551336ace66bab53af3beb83b6cd2d34
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950403"
---
# <a name="data-type-mappings-in-adonet"></a>Сопоставления типов данных в ADO.NET
Платформа .NET Framework основана на общей системе типов, в которой определяются способы объявления, использования типов и управления ими во время выполнения. Система типов состоит из типов-значений и типов-ссылок, производных от базового типа <xref:System.Object>. При работе с источником данных не указанный явным образом тип данных выводится из поставщика данных. Например, объект <xref:System.Data.DataSet> не зависит ни от одного конкретного источника данных. Получение данных в `DataSet` осуществляется из источника данных, а изменения передаются для сохранения в источнике данных с использованием `DataAdapter`. Это означает, что при `DataAdapter` <xref:System.Data.DataTable> заполнении в `DataSet` со значениями из источника данных `DataTable` результирующие типы данных столбцов в являются .NET Framework типами, а не типами, характерными для .NET Frameworkного поставщика данных, который используется для подключения к источнику данных.  
  
 Аналогично, когда `DataReader` объект возвращает значение из источника данных, полученное значение сохраняется в локальной переменной, имеющей тип .NET Framework. Как для `Fill` операций `DataAdapter` , `Get` так`DataReader`и для методов, тип .NET Framework выводится из значения, возвращаемого поставщиком данных .NET Framework.  
  
 Если известен тип возвращаемого значения, то вместо выводимого типа данных можно воспользоваться типизированными методами доступа объекта `DataReader`. Типизированные методы доступа обеспечивают лучшую производительность, возвращая значение как конкретный тип .NET Framework, что устраняет необходимость в дополнительном преобразовании типов.  
  
> [!NOTE]
> Значения NULL для типов данных поставщика данных .NET Framework представлены в `DBNull.Value`.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Сопоставления типов данных SQL Server](../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 Выводит список сопоставлений выводимых типов данных и методов доступа к данным для объекта <xref:System.Data.SqlClient>.  
  
 [Сопоставления типов данных OLE DB](../../../../docs/framework/data/adonet/ole-db-data-type-mappings.md)  
 Выводит список сопоставлений выводимых типов данных и методов доступа к данным для объекта <xref:System.Data.OleDb>.  
  
 [Сопоставления типов данных ODBC](../../../../docs/framework/data/adonet/odbc-data-type-mappings.md)  
 Выводит список сопоставлений выводимых типов данных и методов доступа к данным для объекта <xref:System.Data.Odbc>.  
  
 [Сопоставления типов данных Oracle](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 Выводит список сопоставлений выводимых типов данных и методов доступа к данным для объекта <xref:System.Data.OracleClient>.  
  
 [Числа с плавающей запятой](../../../../docs/framework/data/adonet/floating-point-numbers.md)  
 Описывает проблемы, с которыми разработчики часто сталкиваются при работе с числами с плавающей запятой.  
  
## <a name="see-also"></a>См. также

- [Типы данных SQL Server и ADO.NET](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)
- [Настройка параметров и типы данных параметров](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [Извлечение сведений о схеме базы данных](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [Система общих типов CTS](../../../standard/base-types/common-type-system.md)
- [Преобразование типов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
