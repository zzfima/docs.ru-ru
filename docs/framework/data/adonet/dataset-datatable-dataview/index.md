---
title: "Объекты DataSet, DataTable и DataView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Объекты DataSet, DataTable и DataView
ADO.NET <xref:System.Data.DataSet> \- расположенное в оперативной памяти представление данных, обеспечивающее согласованную реляционную программную модель независимо от источника данных.  <xref:System.Data.DataSet> представляет полный набор данных, включая таблицы, содержащие, упорядочивающие и ограничивающие данные, а также связи между таблицами.  
  
 Существует несколько способов работы с <xref:System.Data.DataSet>, которые могут применяться отдельно или в сочетании.  Можно выполнить следующие действия.  
  
-   Программно создать <xref:System.Data.DataTable>, <xref:System.Data.DataRelation> и <xref:System.Data.Constraint> внутри <xref:System.Data.DataSet> и заполнить таблицы данными.  
  
-   Заполнить <xref:System.Data.DataSet> таблицами данных из существующего реляционного источника данных с помощью `DataAdapter`.  
  
-   Загрузить и сохранить содержимое <xref:System.Data.DataSet> с помощью XML\-кода.  Для получения дополнительной информации см. [Использование XML в DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
 Строго типизированный <xref:System.Data.DataSet> также можно передавать с помощью веб\-службы с поддержкой XML\-кода.  Конструкция <xref:System.Data.DataSet> делает его идеальным для передачи данных с помощью веб\-служб с поддержкой XML\-кода.  Общие сведения о веб\-службах с поддержкой XML\-кода см. в разделе [XML Web Services Overview](http://msdn.microsoft.com/ru-ru/9db0c7b8-bca6-462b-9be5-f5f9a7f05a4d).  Пример использования данных <xref:System.Data.DataSet> из веб\-службы с поддержкой XML см. в разделе [Использование данных из DataSet в веб\-службе XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md).  
  
## В этом подразделе  
 [Создание DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataset.md)  
 Описывает синтаксис, необходимый для создания экземпляра <xref:System.Data.DataSet>.  
  
 [Добавление DataTable в DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-a-datatable-to-a-dataset.md)  
 Описывает создание и добавление таблиц и столбцов в <xref:System.Data.DataSet>.  
  
 [Добавление объектов DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 Описывает создание связей между таблицами <xref:System.Data.DataSet>.  
  
 [Перемещение по связям DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md)  
 Описывает использование связей между таблицами <xref:System.Data.DataSet> для возвращения дочерних или родительских строк связи типа «родитель\-потомок».  
  
 [Объединение содержимого DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md)  
 Описывает процесс слияния содержимого одного <xref:System.Data.DataSet>, <xref:System.Data.DataTable> или массива <xref:System.Data.DataRow> с <xref:System.Data.DataSet>.  
  
 [Копирование содержимого объекта DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md)  
 Описывает создание копии <xref:System.Data.DataSet>, которая может содержать схему, а также указанные данные.  
  
 [Обработка событий наборов данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataset-events.md)  
 Описывает события <xref:System.Data.DataSet> и их использование.  
  
 [Типизированные объекты DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 Обсуждается, что такое типизированный <xref:System.Data.DataSet> и как его создавать и использовать.  
  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 Описывает создание <xref:System.Data.DataTable>, определение схемы и управление данными.  
  
 [DataTableReaders](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 Описывает создание и использование <xref:System.Data.DataTableReader>.  
  
 [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 Описывает создание `DataViews` и работу с ними, а также работу с событиями <xref:System.Data.DataView>.  
  
 [Использование XML в DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Описывает взаимодействие <xref:System.Data.DataSet> с XML\-данными в качестве источника данных, включая загрузку и сохранение содержимого <xref:System.Data.DataSet> в виде XML\-данных.  
  
 [Использование данных из DataSet в веб\-службе XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md)  
 Описывает создание веб\-службы с поддержкой XML, использующей <xref:System.Data.DataSet> для передачи данных.  
  
## Связанные подразделы  
 [Новые возможности ADO.NET](../../../../../docs/framework/data/adonet/whats-new.md)  
 Представляет новые возможности ADO.NET.  
  
 [Общие сведения об ADO.NET](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 Содержит введение в структуру и компоненты ADO.NET.  
  
 [Заполнение набора данных с помощью адаптера данных DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 Описывает загрузку **DataSet** данными из источника данных.  
  
 [Обновление источников данных с помощью объектов DataAdapter](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 Описывает решение по внесению измененных в **DataSet** данных обратно в источник данных.  
  
 [Добавление существующих ограничений к DataSet](../../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 Описывает заполнение **DataSet** сведениями о первичном ключе из источника данных.  
  
## См. также  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)