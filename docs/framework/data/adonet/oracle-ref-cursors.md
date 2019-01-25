---
title: REF CURSOR в Oracle
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: 4dd0a78fafe63197987938021195723e3eed0885
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741000"
---
# <a name="oracle-ref-cursors"></a>REF CURSOR в Oracle
Поставщик данных .NET Framework для Oracle поддерживает Oracle **REF CURSOR** тип данных. При использовании поставщика данных для работы с данными типа REF CURSOR Oracle необходимо учитывать следующие особенности его функционирования.  
  
> [!NOTE]
>  По некоторым особенностям функционирования он отличается от поставщика Microsoft OLE DB для Oracle (MSDAORA).  
  
-   Для повышения производительности поставщик данных для Oracle не обеспечивает и привязку автоматически **REF CURSOR** типы данных, как MSDAORA, если вы явно не указана.  
  
-   Указанный поставщик данных не поддерживает никаких escape-последовательностей ODBC, включая escape-последовательность {resultset}, используемую для задания параметров REF CURSOR.  
  
-   Чтобы выполнить хранимую процедуру, которая возвращает REF CURSOR, необходимо определить параметры в <xref:System.Data.OracleClient.OracleParameterCollection> с <xref:System.Data.OracleClient.OracleType> из **курсор** и <xref:System.Data.OracleClient.OracleParameter.Direction%2A> из **вывода**. Этот поставщик данных поддерживает привязку данных типа REF CURSOR только в качестве выходных параметров. Этот поставщик не поддерживает данные типа REF CURSOR как входные параметры.  
  
-   Получение модуля <xref:System.Data.OracleClient.OracleDataReader> из значения параметра не поддерживается. Значения имеют тип <xref:System.DBNull> после выполнения команды.  
  
-   Единственным **CommandBehavior** значение перечисления, которое работает с типа REF CURSOR (например, при вызове <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) является **CloseConnection**; все остальные игнорируются.  
  
-   Порядок параметров REF CURSOR в **OracleDataReader** зависит от порядка параметров в **OracleParameterCollection**. Свойство <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> не учитывается.  
  
-   PL/SQL **таблицы** тип данных не поддерживается. Но данные типа REF CURSOR являются более эффективными. Если необходимо использовать **таблицы** тип данных, используйте OLE DB поставщик данных .NET с MSDAORA.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Примеры REF CURSOR](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 Содержит три примера, которые демонстрируют использование данных типа REF CURSOR.  
  
 [Параметры REF CURSOR в объекте OracleDataReader](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 Демонстрирует выполнение PL/SQL хранимой процедуры, возвращает параметр REF CURSOR и считывает значение в виде **OracleDataReader**.  
  
 [Извлечение данных из нескольких REF CURSOR с использованием OracleDataReader](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 Демонстрирует выполнение PL/SQL хранимой процедуры, возвращает два параметра REF CURSOR и считывает значения с использованием **OracleDataReader**.  
  
 [Заполнение DataSet с помощью одного или нескольких параметров REF CURSOR](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 Показывает, как выполнить хранимую процедуру PL/SQL, которая возвращает два параметра REF CURSOR и заполняет <xref:System.Data.DataSet> возвращаемыми строками.  
  
## <a name="see-also"></a>См. также
- [Oracle и ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
