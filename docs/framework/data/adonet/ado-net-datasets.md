---
title: "Наборы данных ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 82b641bb-6001-4512-bf1a-2830acdd92ab
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Наборы данных ADO.NET
<xref:System.Data.DataSet> является центральным элементом поддержки разъединенных распределенных сценариев данных в [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]. **DataSet** является оперативной памяти представлением данных, обеспечивающим согласованную реляционную программную модель независимо от источника данных. Он может использоваться с несколькими различными источниками данных, XML-данными или для управления данными, локальными по отношению к приложению. **Набора данных** представляет полный набор данных, включая связанные таблицы, ограничения и связи между таблицами. На следующем рисунке показано **DataSet** объектной модели.  
  
 ![График ADO.Net](../../../../docs/framework/data/adonet/media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
Объектная модель DataSet  
  
 Методы и объекты в **DataSet** такие модели реляционной базы данных.  
  
 **DataSet** также можно сохранять и повторно загружать свое содержимое в виде XML и его схемы XML схемы языка XSD. Дополнительные сведения см. в разделе [использование языка XML в набор данных](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="the-datatablecollection"></a>Класс DataTableCollection  
 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] **DataSet** содержит коллекцию ноль или более таблиц, представленных <xref:System.Data.DataTable> объектов. <xref:System.Data.DataTableCollection> содержит все **DataTable** объектов в **набора данных**.  
  
 Объект **DataTable** определяется в <xref:System.Data> пространства имен и представляет собой одну таблицу, находящуюся в оперативной памяти. Он содержит коллекцию столбцов, представленных <xref:System.Data.DataColumnCollection>и ограничений, представленных <xref:System.Data.ConstraintCollection>, которые вместе определяют схему таблицы. Объект **DataTable** также содержит коллекцию строк, представленных <xref:System.Data.DataRowCollection>, которая содержит данные в таблице. Вместе со своим текущим состоянием <xref:System.Data.DataRow> сохраняет обе свои текущие и исходные версии для определения изменения значений, хранимых в строке.  
  
## <a name="the-dataview-class"></a>Класс DataView  
 Объект <xref:System.Data.DataView> позволяет создавать различные представления данных, хранящихся в <xref:System.Data.DataTable>, эта возможность часто используется в приложениях связывания данных. С помощью <xref:System.Data.DataView>, можно представить данные в таблице с различными порядками сортировки, и можно фильтровать данные по состоянию строки или на основе критерия фильтра. Дополнительные сведения см. в разделе [объектов DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
## <a name="the-datarelationcollection"></a>Класс DataRelationCollection  
 Объект **DataSet** содержит связи в его <xref:System.Data.DataRelationCollection> объекта. Связь, представленная <xref:System.Data.DataRelation> объекта, связывает строки в одном **DataTable** со строками в другом **DataTable**. Связь аналогична пути соединения, который может существовать между столбцами первичного и внешнего ключей реляционной базы данных. Объект **DataRelation** определяет совпадающие столбцы в двух таблицах **набора данных**.  
  
 Связи позволяют перемещаться из одной таблицы в другую в **набора данных**. Важными элементами объекта **DataRelation** являются имя связи, имя связанных таблиц и связанные столбцы в каждой таблице. Связи могут быть построены с более чем одним столбцом для каждой таблицы путем указания массива <xref:System.Data.DataColumn> объектов в качестве ключевых столбцов. При добавлении связи к <xref:System.Data.DataRelationCollection>, при необходимости можно добавить **UniqueKeyConstraint** и **ForeignKeyConstraint** чтобы обеспечить ограничения целостности при внесении изменений значений связанных столбцов.  
  
 Дополнительные сведения см. в разделе [Добавление объектов DataRelation](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="xml"></a>XML  
 Можно заполнить **DataSet** из XML-потока или документа. XML-потока или документа можно использовать для предоставления **DataSet** данных, сведения о схеме или оба. Данные из XML-потока или документа можно комбинировать с существующими данными или сведениями схемы, уже имеющимися в **набора данных**. Дополнительные сведения см. в разделе [использование языка XML в набор данных](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="extendedproperties"></a>Свойство ExtendedProperties  
 **DataSet**, **DataTable**, и **DataColumn** имеют **ExtendedProperties** свойство. **Свойство ExtendedProperties** — **PropertyCollection** где можно размещать пользовательские сведения, например инструкцию SELECT, которая использовалась для создания результирующего набора, или время формирования данных. **ExtendedProperties** сохраняется со сведения о схеме для **набора данных**.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] предоставляет возможности выполнения запросов LINQ к кэшированным данным, хранящимся в объекте DataSet. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]использует стандартный [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] синтаксис и обеспечивает проверку синтаксиса во время компиляции, статическую типизацию и поддержку технологии IntelliSense при использовании [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] интегрированной среды разработки.  
  
 Дополнительные сведения см. в разделе [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)   
 [Наборы данных, таблицы данных и объекты DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Извлечение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Управляемые поставщики ADO.NET и Центр разработчиков DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)