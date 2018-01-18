---
title: DataTables
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 439b951779393d6ac232e6a1a622515905e837ad
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="datatables"></a>DataTables
Набор данных <xref:System.Data.DataSet> состоит из коллекции таблиц, связей и ограничений. В ADO.NET <xref:System.Data.DataTable> объекты используются для представления таблиц в **набора данных**. Объект **DataTable** представляет одну таблицу находящихся в памяти реляционных данных; является локальным для данных. NET-приложение в котором он находится, но могут быть заполнены из источника данных, например Microsoft SQL Server с помощью **DataAdapter** Дополнительные сведения см. в разделе [заполнение DataSet из объекта DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md) .  
  
 **DataTable** входит класс **System.Data** пространство имен в библиотеке классов .NET Framework. Можно создать и использовать **DataTable** отдельно или как член **DataSet**, и **DataTable** объекты могут также использоваться в сочетании с другими объектами .NET Framework включая <xref:System.Data.DataView>. Можно получить доступ к коллекции таблиц в **DataSet** через **таблиц** свойство **набора данных** объекта.  
  
 Схема или структура таблицы представляется столбцами и ограничениями. Определения схемы **DataTable** с помощью <xref:System.Data.DataColumn> объектов в том числе в <xref:System.Data.ForeignKeyConstraint> и <xref:System.Data.UniqueConstraint> объектов. Столбцы таблицы могут сопоставляться со столбцами источника данных, содержать вычисляемые значения выражений, автоматически увеличивать значения или содержать значения первичного ключа.  
  
 Кроме схемы **DataTable** должен также иметь строки, содержащие и данные о заказах. Класс <xref:System.Data.DataRow> представляет фактические данные, содержащиеся в таблице. Вы используете **DataRow** и его свойства и методы для извлечения, оценки и обработки данных в таблице. Как открывать и изменять данные в строке, **DataRow** сохраняет свое текущее и исходное состояние.  
  
 С помощью одного или нескольких связанных столбцов таблицы между таблицами можно создавать связи типа «родители-потомки». Создать связь между **DataTable** объектов с помощью <xref:System.Data.DataRelation>. **DataRelation** объекты могут затем использоваться для возврата связанных дочерних или родительских строк определенной строки. Дополнительные сведения см. в разделе [Добавление отношений DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Создание DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 Описание способов создания **DataTable** и добавьте его в **набора данных**.  
  
 [Определение схемы DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 Содержит сведения о создании и использовании **DataColumn** объектов и ограничений.  
  
 [Управление данными в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 Описывает, как добавлять, изменять и удалять данные таблицы. Описание способов использования **DataTable** событий для изучения изменений данных в таблице.  
  
 [Обработка событий DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 Предоставляет сведения о событиях, доступных для использования с **DataTable**, включая события, связанные с изменением значений столбцов и добавлением или удалением строк.  
  
## <a name="related-sections"></a>Связанные разделы  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Описывает архитектуру и компоненты ADO.NET, а также их использование для получения доступа к существующим источникам данных и управления данными приложения.  
  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Предоставляет сведения о ADO.NET **DataSet** включая создание связей между таблицами.  
  
 <xref:System.Data.Constraint>  
 Содержит справочные сведения о **ограничение** объекта.  
  
 <xref:System.Data.DataColumn>  
 Содержит справочные сведения о **DataColumn** объекта.  
  
 <xref:System.Data.DataSet>  
 Содержит справочные сведения о **DataSet** объекта.  
  
 <xref:System.Data.DataTable>  
 Содержит справочные сведения о **DataTable** объекта.  
  
 [Общие сведения о библиотеке классов](../../../../../docs/standard/class-library-overview.md)  
 Общие сведения о библиотеке классов .NET Framework, включая **системы** пространства имен и пространство имен второго уровня **System.Data**.  
  
## <a name="see-also"></a>См. также  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
