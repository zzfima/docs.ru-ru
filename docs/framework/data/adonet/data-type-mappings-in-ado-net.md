---
title: Сопоставления типов данных в ADO.NET
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: 1db427424e48d5b94e6c158e1d9967626297f4aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178702"
---
# <a name="data-type-mappings-in-adonet"></a>Сопоставления типов данных в ADO.NET
Платформа .NET Framework основана на общей системе типов, в которой определяются способы объявления, использования типов и управления ими во время выполнения. Система типов состоит из типов-значений и типов-ссылок, производных от базового типа <xref:System.Object>. При работе с источником данных не указанный явным образом тип данных выводится из поставщика данных. Например, объект <xref:System.Data.DataSet> не зависит ни от одного конкретного источника данных. Получение данных в `DataSet` осуществляется из источника данных, а изменения передаются для сохранения в источнике данных с использованием `DataAdapter`. Это означает, что при заполнении адаптером `DataAdapter` таблицы <xref:System.Data.DataTable> в наборе данных `DataSet` значениями из источника данных, результирующие типы данных столбцов в `DataTable` представляют собой типы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], а не типы, относящиеся к поставщику данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], который использовался для подключения к источнику данных.  
  
 Аналогичным образом, при возврате модулем `DataReader` любого значения из источника данных результирующее значение сохраняется в локальной переменной, которая имеет тип [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Как для операций `Fill` объекта `DataAdapter`, так и для методов `Get` класса `DataReader`, тип [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] выводится из значения, возвращенного поставщиком данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
 Если известен тип возвращаемого значения, то вместо выводимого типа данных можно воспользоваться типизированными методами доступа объекта `DataReader`. Применение типизированных методов доступа позволяет достичь более высокой производительности, поскольку происходит возврат значения в качестве конкретного типа [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], в связи с чем устраняется необходимость в дополнительном преобразовании типа.  
  
> [!NOTE]
>  Значения NULL для типов данных поставщика данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] представлены с помощью `DBNull.Value`.  
  
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
- [Система общих типов CTS](../../../../docs/standard/base-types/common-type-system.md)
- [Преобразование типов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/t8s7t9bf(v=vs.90))
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
