---
title: "Oracle и ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Oracle и ADO.NET
> [!NOTE]
>  Типы в пространстве имен <xref:System.Data.OracleClient> считаются устаревшими.  Эти типы по\-прежнему поддерживаются в платформе .NET Framework текущей версии, однако будут удалены в следующем выпуске.  Корпорация Майкрософт рекомендует использовать поставщик Oracle, предоставляемый сторонними разработчиками.  
  
 В этом разделе описаны функции и правила работы, характерные для поставщика данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для Oracle.  
  
 Поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для Oracle обеспечивает доступ к базе данных Oracle, используя интерфейс Oracle Call \(OCI\), поставляемый в пакете клиентского программного обеспечения Oracle.  Функциональные возможности этого поставщика данных схожи с возможностями поставщиков данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], OLE DB и ODBC.  
  
 Чтобы использовать поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для Oracle, приложение должно содержать ссылку на пространство имен <xref:System.Data.OracleClient> следующим образом:  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 Также при компиляции кода необходимо включить ссылку на библиотеку DLL.  Например, при компиляции программы C\# командная строка должна включать:  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## В этом подразделе  
 [Требования к системе](../../../../docs/framework/data/adonet/system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 Содержит требования к использованию поставщика данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для Oracle и описывает многие проблемы, которые необходимо учитывать при его использовании.  
  
 [BFILE в Oracle](../../../../docs/framework/data/adonet/oracle-bfiles.md)  
 Описывает класс <xref:System.Data.OracleClient.OracleBFile>, который используется для работы с типом данных Oracle BFILE.  
  
 [LOB\-объекты в Oracle](../../../../docs/framework/data/adonet/oracle-lobs.md)  
 Описывает класс <xref:System.Data.OracleClient.OracleLob>, который используется для работы с типом данных Oracle LOB.  
  
 [Курсоры REF CURSOR в Oracle](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 Описывает поддержку для типа данных Oracle REF CURSOR.  
  
 [Объекты OracleType](../../../../docs/framework/data/adonet/oracletypes.md)  
 Описывает структуры, которые можно использовать с типами данных Oracle, включая <xref:System.Data.OracleClient.OracleNumber> и <xref:System.Data.OracleClient.OracleString>.  
  
 [Последовательности Oracle](../../../../docs/framework/data/adonet/oracle-sequences.md)  
 Описывает поддержку получения сформированного сервером ключа значений Oracle Sequence.  
  
 [Сопоставления типов данных Oracle](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 Перечисляет типы данных Oracle и их сопоставление с объектом <xref:System.Data.OracleClient.OracleDataReader>.  
  
 [Распределенные транзакции Oracle](../../../../docs/framework/data/adonet/oracle-distributed-transactions.md)  
 Описывает автоматическое прикрепление объекта <xref:System.Data.OracleClient.OracleConnection> к существующей распределенной транзакции, если эта транзакция активна.  
  
## Связанные подразделы  
 [Защита приложений ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 Описывает приемы безопасного программирования при использовании [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
 [Объекты DataSet, DataTable и DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Описывает процесс создания и использования объектов `DataSets`, типизированных объектов `DataSets`, а также объектов `DataTables` и `DataViews`.  
  
 [Получение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 Описывает работу с данными в ADO.NET.  
  
 [SQL Server и ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)  
 Описывает процесс работы со специальными возможностями и функциями [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].  
  
 [Объекты DbProviderFactory](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 Описывает универсальные классы, позволяющие создавать независимый от поставщика код в [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
## См. также  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)