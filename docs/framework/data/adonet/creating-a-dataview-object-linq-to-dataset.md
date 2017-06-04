---
title: "Создание объекта DataView (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 76057508-e12d-4779-a707-06a4c2568acf
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Создание объекта DataView (LINQ to DataSet)
Объект <xref:System.Data.DataView> в контексте [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] можно создать двумя способами.  Можно создать объект <xref:System.Data.DataView> на основе запроса [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] к таблице <xref:System.Data.DataTable> или на основе типизированной или нетипизированной таблицы <xref:System.Data.DataTable>.  В обоих случаях объект <xref:System.Data.DataView> создается с помощью одного из методов расширений <xref:System.Data.DataTableExtensions.AsDataView%2A>; объект <xref:System.Data.DataView> нельзя напрямую создать в контексте [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  
  
 После создания объекта <xref:System.Data.DataView> его можно привязать к элементу управления в пользовательском интерфейсе приложения Windows Forms или ASP.NET либо изменить параметры фильтрации и сортировки.  
  
 Объект <xref:System.Data.DataView> создает индекс, значительно повышающий производительность операций, использующих этот индекс, таких как фильтрация и сортировка.  Индекс для <xref:System.Data.DataView> формируется как при создании <xref:System.Data.DataView>, так и при изменении каких\-либо сведений о сортировке или фильтрации.  Создание <xref:System.Data.DataView> и последующее задание сведений о сортировке или фильтрации приводит как минимум к двукратному построению индекса \- при создании <xref:System.Data.DataView> и при изменении каких\-либо свойств сортировки или фильтрации.  
  
 Дополнительные сведения о фильтрации и сортировке с помощью <xref:System.Data.DataView> см. в разделах [Фильтрация с помощью DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md) и [Сортировка с помощью DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md).  
  
## Создание объекта DataView на основе запроса LINQ to DataSet  
 Объект <xref:System.Data.DataView> можно создать на основе результатов запроса [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], которые являются проекцией объектов <xref:System.Data.DataRow>.  Созданный объект <xref:System.Data.DataView> наследует сведения о фильтрации и сортировке из запроса, на основе которого он был создан.  
  
> [!NOTE]
>  В большинстве случаев выражение, используемое для фильтрации и сортировки, не должно иметь побочных эффектов и должно быть детерминированным.  Также эти выражения не должны содержать логику, зависящую от заданного количества выполнений, так как операции фильтрации и сортировки могут выполняться любое количество раз.  
  
 Не поддерживается создание объектов <xref:System.Data.DataView> на основе запросов, возвращающих анонимные типы, или запросов, содержащих операции соединения.  
  
 В запросах, на основе которых создаются объекты <xref:System.Data.DataView>, поддерживаются только следующие операторы запросов:  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.Cast%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.OrderBy%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.OrderByDescending%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.ThenBy%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.ThenByDescending%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.Where%2A>  
  
 Обратите внимание, что при создании объекта <xref:System.Data.DataView> на основе запроса [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] метод <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A> должен являться завершающим методом, вызываемым в запросе. Это показано в следующем примере, иллюстрирующем создание объекта <xref:System.Data.DataView> из совершенных через Интернет заказов, отсортированных по сумме заказа:  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquery1)]
 [!code-vb[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquery1)]  
  
 Также для фильтрации и сортировки объекта <xref:System.Data.DataView> после его создания из запроса можно использовать строковые свойства <xref:System.Data.DataView.RowFilter%2A> и <xref:System.Data.DataView.Sort%2A>.  Обратите внимание, что при этом сведения о сортировке и фильтрации, унаследованные из запроса, будут удалены.  В следующем примере показано создание объекта <xref:System.Data.DataView> на основе запроса [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], выполняющего фильтрацию по фамилиям, начинающимся с буквы «С».  Строковое свойство <xref:System.Data.DataView.Sort%2A> задает сортировку по фамилиям в возрастающем порядке, а затем по именам в убывающем порядке:  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## Создание объекта DataView на основе DataTable  
 Кроме запроса [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], объект <xref:System.Data.DataView> может быть также создан и на основе объекта <xref:System.Data.DataTable> с помощью метода <xref:System.Data.DataTableExtensions.AsDataView%2A>.  
  
 В следующем примере объект <xref:System.Data.DataView> создается на основе таблицы SalesOrderDetail и становится источником данных для объекта <xref:System.Windows.Forms.BindingSource>.  Этот объект выступает в роли посредника для элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromtable)]
 [!code-vb[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromtable)]  
  
 Фильтрацию и сортировку для объекта <xref:System.Data.DataView> можно задать после его создания на основе таблицы <xref:System.Data.DataTable>.  В следующем примере объект <xref:System.Data.DataView> создается на основе таблицы Contact, и в свойстве <xref:System.Data.DataView.Sort%2A> задается сортировка по фамилиям в возрастающем порядке, а затем по именам в убывающем порядке:  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
 Однако задание свойств <xref:System.Data.DataView.RowFilter%2A> или <xref:System.Data.DataView.Sort%2A> после создания объекта <xref:System.Data.DataView> на основе запроса приводит к потере производительности, так как объект <xref:System.Data.DataView> строит индекс для поддержки операций фильтрации и сортировки.  При установке свойств <xref:System.Data.DataView.RowFilter%2A> или <xref:System.Data.DataView.Sort%2A> перестраивается индекс данных, что добавляет нагрузку на приложение и снижает производительность.  Если возможно, лучше указать сведения о фильтрации и сортировке при создании объекта <xref:System.Data.DataView> и избежать необходимости изменять его позднее.  
  
## См. также  
 [Связывание с данными и LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)   
 [Фильтрация с помощью DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)   
 [Сортировка с помощью DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)