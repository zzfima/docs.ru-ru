---
title: Добавление существующих ограничений к набору данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: 90aa1e5dceb3cac87d330837496b9dc467dc1876
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44260062"
---
# <a name="adding-existing-constraints-to-a-dataset"></a>Добавление существующих ограничений к набору данных
**Заполнения** метод **DataAdapter** заполняет <xref:System.Data.DataSet> только со столбцами таблицы и строки из источника данных; Однако обычно устанавливают ограничения источником данных, **заполнения** метод не добавляет эти данные схемы к **набора данных** по умолчанию. Для заполнения **набора данных** сведениями о существующие ограничения первичного ключа из источника данных, можно вызвать метод **FillSchema** метод **DataAdapter**, или задать **MissingSchemaAction** свойство **DataAdapter** для **AddWithKey** перед вызовом **заполнения**. Это позволит гарантировать, что первичный ключ ограничения в **набора данных** отражаются в источнике данных. Ограничение внешнего ключа сведения не включается и нужно создавать явно, как показано в [ограничения таблиц данных](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 Добавление сведений о схеме для **набора данных** прежде, чем заполнение данных гарантирует, что ограничения первичного ключа входят в состав <xref:System.Data.DataTable> объекты в **набора данных**. В результате при дополнительных вызовах для заполнения **набора данных** вносятся основной сведения о ключевом столбце используется для проверки соответствия новых строк из источника данных текущим строкам в каждом **DataTable**и текущие данные в таблиц перезаписываются данными из источника данных. Без данных схемы новые строки из источника данных, добавляются к **набора данных**, полученный в повторяющихся строк.  
  
> [!NOTE]
>  Если столбец в источнике данных определен как заданы с автоматическим приращением, **FillSchema** метод, или **заполнения** метод с **MissingSchemaAction** из  **AddWithKey**, создает **DataColumn** с **AutoIncrement** свойство значение `true`. Тем не менее, вам потребуется задать **AutoIncrementStep** и **AutoIncrementSeed** значения самостоятельно. Дополнительные сведения о столбцах автоприращения см. в разделе [Создание столбцов AutoIncrement](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).  
  
 С помощью **FillSchema** или параметр **MissingSchemaAction** для **AddWithKey** требует дополнительной обработки в источнике данных, чтобы определить столбец первичного ключа сведения. Такая дополнительная обработка может снизить производительность. Если сведения о столбцах первичного ключа известны во время разработки, рекомендуется явно задавать столбец или столбцы первичного ключа, чтобы добиться оптимальной производительности. Сведения о явном задании сведения о первичном ключе таблицы, см. в разделе [Определение первичных ключей](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
 В следующем примере кода показано, как добавить сведения о схеме для **набора данных** с помощью **FillSchema**.  
  
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
  
 В следующем примере кода показано, как добавить сведения о схеме для **набора данных** с помощью **MissingSchemaAction.AddWithKey** свойство **заполнения** метод.  
  
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
 Если **DataAdapter** обнаруживает несколько результирующих наборов, возвращенных **SelectCommand**, он создаст несколько таблиц в **набора данных**. Таблицы, получает имя по умолчанию **таблицы** *N*, начиная с **таблицы** вместо «Table0». Если имя таблицы передается в качестве аргумента для **FillSchema** метода таблиц Получает отсчитываемый от нуля добавочное имя **TableName** *N*, начиная с **TableName** вместо «TableName0».  
  
> [!NOTE]
>  Если **FillSchema** метод **OleDbDataAdapter** объекта вызывается для команды, которая возвращает несколько результирующих наборов, возвращаются только сведения о схеме из первого результирующего набора. Если данные схемы возвращаются для нескольких результирующих наборов с помощью **OleDbDataAdapter**, рекомендуется указывать **MissingSchemaAction** из **AddWithKey** и получить сведения о схеме, при вызове **заполнения** метод.  
  
## <a name="see-also"></a>См. также  
 [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Наборы данных, таблицы данных и объекты DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Извлечение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
