---
title: "Добавление существующих ограничений к DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Добавление существующих ограничений к DataSet
Метод **Fill** объекта **DataAdapter** заполняет <xref:System.Data.DataSet> только столбцами таблицы и строками из источника данных. Хотя источники данных обычно устанавливают ограничения, метод **Fill** по умолчанию не добавляет эти данные схемы к набору данных **DataSet**.  Чтобы учесть при заполнении набора данных **DataSet** существующие ограничения первичного ключа, заданные в источнике данных, можно вызвать метод **FillSchema** объекта **DataAdapter** или задать значение свойства **MissingSchemaAction** объекта **DataAdapter**, равное **AddWithKey**, перед вызовом метода **Fill**.  Тем самым ограничения первичного ключа в наборе данных **DataSet** будут соответствовать ограничениям первичного ключа в источнике данных.  Данные об ограничениях внешнего ключа не добавляются; их нужно создавать явно, как показано в [Ограничения DataTable](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 Добавление данных схемы в **DataSet** перед его заполнением обеспечивает включение ограничений первичного ключа в объекты <xref:System.Data.DataTable> набора данных **DataSet**.  В результате при дополнительных вызовах для заполнения **DataSet** данные столбца первичного ключа используются для проверки соответствия новых строк из источника данных текущим строкам в каждой таблице **DataTable** и текущие данные таблиц перезаписываются данными из источника.  При отсутствии данных схемы новые строки добавляются из источника данных к набору данных **DataSet**, что приводит к появлению повторяющихся строк.  
  
> [!NOTE]
>  Если столбец в источнике данных определен как столбец автоприращения, метод **FillSchema** или **Fill** со свойством **MissingSchemaAction**, имеющим значение **AddWithKey**, создает столбец **DataColumn**, свойство которого **AutoIncrement** имеет значение `true`.  Но выполнение задачи присваивания значений свойств **AutoIncrementStep** и **AutoIncrementSeed** необходимо взять на себя.  Дополнительные сведения о столбцах автоприращения см. в разделе [Создание столбцов AutoIncrement](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).  
  
 Использование метода **FillSchema** или присвоение свойству **MissingSchemaAction** значения **AddWithKey** требует дополнительной обработки в источнике данных, чтобы определить сведения о столбцах первичного ключа.  Такая дополнительная обработка может снизить производительность.  Если сведения о столбцах первичного ключа известны во время разработки, рекомендуется явно задавать столбец или столбцы первичного ключа, чтобы добиться оптимальной производительности.  Сведения о явной установке данных первичного ключа таблицы см. в разделе [Определение первичных ключей](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
 В следующем примере кода показано добавление данных схемы в объект **DataSet** с помощью метода **FillSchema**.  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 В следующем примере кода показано добавление данных схемы в объект **DataSet** с помощью свойства **MissingSchemaAction.AddWithKey** метода **Fill**.  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## Обработка нескольких результирующих наборов  
 Если **DataAdapter** получит несколько результирующих наборов, возвращенных **SelectCommand**, в наборе **DataSet** создается несколько таблиц.  Эти таблицы по умолчанию получают имя **Table** *N* с последовательно увеличивающимся суффиксом, но начиная с **Table**, а не с «Table0».  Если имя таблицы передается в качестве аргумента методу **FillSchema**, то таблицы получают имя **TableName** *N* с отсчитываемым от нуля и последовательно увеличивающимся суффиксом, но начиная с **TableName**, а не с «TableName0».  
  
> [!NOTE]
>  Если вызывается метод **FillSchema** объекта **OleDbDataAdapter** для команды, возвращающей несколько результирующих наборов, возвращаются только данные схемы из первого результирующего набора.  Если данные схемы возвращаются для нескольких результирующих наборов с помощью объекта **OleDbDataAdapter**, рекомендуется задать свойство **MissingSchemaAction** со значением **AddWithKey** и получить данные схемы, вызвав метод **Fill**.  
  
## См. также  
 [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [Объекты DataSet, DataTable и DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Получение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)