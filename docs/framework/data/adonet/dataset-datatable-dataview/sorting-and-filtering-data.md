---
title: "Сортировка и фильтрация данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Сортировка и фильтрация данных
<xref:System.Data.DataView> предоставляет несколько способов сортировки и фильтрации данных в <xref:System.Data.DataTable>.  
  
-   Можно использовать свойство <xref:System.Data.DataView.Sort%2A> для задания одного или нескольких порядков сортировки столбцов и включить параметры ASC \(по возрастанию\) и DESC \(по убыванию\).  
  
-   Свойство <xref:System.Data.DataView.ApplyDefaultSort%2A> служит для автоматического создания порядка сортировки по возрастанию на основании столбца или столбцов первичного ключа таблицы.  <xref:System.Data.DataView.ApplyDefaultSort%2A> применяется только в том случае, если свойство **Sort** является ссылкой со значением NULL или пустой строкой, а в таблице определен первичный ключ.  
  
-   Свойство <xref:System.Data.DataView.RowFilter%2A> можно использовать для задания подмножеств строк на основании значений их столбцов.  Подробные сведения о допустимых выражениях для свойства **RowFilter** см. в справочных сведениях для свойства <xref:System.Data.DataColumn.Expression%2A> класса <xref:System.Data.DataColumn>.  
  
     Чтобы вернуть результаты определенного запроса к данным \(а не динамическое представление подмножества данных\), можно воспользоваться методами <xref:System.Data.DataView.Find%2A> или <xref:System.Data.DataView.FindRows%2A> класса **DataView** для достижения большей производительности, а не выполнять настройку свойства **RowFilter**.  При установке свойства **RowFilter** перестраивается индекс данных, что добавляет нагрузку на приложение и снижает производительность.  Свойство **RowFilter** используется наилучшим образом в привязанном к данным приложении, где элемент связывания отображает отфильтрованные результаты.  Методы **Find** и **FindRows** используют текущий индекс, не требуя его перестроения.  Дополнительные сведения о методах **Find** и **FindRows** см. в разделе [поиск строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).  
  
-   Свойство <xref:System.Data.DataView.RowStateFilter%2A> можно использовать для определения, какие версии строк следует просматривать.  **DataView** неявно регулирует выбор версии строк, которая должна представляться, в зависимости от базовой строки **RowState**.  Например, если для **RowStateFilter** установлено **DataViewRowState.Deleted**, **DataView** представляет версию строки **Original** из всех строк **Deleted**, т.к. нет версии строки **Current**.  Какая версия строки представляется, можно определить при помощи свойства **RowVersion** для **DataRowView**.  
  
     В следующей таблице показаны параметры для **DataViewRowState**.  
  
    |Параметры DataViewRowState|Описание|  
    |--------------------------------|--------------|  
    |**CurrentRows**|Версия строки **Current** из всех строк **Unchanged**, **Added** и **Modified**.  Это значение по умолчанию.|  
    |**Added**|Версия строки **Current** из всех строк **Added**.|  
    |**Deleted**|Версия строки **Original** из всех строк **Deleted**.|  
    |**ModifiedCurrent**|Версия строки **Current** из всех строк **Modified**.|  
    |**ModifiedOriginal**|Версия строки **Original** из всех строк **Modified**.|  
    |**Нет**|Нет строк.|  
    |**OriginalRows**|Версия строки **Original** из всех строк **Unchanged**, **Modified** и **Deleted**.|  
    |**Unchanged**|Версия строки **Current** из всех строк **Unchanged**.|  
  
 Дополнительные сведения о состояниях и версиях строк см. в разделе [Состояния и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
 В следующем примере кода создается представление, которое показывает все продукты, где число элементов на складе меньше или равно уровню переупорядочения, отсортированного вначале по идентификаторам поставщиков, а затем по названиям продуктов.  
  
```vb  
Dim prodView As DataView = New DataView(prodDS.Tables("Products"), _  
   "UnitsInStock <= ReorderLevel", _  
   "SupplierID, ProductName", _  
   DataViewRowState.CurrentRows)  
  
```  
  
```csharp  
DataView prodView = new DataView(prodDS.Tables["Products"],  
   "UnitsInStock <= ReorderLevel",  
   "SupplierID, ProductName",  
   DataViewRowState.CurrentRows);  
```  
  
## См. также  
 <xref:System.Data.DataViewRowState>   
 <xref:System.Data.DataColumn.Expression%2A?displayProperty=fullName>   
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataView>   
 [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)