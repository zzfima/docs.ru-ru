---
title: Oracle и ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 5683f2b4ba57021ff6dda3a51baca016f886b605
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980084"
---
# <a name="oracle-and-adonet"></a>Oracle и ADO.NET
> [!NOTE]
> Типы в пространстве имен <xref:System.Data.OracleClient> считаются устаревшими. Эти типы по-прежнему поддерживаются в платформе .NET Framework текущей версии, однако будут удалены в следующем выпуске. Корпорация Майкрософт рекомендует использовать поставщик Oracle, предоставляемый сторонними разработчиками.  
  
 В этом разделе описываются функции и поведения, характерные для поставщика данных .NET Framework для Oracle.  
  
 Поставщик данных .NET Framework для Oracle предоставляет доступ к базе данных Oracle с помощью интерфейса Oracle Call Interface (OCI), предоставляемого клиентским программным обеспечением Oracle. Функциональные возможности поставщика данных аналогичны функциям .NET Framework поставщиков данных для SQL Server, OLE DB и ODBC.  
  
 Чтобы использовать поставщик данных .NET Framework для Oracle, приложение должно ссылаться на пространство имен <xref:System.Data.OracleClient> следующим образом:  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 Также при компиляции кода необходимо включить ссылку на библиотеку DLL. Например, при компиляции программы C# командная строка должна включать:  
  
```console
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a>В этом разделе  
 [Требования к системе](system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 Описывает требования к использованию поставщика данных .NET Framework для Oracle и описывает ряд проблем, которые необходимо учитывать при их использовании.  
  
 [BFILE в Oracle](oracle-bfiles.md)  
 Описывает класс <xref:System.Data.OracleClient.OracleBFile>, который используется для работы с типом данных Oracle BFILE.  
  
 [Большие объекты (LOB) в Oracle](oracle-lobs.md)  
 Описывает класс <xref:System.Data.OracleClient.OracleLob>, который используется для работы с типом данных Oracle LOB.  
  
 [REF CURSOR в Oracle](oracle-ref-cursors.md)  
 Описывает поддержку для типа данных Oracle REF CURSOR.  
  
 [OracleTypes](oracletypes.md)  
 Описывает структуры, которые можно использовать с типами данных Oracle, включая <xref:System.Data.OracleClient.OracleNumber> и <xref:System.Data.OracleClient.OracleString>.  
  
 [Последовательности Oracle](oracle-sequences.md)  
 Описывает поддержку получения сформированного сервером ключа значений Oracle Sequence.  
  
 [Сопоставления типов данных Oracle](oracle-data-type-mappings.md)  
 Перечисляет типы данных Oracle и их сопоставление с объектом <xref:System.Data.OracleClient.OracleDataReader>.  
  
 [Распределенные транзакции Oracle](oracle-distributed-transactions.md)  
 Описывает автоматическое прикрепление объекта <xref:System.Data.OracleClient.OracleConnection> к существующей распределенной транзакции, если эта транзакция активна.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Защита приложений ADO.NET](securing-ado-net-applications.md)  
 Описывает приемы безопасного программирования при использовании ADO.NET.  
  
 [Наборы данных, таблицы данных и объекты DataView](./dataset-datatable-dataview/index.md)  
 Описывает процесс создания и использования объектов `DataSets`, типизированных объектов `DataSets`, а также объектов `DataTables` и `DataViews`.  
  
 [Извлечение и изменение данных в ADO.NET](retrieving-and-modifying-data.md)  
 Описывает работу с данными в ADO.NET.  
  
 [SQL Server и ADO.NET](./sql/index.md)  
 Описывает процесс работы со специальными возможностями и функциями SQL Server.  
  
 [DbProviderFactories](dbproviderfactories.md)  
 Описывает универсальные классы, позволяющие писать независимый от поставщика код в ADO.NET.  
  
## <a name="see-also"></a>См. также:

- [ADO.NET](index.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
