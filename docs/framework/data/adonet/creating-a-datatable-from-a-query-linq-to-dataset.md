---
title: "Создание таблицы данных из запроса (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1b97afeb-03f8-41e2-8eb3-58aff65f7d18
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a3d28c66cfec1d96ef52dfab9265cf41043e4bf7
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="creating-a-datatable-from-a-query-linq-to-dataset"></a>Создание таблицы данных из запроса (LINQ to DataSet)
Объект <xref:System.Data.DataTable> часто используется для привязки данных. Метод <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> принимает результаты запроса и копирует данные в <xref:System.Data.DataTable>, которую в дальнейшем можно использовать для связывания с данными. После выполнения операций с данными происходит слияние нового объекта <xref:System.Data.DataTable> с исходным объектом <xref:System.Data.DataTable>.  
  
 Метод <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> использует для создания объекта <xref:System.Data.DataTable> на основе запроса следующий процесс.  
  
1.  Метод <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> клонирует объект <xref:System.Data.DataTable> из исходной таблицы (объект <xref:System.Data.DataTable>, реализующий интерфейс <xref:System.Linq.IQueryable%601>). Источник <xref:System.Collections.IEnumerable> обычно создается из выражения [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] или запроса метода.  
  
2.  Схема клонированного объекта <xref:System.Data.DataTable> строится на основе столбцов первого перечисленного объекта <xref:System.Data.DataRow> в исходной таблице, а клонированной таблице присваивается имя исходной таблицы с добавлением слова «query».  
  
3.  Содержимое каждой строки исходной таблицы копируется в новый объект <xref:System.Data.DataRow>, который затем вставляется в клонированную таблицу. Свойства <xref:System.Data.DataRow.RowState%2A> и <xref:System.Data.DataRow.RowError%2A> сохраняются на протяжении операции копирования. Исключение <xref:System.ArgumentException> возникает, если объекты <xref:System.Data.DataRow> в источнике происходят из разных таблиц.  
  
4.  Клонированный объект <xref:System.Data.DataTable> возвращается после копирования всех объектов <xref:System.Data.DataRow> в запрашиваемой входной таблице. Если исходная последовательность не содержит объектов <xref:System.Data.DataRow>, метод возвращает пустой объект <xref:System.Data.DataTable>.  
  
 Следует иметь в виду, что при вызове метода <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> выполняющийся запрос привязывается к исходной таблице.  
  
 Когда метод <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> встречает ссылку NULL или тип значения, допускающий значение NULL, в строке исходной таблицы, это значение будет заменено на <xref:System.DBNull.Value>. Таким образом, значения NULL обрабатываются правильно в возвращаемой таблице <xref:System.Data.DataTable>.  
  
 Примечание. Метод <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> в качестве входных данных принимает запрос, который может возвращать строки из нескольких объектов <xref:System.Data.DataTable> или <xref:System.Data.DataSet>. Метод <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> копирует данные из исходных объектов <xref:System.Data.DataTable> и <xref:System.Data.DataSet> в возвращаемую таблицу <xref:System.Data.DataTable>, но не копирует свойства. Необходимо вручную явно установить свойства возвращаемой таблицы <xref:System.Data.DataTable>, например <xref:System.Data.DataTable.Locale%2A> и <xref:System.Data.DataTable.TableName%2A>.  
  
 В следующем примере выполняется запрос к таблице SalesOrderHeader и возвращаются заказы, сделанные после 8 августа 2001 года, а метод <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> применяется для создания объекта <xref:System.Data.DataTable> на основе этого запроса. Затем объект <xref:System.Data.DataTable> привязывается к источнику <xref:System.Windows.Forms.BindingSource>, который является посредником для объекта <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#CopyToDataTable1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#copytodatatable1)]
 [!code-vb[DP LINQ to DataSet Examples#CopyToDataTable1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#copytodatatable1)]  
  
## <a name="creating-a-custom-copytodatatablet-method"></a>Создание пользовательских CopyToDataTable\<T > метод  
 Существующие методы <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> работают только с источником <xref:System.Collections.Generic.IEnumerable%601>, где общий параметр `T` принадлежит к типу <xref:System.Data.DataRow>. Хотя это и полезно, это не позволяет создавать таблицы из последовательности скалярных типов, из запросов, возвращающих анонимные типы, или из запросов, выполняющих соединение таблиц. Пример реализации пользовательских `CopyToDataTable` методов для загрузки таблицы из последовательности скалярных или анонимных типов, см. [как: реализовать CopyToDataTable\<T > где универсальный тип T не совпадает DataRow](../../../../docs/framework/data/adonet/implement-copytodatatable-where-type-not-a-datarow.md)s.  
  
 В примерах, приведенных в этом разделе, используются следующие пользовательские типы:  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#ItemClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#itemclass)]
 [!code-vb[DP Custom CopyToDataTable Examples#ItemClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#itemclass)]  
  
### <a name="example"></a>Пример  
 В этом примере выполняется соединение в таблицах `SalesOrderHeader` и `SalesOrderDetail` для получения совершенных через Интернет заказов начиная с августа и на основе этого запроса создается таблица.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#join)]
 [!code-vb[DP Custom CopyToDataTable Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#join)]  
  
### <a name="example"></a>Пример  
 В следующем примере выполняется запрос к коллекции для получения элементов, цена которых составляет больше 9,99 доллара США, и на основе результатов этого запроса создается таблица.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsIntoTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsintotable)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsIntoTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsintotable)]  
  
### <a name="example"></a>Пример  
 В следующем примере выполняется запрос к коллекции для получения элементов, цена которых составляет больше 9,99, и результаты запроса проецируются. Возвращаемая последовательность анонимных типов загружается в существующую таблицу.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsIntoExistingTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsintoexistingtable)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsIntoExistingTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsintoexistingtable)]  
  
### <a name="example"></a>Пример  
 В следующем примере выполняется запрос к коллекции для получения элементов, цена которых составляет больше 9,99 доллара США, и результаты запроса проецируются. Возвращаемая последовательность анонимных типов загружается в существующую таблицу. Схема таблицы автоматически расширяется, так как типы `Book` и `Movies` являются производными от типа `Item`.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsExpandSchema](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsexpandschema)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsExpandSchema](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsexpandschema)]  
  
### <a name="example"></a>Пример  
 В следующем примере выполняется запрос к коллекции для получения элементов, цена которых составляет больше 9,99 доллара США, и возвращаемая последовательность значений типа <xref:System.Double> загружается в новую таблицу.  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadScalarSequence](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loadscalarsequence)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadScalarSequence](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loadscalarsequence)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
 [Универсальные методы Field и SetField](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)  
 [Примеры LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
