---
title: Сопоставления типов данных в ADO.NET
ms.date: 03/30/2017
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
ms.openlocfilehash: 4e85db4732da664848cee2ef48f9a880a86fef18
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583763"
---
# <a name="data-type-mappings-in-adonet"></a>Сопоставления типов данных в ADO.NET
Платформа .NET Framework основана на общей системе типов, в которой определяются способы объявления, использования типов и управления ими во время выполнения. Система типов состоит из типов-значений и типов-ссылок, производных от базового типа <xref:System.Object>. При работе с источником данных не указанный явным образом тип данных выводится из поставщика данных. Например, объект <xref:System.Data.DataSet> не зависит ни от одного конкретного источника данных. Получение данных в `DataSet` осуществляется из источника данных, а изменения передаются для сохранения в источнике данных с использованием `DataAdapter`. Это означает, что при `DataAdapter` заполняет <xref:System.Data.DataTable> в `DataSet` со значениями из источника данных, результирующие типы данных столбцов в `DataTable` являются типами .NET Framework, а не типы, относящиеся к поставщику данных .NET Framework, используется для подключения к источнику данных.  
  
 Аналогичным образом, если `DataReader` возвращает значение из источника данных, результирующее значение сохраняется в локальной переменной с типом .NET Framework. Для обоих `Fill` операций `DataAdapter` и `Get` методы `DataReader`, тип .NET Framework, выводится из значения, возвращенного от поставщика данных .NET Framework.  
  
 Если известен тип возвращаемого значения, то вместо выводимого типа данных можно воспользоваться типизированными методами доступа объекта `DataReader`. Типизированные методы доступа позволяют повысить производительность, возвращая значение как конкретный тип .NET Framework, что устраняет потребность в дополнительном преобразовании типа.  
  
> [!NOTE]
>  Значения NULL для типов данных поставщика данных .NET Framework представлены `DBNull.Value`.  
  
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
