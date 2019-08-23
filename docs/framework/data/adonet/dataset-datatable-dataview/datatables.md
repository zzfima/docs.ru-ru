---
title: DataTables
ms.date: 03/30/2017
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
ms.openlocfilehash: 369855d1aff854b60c251010ec42557b70c093c0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952650"
---
# <a name="datatables"></a>DataTables
Набор данных <xref:System.Data.DataSet> состоит из коллекции таблиц, связей и ограничений. В ADO.NET <xref:System.Data.DataTable> объекты используются для представления таблиц в **наборе данных**. Объект **DataTable** представляет одну таблицу реляционных данных в памяти; данные являются локальными для. NET-приложение, в котором оно находится, но может быть заполнено из источника данных, например Microsoft SQL Server помощью **DataAdapter** . Дополнительные сведения см. в разделе Заполнение [набора данных из DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md).  
  
 Класс **DataTable** является членом пространства имен **System. Data** в библиотеке классов .NET Framework. Можно создавать и использовать **DataTable** независимо или как член **набора данных**, а объекты **DataTable** также можно использовать совместно с другими <xref:System.Data.DataView>.NET Frameworkными объектами, включая. Доступ к коллекции таблиц в **наборе данных** осуществляется через свойство **Tables** объекта **DataSet** .  
  
 Схема или структура таблицы представляется столбцами и ограничениями. Схема **DataTable** определяется с помощью <xref:System.Data.DataColumn> <xref:System.Data.ForeignKeyConstraint> объектов, а также объектов и <xref:System.Data.UniqueConstraint> . Столбцы таблицы могут сопоставляться со столбцами источника данных, содержать вычисляемые значения выражений, автоматически увеличивать значения или содержать значения первичного ключа.  
  
 Помимо схемы, в **DataTable** также должны содержаться строки для хранения и упорядочения данных. Класс <xref:System.Data.DataRow> представляет фактические данные, содержащиеся в таблице. Для получения, вычисления и обработки данных в таблице используется объект **DataRow** и его свойства и методы. При доступе и изменении данных в строке объект **DataRow** сохраняет как текущее, так и исходное состояние.  
  
 С помощью одного или нескольких связанных столбцов таблицы между таблицами можно создавать связи типа «родители-потомки». Связь между объектами **DataTable** создается с помощью <xref:System.Data.DataRelation>. Затем объекты **DataRelation** можно использовать для возврата связанных дочерних или родительских строк определенной строки. Дополнительные сведения см. в разделе [Добавление связей](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)данных.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Создание DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 Объясняет, как создать **таблицу DataTable** и добавить ее в **набор данных**.  
  
 [Определение схемы DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 Содержит сведения о создании и использовании объектов **DataColumn** и ограничений.  
  
 [Управление данными в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 Описывает, как добавлять, изменять и удалять данные таблицы. Объясняет, как использовать события **DataTable** для проверки изменений данных в таблице.  
  
 [Обработка событий DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 Предоставляет сведения о событиях, доступных для использования с **таблицей**данных, включая события при изменении значений столбцов и добавлении или удалении строк.  
  
## <a name="related-sections"></a>Связанные разделы  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Описывает архитектуру и компоненты ADO.NET, а также их использование для получения доступа к существующим источникам данных и управления данными приложения.  
  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Предоставляет сведения о наборе **данных** ADO.NET, включая создание связей между таблицами.  
  
 <xref:System.Data.Constraint>  
 Содержит справочные сведения об объекте **constraint** .  
  
 <xref:System.Data.DataColumn>  
 Содержит справочные сведения об объекте **DataColumn** .  
  
 <xref:System.Data.DataSet>  
 Содержит справочные сведения об объекте **DataSet** .  
  
 <xref:System.Data.DataTable>  
 Содержит справочные сведения о объекте **DataTable** .  
  
 [Общие сведения о библиотеке классов](../../../../standard/class-library-overview.md)  
 Содержит общие сведения о библиотеке классов .NET Framework, включая пространство имен **System** , а также его пространство имен второго уровня, **System. Data**.  
  
## <a name="see-also"></a>См. также

- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
