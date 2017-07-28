---
title: "Курсоры REF CURSOR в Oracle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Курсоры REF CURSOR в Oracle
Поставщик данных .NET Framework для Oracle поддерживает тип данных **REF CURSOR** Oracle.  При использовании поставщика данных для работы с данными типа REF CURSOR Oracle необходимо учитывать следующие особенности его функционирования.  
  
> [!NOTE]
>  По некоторым особенностям функционирования он отличается от поставщика Microsoft OLE DB для Oracle \(MSDAORA\).  
  
-   В целях повышения производительности поставщик данных для Oracle, в отличие от MSDAORA, не выполняет автоматически привязку типов данных **REF CURSOR**, если это не задано явно.  
  
-   Указанный поставщик данных не поддерживает никаких escape\-последовательностей ODBC, включая escape\-последовательность {resultset}, используемую для задания параметров REF CURSOR.  
  
-   Чтобы выполнить хранимую процедуру, которая возвращает данные типа REF CURSOR, необходимо определить параметры в <xref:System.Data.OracleClient.OracleParameterCollection> с помощью свойства <xref:System.Data.OracleClient.OracleType> объекта **Cursor** и свойства <xref:System.Data.OracleClient.OracleParameter.Direction%2A> объекта **Output**.  Этот поставщик данных поддерживает связывание данных типа REF CURSOR только в качестве выходных параметров.  Этот поставщик не поддерживает данные типа REF CURSOR как входные параметры.  
  
-   Получение модуля <xref:System.Data.OracleClient.OracleDataReader> из значения параметра не поддерживается.  Значения имеют тип <xref:System.DBNull> после выполнения команды.  
  
-   Единственным значением перечисления **CommandBehavior**, которое может применяться для работы с данными типа REF CURSOR \(например, при вызове <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>\), является **CloseConnection**; все прочие значения не учитываются.  
  
-   Последовательность расположения данных типа REF CURSOR в объекте **OracleDataReader** зависит от последовательности параметров в коллекции **OracleParameterCollection**.  Свойство <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> не учитывается.  
  
-   Тип данных **TABLE** языка PL\/SQL не поддерживается.  Но данные типа REF CURSOR являются более эффективными.  Если возникает необходимость в использовании типа данных **TABLE**, используйте поставщика данных OLE DB .NET с MSDAORA.  
  
## В этом подразделе  
 [Примеры курсоров REF CURSOR](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 Содержит три примера, которые демонстрируют использование данных типа REF CURSOR.  
  
 [Параметры REF CURSOR в OracleDataReader](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 Показывает, как выполнить хранимую процедуру PL\/SQL, которая возвращает параметр REF CURSOR и считывает значение как **OracleDataReader**.  
  
 [Извлечение данных из нескольких курсоров REF CURSOR с помощью OracleDataReader](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 Показывает, как выполнить хранимую процедуру PL\/SQL, которая возвращает два параметра REF CURSOR и считывает значения с использованием **OracleDataReader**.  
  
 [Заполнение набора данных с помощью одного или нескольких параметров REF CURSOR](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 Показывает, как выполнить хранимую процедуру PL\/SQL, которая возвращает два параметра REF CURSOR и заполняет <xref:System.Data.DataSet> возвращаемыми строками.  
  
## См. также  
 [Oracle и ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)