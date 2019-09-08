---
title: Создание объекта DataView (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76057508-e12d-4779-a707-06a4c2568acf
ms.openlocfilehash: 054898a3520cbc2b607fc26b94b72b9896ad9c71
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786682"
---
# <a name="creating-a-dataview-object-linq-to-dataset"></a>Создание объекта DataView (LINQ to DataSet)
Существует два способа создания <xref:System.Data.DataView> в контексте LINQ to DataSet. Можно создать объект <xref:System.Data.DataView> из LINQ to DataSet запроса к <xref:System.Data.DataTable>или создать его из типизированного или нетипизированного <xref:System.Data.DataTable>. В обоих случаях создается <xref:System.Data.DataView> с помощью одного <xref:System.Data.DataTableExtensions.AsDataView%2A> из методов расширения; <xref:System.Data.DataView> не конструируемым непосредственно в контексте LINQ to DataSet.  
  
 После создания объекта <xref:System.Data.DataView> его можно привязать к элементу управления в пользовательском интерфейсе приложения Windows Forms или ASP.NET либо изменить параметры фильтрации и сортировки.  
  
 Объект <xref:System.Data.DataView> создает индекс, значительно повышающий производительность операций, использующих этот индекс, таких как фильтрация и сортировка. Индекс для <xref:System.Data.DataView> формируется как при создании <xref:System.Data.DataView>, так и при изменении каких-либо сведений о сортировке или фильтрации. Создание <xref:System.Data.DataView> и последующее задание сведений о сортировке или фильтрации приводит как минимум к двукратному построению индекса - при создании <xref:System.Data.DataView> и при изменении каких-либо свойств сортировки или фильтрации.  
  
 Дополнительные сведения о фильтрации и сортировке с <xref:System.Data.DataView>помощью см. в разделе [Фильтрация с помощью DataView](filtering-with-dataview-linq-to-dataset.md) и [Сортировка с помощью DataView](sorting-with-dataview-linq-to-dataset.md).  
  
## <a name="creating-dataview-from-a-linq-to-dataset-query"></a>Создание объекта DataView на основе запроса LINQ to DataSet  
 Объект может быть создан на основе результатов запроса LINQ to DataSet, где результаты представляют собой <xref:System.Data.DataRow> проекцию объектов. <xref:System.Data.DataView> Созданный объект <xref:System.Data.DataView> наследует сведения о фильтрации и сортировке из запроса, на основе которого он был создан.  
  
> [!NOTE]
> В большинстве случаев выражение, используемое для фильтрации и сортировки, не должно иметь побочных эффектов и должно быть детерминированным. Также эти выражения не должны содержать логику, зависящую от заданного количества выполнений, так как операции фильтрации и сортировки могут выполняться любое количество раз.  
  
 Не поддерживается создание объектов <xref:System.Data.DataView> на основе запросов, возвращающих анонимные типы, или запросов, содержащих операции соединения.  
  
 В запросах, на основе которых создаются объекты <xref:System.Data.DataView>, поддерживаются только следующие операторы запросов:  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Cast%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.OrderBy%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.OrderByDescending%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.ThenBy%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.ThenByDescending%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Where%2A>  
  
 Обратите внимание, <xref:System.Data.DataView> что при создании из LINQ to DataSet <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A> запроса метод должен быть последним методом, вызываемым в запросе. Это показано в следующем примере, в котором создается <xref:System.Data.DataView> веб-заказы, отсортированные по общему количеству.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquery1)]
 [!code-vb[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquery1)]  
  
 Можно также использовать строковые <xref:System.Data.DataView.RowFilter%2A> и <xref:System.Data.DataView.Sort%2A> свойства <xref:System.Data.DataView> для фильтрации и сортировки после создания из запроса. Обратите внимание, что при этом сведения о сортировке и фильтрации, унаследованные из запроса, будут удалены. В следующем примере создается объект <xref:System.Data.DataView> из LINQ to DataSet запроса, который фильтрует по фамилиям, начинающимся с «». Строковое свойство <xref:System.Data.DataView.Sort%2A> задает сортировку по фамилиям в возрастающем порядке, а затем по именам в убывающем порядке:  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## <a name="creating-a-dataview-from-a-datatable"></a>Создание объекта DataView на основе DataTable  
 В дополнение к созданию из LINQ to DataSet запроса <xref:System.Data.DataView> объект можно создать <xref:System.Data.DataTable> из с помощью <xref:System.Data.DataTableExtensions.AsDataView%2A> метода.  
  
 В следующем примере объект <xref:System.Data.DataView> создается на основе таблицы SalesOrderDetail и становится источником данных для объекта <xref:System.Windows.Forms.BindingSource>. Этот объект выступает в роли посредника для элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromtable)]
 [!code-vb[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromtable)]  
  
 Фильтрацию и сортировку для объекта <xref:System.Data.DataView> можно задать после его создания на основе таблицы <xref:System.Data.DataTable>. В следующем примере объект <xref:System.Data.DataView> создается на основе таблицы Contact, и в свойстве <xref:System.Data.DataView.Sort%2A> задается сортировка по фамилиям в возрастающем порядке, а затем по именам в убывающем порядке:  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
 Однако задание свойств <xref:System.Data.DataView.RowFilter%2A> или <xref:System.Data.DataView.Sort%2A> после создания объекта <xref:System.Data.DataView> на основе запроса приводит к потере производительности, так как объект <xref:System.Data.DataView> строит индекс для поддержки операций фильтрации и сортировки. При установке свойств <xref:System.Data.DataView.RowFilter%2A> или <xref:System.Data.DataView.Sort%2A> перестраивается индекс данных, что добавляет нагрузку на приложение и снижает производительность. Если возможно, лучше указать сведения о фильтрации и сортировке при создании объекта <xref:System.Data.DataView> и избежать необходимости изменять его позднее.  
  
## <a name="see-also"></a>См. также

- [Привязка данных и LINQ to DataSet](data-binding-and-linq-to-dataset.md)
- [Фильтрация с использованием объекта DataView](filtering-with-dataview-linq-to-dataset.md)
- [Сортировка с использованием объекта DataView](sorting-with-dataview-linq-to-dataset.md)
