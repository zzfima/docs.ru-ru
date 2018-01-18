---
title: "Добавление существующих ограничений к набору данных"
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
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2f2f6c60197b1d71feb13ca351ad19298e09ea56
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="adding-existing-constraints-to-a-dataset"></a>Добавление существующих ограничений к набору данных
**Заполнения** метод **DataAdapter** заполняет <xref:System.Data.DataSet> только со столбцами таблицы и строки из источника данных; Однако обычно устанавливают ограничения по источнику данных **заполнения** метод не добавляет эти данные схемы к **DataSet** по умолчанию. Для заполнения **DataSet** с существующие ограничения первичного ключа сведения из источника данных, можно вызвать **FillSchema** метод **DataAdapter**, или задать **MissingSchemaAction** свойство **DataAdapter** для **AddWithKey** перед вызовом **заполнения**. Это позволит гарантировать, что первичный ключ ограничений в **DataSet** отражаются в источнике данных. Ограничение внешнего ключа сведения не включено и должны создаваться явно, как показано в [ограничения таблиц данных](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 Добавление сведений о схеме для **DataSet** перед заполнение данных гарантирует, что ограничений primary key включаются с <xref:System.Data.DataTable> объекты в **набора данных**. В результате при дополнительных вызовах для заполнения **набора данных** вносятся первичном сведений о столбце ключей используется для сопоставления новых строк из источника данных с текущим строкам в каждой **DataTable**и текущие данные в таблиц перезаписываются данными из источника данных. Без данных схемы новые строки из источника данных добавляются к **набора данных**, полученный в повторяющихся строк.  
  
> [!NOTE]
>  Если столбец в источнике данных определен как заданы с автоматическим приращением, **FillSchema** метод, или **заполнения** метод с **MissingSchemaAction** из  **AddWithKey**, создает **DataColumn** с **AutoIncrement** свойство `true`. Тем не менее, необходимо задать **AutoIncrementStep** и **AutoIncrementSeed** значения самостоятельно. Дополнительные сведения о столбцах с автоматическим приращением см. в разделе [Создание столбцов AutoIncrement](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).  
  
 С помощью **FillSchema** или параметр **MissingSchemaAction** для **AddWithKey** требует дополнительной обработки в источнике данных, чтобы определить столбец первичного ключа сведения. Такая дополнительная обработка может снизить производительность. Если сведения о столбцах первичного ключа известны во время разработки, рекомендуется явно задавать столбец или столбцы первичного ключа, чтобы добиться оптимальной производительности. Сведения о явном данные первичного ключа для таблицы см. в разделе [Определение первичных ключей](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
 В следующем примере кода показано, как добавить сведения о схеме для **DataSet** с помощью **FillSchema**.  
  
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
  
 В следующем примере кода показано, как добавить сведения о схеме для **DataSet** с помощью **MissingSchemaAction.AddWithKey** свойство **заполнения** метод.  
  
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
  
## <a name="handling-multiple-result-sets"></a>Обработка нескольких результирующих наборов  
 Если **DataAdapter** обнаруживает несколько результирующих наборов, возвращенных **SelectCommand**, он создает несколько таблиц в **набора данных**. Таблицы присваивается имя по умолчанию **таблицы** *N*, начиная с **таблицы** вместо «Table0». Если имя таблицы передается в качестве аргумента для **FillSchema** метод, таблицам будут присваиваться с нуля добавочное имя **TableName** *N*, начиная с **TableName** вместо «TableName0».  
  
> [!NOTE]
>  Если **FillSchema** метод **OleDbDataAdapter** вызывается для команды, которая возвращает несколько результирующих наборов, возвращаются только сведения о схеме из первого результирующего набора. Когда данные схемы возвращаются для нескольких результирующих задает использование **OleDbDataAdapter**, рекомендуется указывать **MissingSchemaAction** из **AddWithKey** и получить сведения о схеме, при вызове **заполнения** метод.  
  
## <a name="see-also"></a>См. также  
 [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Наборы данных, таблицы данных и объекты DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Извлечение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
