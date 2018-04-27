---
title: Наборы данных ADO.NET
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82b641bb-6001-4512-bf1a-2830acdd92ab
caps.latest.revision: 6
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 9458206ea7edfeba61f9805c2b601d6aa9198256
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="adonet-datasets"></a>Наборы данных ADO.NET
Объект <xref:System.Data.DataSet> является центральным элементом поддержки разъединенных распределенных сценариев данных в [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]. **DataSet** является размещенные в оперативной памяти представлением данных, обеспечивающим согласованную реляционную программную модель независимо от источника данных. Он может использоваться с несколькими различными источниками данных, XML-данными или для управления данными, локальными по отношению к приложению. **Набора данных** представляет полный набор данных, включая связанные таблицы, ограничения и связи между таблицами. На следующем рисунке показана **DataSet** объектной модели.  
  
 ![Графика ADO.Net](../../../../docs/framework/data/adonet/media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
Объектная модель DataSet  
  
 Методы и объекты в **DataSet** согласованы с идентификаторами в реляционной базе данных модели.  
  
 **DataSet** также можно сохранять и повторно загружать свое содержимое в виде XML и его схемы XML схемы языка XSD. Дополнительные сведения см. в статье [Использование XML в наборах данных](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="the-datatablecollection"></a>Класс DataTableCollection  
 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] **DataSet** содержит коллекцию из нуля или более таблиц, представленных <xref:System.Data.DataTable> объектов. <xref:System.Data.DataTableCollection> Содержит все **DataTable** объекты в **набора данных**.  
  
 Объект **DataTable** определяется в <xref:System.Data> пространства имен и представляет собой одну таблицу данных в памяти. Он содержит коллекцию столбцов, представленных объектом <xref:System.Data.DataColumnCollection>, и ограничений, представленных объектом <xref:System.Data.ConstraintCollection>, которые вместе определяют схему таблицы. Объект **DataTable** также содержит коллекцию строк, представленных <xref:System.Data.DataRowCollection>, которая содержит данные в таблице. Вместе со своим текущим состоянием объект <xref:System.Data.DataRow> сохраняет обе свои версии (текущую и исходную), чтобы определить изменения значений, хранимых в строке.  
  
## <a name="the-dataview-class"></a>Класс DataView  
 <xref:System.Data.DataView> позволяет создавать различные представления данных, которые хранятся в <xref:System.Data.DataTable>. Эта возможность часто используется в приложениях связывания данных. С помощью объекта <xref:System.Data.DataView> можно представлять данные в таблице с различными порядками сортировки, а также фильтровать данные по состоянию строки или на основе критерия фильтра. Дополнительные сведения см. в разделе [объекты DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
## <a name="the-datarelationcollection"></a>Класс DataRelationCollection  
 Объект **DataSet** содержит связи в его <xref:System.Data.DataRelationCollection> объекта. Связь, представленная <xref:System.Data.DataRelation> объекта, связывает строки в одном **DataTable** со строками в другом **DataTable**. Связь аналогична пути соединения, который может существовать между столбцами первичного и внешнего ключей реляционной базы данных. Объект **DataRelation** определяет совпадающие столбцы в двух таблицах объекта **набора данных**.  
  
 Связи позволяют перемещаться из одной таблицы в другую в **набора данных**. Главные **DataRelation** являются имя связи, имя связанных таблиц и связанные столбцы в каждой таблице. Связи могут быть построены с более чем одним столбцом для каждой таблицы путем указания массива объектов <xref:System.Data.DataColumn> в качестве ключевых столбцов. При добавлении связи к <xref:System.Data.DataRelationCollection>, вы можете добавить **UniqueKeyConstraint** и **ForeignKeyConstraint** для принудительного применения ограничения целостности при изменении связанного столбца значения.  
  
 Дополнительные сведения см. в разделе [Добавление отношений DataRelation](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="xml"></a>XML  
 Можно заполнить **DataSet** из XML-документ или XML-поток. XML-поток или документ можно использовать для предоставления **DataSet** данных, сведения о схеме или оба. Данные, полученные из XML-потока или документа могут быть объединены с существующими данными или сведениями о схеме в **набора данных**. Дополнительные сведения см. в статье [Использование XML в наборах данных](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="extendedproperties"></a>Свойство ExtendedProperties  
 **DataSet**, **DataTable**, и **DataColumn** имеют **ExtendedProperties** свойство. **Свойство ExtendedProperties** — **PropertyCollection** где можно размещать пользовательские сведения, например инструкцию SELECT, которая использовалась для создания результирующего набора, или время формирования данных. **ExtendedProperties** сохраняется со сведения о схеме для **набора данных**.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] предоставляет возможности выполнения запросов LINQ к кэшированным данным, хранящимся в объекте DataSet. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] использует стандартный [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] синтаксис и обеспечивает проверку синтаксиса во время компиляции, статическую типизацию и поддержку технологии IntelliSense при использовании интегрированной среды разработки Visual Studio.  
  
 Дополнительные сведения см. в разделе [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [Наборы данных, таблицы данных и объекты DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Извлечение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
