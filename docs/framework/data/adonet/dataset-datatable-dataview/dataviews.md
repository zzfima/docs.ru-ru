---
title: "Объекты DataView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Объекты DataView
<xref:System.Data.DataView> позволяет создавать различные представления данных, которые хранятся в <xref:System.Data.DataTable>. Эта возможность часто используется в приложениях связывания данных.  С помощью класса **DataView** можно представить данные в таблице с различными порядками сортировки и отфильтровать их по состоянию строки или критерию фильтра.  
  
 Класс **DataView** обеспечивает динамическое представление данных базового класса **DataTable** \- содержимое, упорядочение и членство отображают изменения по мере их появления.  В этом состоит отличие от метода **Select** класса **DataTable**, который возвращает массив <xref:System.Data.DataRow> из таблицы на основе определенного фильтра или порядка сортировки \- этосодержимое отражает изменения в базовой таблице, но при этом членство и упорядочение будут статическими.  Благодаря динамическим возможностям класс **DataView** идеально подходит для приложений связывания данных.  
  
 **DataView** обеспечивает динамическое представление единого набора данных во многом похожего на представление базы данных, к которому можно применить различные критерии сортировки и фильтрации.  Однако, в отличие от представления базы данных, класс **DataView** нельзя обрабатывать как таблицу, и он не может обеспечить представление соединяемых таблиц.  Кроме того, нельзя исключать столбцы, существующие в исходной таблице, добавлять столбцы \(например, вычисляемые\), которых нет в исходной таблице.  
  
 Управлять настройками представления для всех таблиц в объекте **DataSet** можно с помощью класса <xref:System.Data.DataView.DataViewManager%2A>.  Класс **DataViewManager** является удобным средством для управления настройками представления по умолчанию для каждой таблицы.  При привязке элемента управления к нескольким таблицам класса **DataSet** привязка к **DataViewManager** будет идеальным выбором.  
  
## В этом подразделе  
 [Создание DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 Описывает создание **DataView** для **DataTable**.  
  
 [Сортировка и фильтрация данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 Описывает настройку возврата подмножества строк данных, соответствующих определенным условиям фильтра, или возврата данных в определенном порядке сортировки, с помощью свойств **DataView**.  
  
 [Объекты DataRow и DataRowView ](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 Описывает способы доступа к данным, представленным классом **DataView**.  
  
 [поиск строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 Описывает способы поиска конкретной строки в **DataView**.  
  
 [Объекты ChildView и связи](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 Описывает создание представлений из связи типа «родители\-потомки» с помощью класса **DataView**.  
  
 [изменение DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 Описывает способы изменения данных в базовом объекте **DataTable** через **DataView**, в том числе включение и отключение обновлений.  
  
 [Обработка событий DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 Описывает получение уведомления при обновлении содержимого или порядка **DataView** с помощью события **ListChanged**.  
  
 [Управление объектами DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 Описывает управление настройками **DataView** для каждой таблицы в **DataSet** с помощью класса **DataViewManager**.  
  
## Связанные подразделы  
 [ASP.NET Web Applications](http://msdn.microsoft.com/ru-ru/a812d7b7-049e-4234-a4c2-6acf690301f6)  
 Описывает обзоры и подробные пошаговые инструкции по созданию приложений ASP.NET, Web Forms и веб\-служб.  
  
 [Windows Applications](http://msdn.microsoft.com/ru-ru/a6bb2180-09b1-4738-b9fd-7fb05fc92f23)  
 Содержит подробные сведения о работе с консольными приложениями и Windows Forms.  
  
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Описывает объект **DataSet** и способы управления данными приложений с его помощью.  
  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 Описывает объект **DataTable** и способы управления данными приложений самостоятельно или в составе **DataSet** с его помощью.  
  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Описывает архитектуру и компоненты ADO.NET, а также использование ADO.NET для доступа к существующим источникам данных и управления данными приложений.  
  
## См. также  
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)