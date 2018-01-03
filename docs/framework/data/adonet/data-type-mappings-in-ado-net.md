---
title: "Сопоставления типов данных в ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b30f4e36ffd98289bb971e04b55b0249138e0efd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
 [Типы данных SQL Server и ADO.NET](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [Настройка параметров и типы данных параметров](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [Извлечение сведений о схеме базы данных](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [Система общих типов CTS](../../../../docs/standard/base-types/common-type-system.md)  
 [Преобразование типов](http://msdn.microsoft.com/en-us/6038316e-bdaf-4f55-8006-407f591ce156)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
