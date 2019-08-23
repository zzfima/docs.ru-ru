---
title: REF CURSOR в Oracle
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: 7c6b326b15a2af58da9206adf28070e57fec600c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963510"
---
# <a name="oracle-ref-cursors"></a>REF CURSOR в Oracle
Поставщик данных .NET Framework для Oracle поддерживает тип данных Oracle **ref Cursor** . При использовании поставщика данных для работы с данными типа REF CURSOR Oracle необходимо учитывать следующие особенности его функционирования.  
  
> [!NOTE]
> По некоторым особенностям функционирования он отличается от поставщика Microsoft OLE DB для Oracle (MSDAORA).  
  
- По соображениям производительности поставщик данных для Oracle не привязывает типы данных **ссылочных курсоров** автоматически, как если бы они явно не заданы.  
  
- Указанный поставщик данных не поддерживает никаких escape-последовательностей ODBC, включая escape-последовательность {resultset}, используемую для задания параметров REF CURSOR.  
  
- Для выполнения хранимой процедуры, возвращающей ссылки REF CURSOR, необходимо <xref:System.Data.OracleClient.OracleParameterCollection> определить параметры в <xref:System.Data.OracleClient.OracleType> с помощью курсора и <xref:System.Data.OracleClient.OracleParameter.Direction%2A> **выходных данных**. Этот поставщик данных поддерживает привязку данных типа REF CURSOR только в качестве выходных параметров. Этот поставщик не поддерживает данные типа REF CURSOR как входные параметры.  
  
- Получение модуля <xref:System.Data.OracleClient.OracleDataReader> из значения параметра не поддерживается. Значения имеют тип <xref:System.DBNull> после выполнения команды.  
  
- Единственным значением перечисления **CommandBehavior** , которое работает с ключевыми курсорами (например, при вызове <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>), является **клосеконнектион**; все остальные игнорируются.  
  
- Порядок ССЫЛОЧных КУРСОРов в **OracleDataReader** зависит от порядка параметров в **OracleParameterCollection**. Свойство <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> не учитывается.  
  
- Табличный тип данных PL/SQL не поддерживается. Но данные типа REF CURSOR являются более эффективными. Если необходимо использовать табличный тип данных, используйте поставщик данных OLE DB .NET с MSDAORA.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Примеры REF CURSOR](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 Содержит три примера, которые демонстрируют использование данных типа REF CURSOR.  
  
 [Параметры REF CURSOR в объекте OracleDataReader](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 Демонстрирует выполнение хранимой процедуры PL/SQL, возвращающей параметр REF CURSOR, и считывание значения в виде **OracleDataReader**.  
  
 [Извлечение данных из нескольких REF CURSOR с использованием OracleDataReader](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 Демонстрирует выполнение хранимой процедуры PL/SQL, возвращающей два параметра REF CURSOR, и считывание значений с помощью **OracleDataReader**.  
  
 [Заполнение DataSet с помощью одного или нескольких параметров REF CURSOR](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 Показывает, как выполнить хранимую процедуру PL/SQL, которая возвращает два параметра REF CURSOR и заполняет <xref:System.Data.DataSet> возвращаемыми строками.  
  
## <a name="see-also"></a>См. также

- [Oracle и ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
