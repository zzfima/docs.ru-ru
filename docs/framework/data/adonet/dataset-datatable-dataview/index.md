---
title: Наборы данных, таблицы данных и объекты DataView
ms.date: 03/30/2017
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
ms.openlocfilehash: abfb53b0a7d827ffe8df909746c0c0ad0ce8c57b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64750753"
---
# <a name="datasets-datatables-and-dataviews"></a>Наборы данных, таблицы данных и объекты DataView
ADO.NET <xref:System.Data.DataSet> - расположенное в оперативной памяти представление данных, обеспечивающее согласованную реляционную программную модель независимо от источника данных. <xref:System.Data.DataSet> представляет полный набор данных, включая таблицы, содержащие, упорядочивающие и ограничивающие данные, а также связи между таблицами.  
  
 Существует несколько способов работы с <xref:System.Data.DataSet>, которые могут применяться отдельно или в сочетании. Можно выполнить следующие действия:   
  
- Программно создать <xref:System.Data.DataTable>, <xref:System.Data.DataRelation> и <xref:System.Data.Constraint> внутри <xref:System.Data.DataSet> и заполнить таблицы данными.  
  
- Заполнить <xref:System.Data.DataSet> таблицами данных из существующего реляционного источника данных с помощью `DataAdapter`.  
  
- Загрузить и сохранить содержимое <xref:System.Data.DataSet> с помощью XML-кода. Дополнительные сведения см. в статье [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
 Строго типизированный <xref:System.Data.DataSet> также можно передавать с помощью веб-службы с поддержкой XML-кода. Конструкция <xref:System.Data.DataSet> делает его идеальным для передачи данных с помощью веб-служб с поддержкой XML-кода. Общие сведения об XML-веб-службах см. в разделе [Общие сведения об XML-веб-службах](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)). Пример использования <xref:System.Data.DataSet> из XML-веб-службы см. в разделе [Потребление набора данных из веб-службы XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Создание набора данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataset.md)  
 Описывает синтаксис, необходимый для создания экземпляра <xref:System.Data.DataSet>.  
  
 [Добавление новой таблицы данных в набор данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-a-datatable-to-a-dataset.md)  
 Описывает создание и добавление таблиц и столбцов в <xref:System.Data.DataSet>.  
  
 [Добавление отношений DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 Описывает создание связей между таблицами <xref:System.Data.DataSet>.  
  
 [Навигация по отношениям DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md)  
 Описывает использование связей между таблицами <xref:System.Data.DataSet> для возвращения дочерних или родительских строк связи типа «родитель-потомок».  
  
 [Слияние содержимого набора данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md)  
 Описывает процесс слияния содержимого одного <xref:System.Data.DataSet>, <xref:System.Data.DataTable> или массива <xref:System.Data.DataRow> с <xref:System.Data.DataSet>.  
  
 [Копирование содержимого набора данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md)  
 Описывает создание копии <xref:System.Data.DataSet>, которая может содержать схему, а также указанные данные.  
  
 [Обработка событий наборов данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataset-events.md)  
 Описывает события <xref:System.Data.DataSet> и их использование.  
  
 [Типизированные наборы данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 Обсуждается, что такое типизированный <xref:System.Data.DataSet> и как его создавать и использовать.  
  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 Описывает создание <xref:System.Data.DataTable>, определение схемы и управление данными.  
  
 [Объекты DataTableReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 Описывает создание и использование <xref:System.Data.DataTableReader>.  
  
 [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 Описывает создание `DataViews` и работу с ними, а также работу с событиями <xref:System.Data.DataView>.  
  
 [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Описывает взаимодействие <xref:System.Data.DataSet> с XML-данными в качестве источника данных, включая загрузку и сохранение содержимого <xref:System.Data.DataSet> в виде XML-данных.  
  
 [Потребление набора данных из веб-службы XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md)  
 Описывает создание веб-службы с поддержкой XML, использующей <xref:System.Data.DataSet> для передачи данных.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Новые возможности в ADO.NET](../../../../../docs/framework/data/adonet/whats-new.md)  
 Представляет новые возможности ADO.NET.  
  
 [Общие сведения об ADO.NET](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 Содержит введение в структуру и компоненты ADO.NET.  
  
 [Заполнение набора данных с помощью адаптера данных DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 Описывается загрузка **DataSet** данными из источника данных.  
  
 [Обновление источников данных с объектами DataAdapter](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 Описывается решение по внесению измененных в **DataSet** данных обратно в источник данных.  
  
 [Добавление существующих ограничений к набору данных](../../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 Описывает заполнение **DataSet** сведениями о первичном ключе из источника данных.  
  
## <a name="see-also"></a>См. также

- [ADO.NET](../../../../../docs/framework/data/adonet/index.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
