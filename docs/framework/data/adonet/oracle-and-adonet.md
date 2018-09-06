---
title: Oracle и ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 9a60499674f0192bb7589f227bffb6f907f682d9
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43786074"
---
# <a name="oracle-and-adonet"></a>Oracle и ADO.NET
> [!NOTE]
>  Типы в пространстве имен <xref:System.Data.OracleClient> считаются устаревшими. Эти типы по-прежнему поддерживаются в платформе .NET Framework текущей версии, однако будут удалены в следующем выпуске. Корпорация Майкрософт рекомендует использовать поставщик Oracle, предоставляемый сторонними разработчиками.  
  
 В этом разделе описаны функции и правила работы, характерные для поставщика данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для Oracle.  
  
 Поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для Oracle обеспечивает доступ к базе данных Oracle, используя интерфейс Oracle Call (OCI), поставляемый в пакете клиентского программного обеспечения Oracle. Функциональные возможности поставщика данных должен быть аналогичен [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] поставщики данных для SQL Server, OLE DB и ODBC.  
  
 Чтобы использовать поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для Oracle, приложение должно содержать ссылку на пространство имен <xref:System.Data.OracleClient> следующим образом:   
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 Также при компиляции кода необходимо включить ссылку на библиотеку DLL. Например, при компиляции программы C# командная строка должна включать:  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a>В этом разделе  
 [Требования к системе](../../../../docs/framework/data/adonet/system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 Содержит требования к использованию поставщика данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для Oracle и описывает многие проблемы, которые необходимо учитывать при его использовании.  
  
 [BFILE в Oracle](../../../../docs/framework/data/adonet/oracle-bfiles.md)  
 Описывает класс <xref:System.Data.OracleClient.OracleBFile>, который используется для работы с типом данных Oracle BFILE.  
  
 [Большие объекты (LOB) в Oracle](../../../../docs/framework/data/adonet/oracle-lobs.md)  
 Описывает класс <xref:System.Data.OracleClient.OracleLob>, который используется для работы с типом данных Oracle LOB.  
  
 [REF CURSOR в Oracle](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 Описывает поддержку для типа данных Oracle REF CURSOR.  
  
 [OracleTypes](../../../../docs/framework/data/adonet/oracletypes.md)  
 Описывает структуры, которые можно использовать с типами данных Oracle, включая <xref:System.Data.OracleClient.OracleNumber> и <xref:System.Data.OracleClient.OracleString>.  
  
 [Последовательности Oracle](../../../../docs/framework/data/adonet/oracle-sequences.md)  
 Описывает поддержку получения сформированного сервером ключа значений Oracle Sequence.  
  
 [Сопоставления типов данных Oracle](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 Перечисляет типы данных Oracle и их сопоставление с объектом <xref:System.Data.OracleClient.OracleDataReader>.  
  
 [Распределенные транзакции Oracle](../../../../docs/framework/data/adonet/oracle-distributed-transactions.md)  
 Описывает автоматическое прикрепление объекта <xref:System.Data.OracleClient.OracleConnection> к существующей распределенной транзакции, если эта транзакция активна.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Защита приложений ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 Описывает приемы безопасного программирования при использовании [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
 [Наборы данных, таблицы данных и объекты DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Описывает процесс создания и использования объектов `DataSets`, типизированных объектов `DataSets`, а также объектов `DataTables` и `DataViews`.  
  
 [Извлечение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 Описывает работу с данными в ADO.NET.  
  
 [SQL Server и ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)  
 Описывает процесс работы со специальными возможностями и возможностями SQL Server.  
  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 Описывает универсальные классы, позволяющие создавать независимый от поставщика код в [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
## <a name="see-also"></a>См. также  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
