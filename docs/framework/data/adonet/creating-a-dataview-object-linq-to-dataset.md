---
title: Создание объекта DataView (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76057508-e12d-4779-a707-06a4c2568acf
ms.openlocfilehash: bd39b40864703b6bb24c2cc6590787562f3f4f98
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504151"
---
# <a name="creating-a-dataview-object-linq-to-dataset"></a>Создание объекта DataView (LINQ to DataSet)
Существует два способа создания <xref:System.Data.DataView> в LINQ to DataSet контекста. Можно создать <xref:System.Data.DataView> из LINQ для запросов набора данных к <xref:System.Data.DataTable>, или ее можно создать из типизированного или нетипизированного <xref:System.Data.DataTable>. В обоих случаях вы создадите <xref:System.Data.DataView> с помощью одного из <xref:System.Data.DataTableExtensions.AsDataView%2A> методы расширения; <xref:System.Data.DataView> не напрямую создать в LINQ to DataSet контекста.  
  
 После создания объекта <xref:System.Data.DataView> его можно привязать к элементу управления в пользовательском интерфейсе приложения Windows Forms или ASP.NET либо изменить параметры фильтрации и сортировки.  
  
 Объект <xref:System.Data.DataView> создает индекс, значительно повышающий производительность операций, использующих этот индекс, таких как фильтрация и сортировка. Индекс для <xref:System.Data.DataView> формируется как при создании <xref:System.Data.DataView>, так и при изменении каких-либо сведений о сортировке или фильтрации. Создание <xref:System.Data.DataView> и последующее задание сведений о сортировке или фильтрации приводит как минимум к двукратному построению индекса - при создании <xref:System.Data.DataView> и при изменении каких-либо свойств сортировки или фильтрации.  
  
 Дополнительные сведения о фильтрации и сортировке с <xref:System.Data.DataView>, см. в разделе [фильтрации с использованием объекта DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md) и [сортировка с использованием объекта DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md).  
  
## <a name="creating-dataview-from-a-linq-to-dataset-query"></a>Создание объекта DataView на основе запроса LINQ to DataSet  
 Объект <xref:System.Data.DataView> объект может быть создан в результате выполнения LINQ запрос к набору данных, где результаты являются проекцией <xref:System.Data.DataRow> объектов. Созданный объект <xref:System.Data.DataView> наследует сведения о фильтрации и сортировке из запроса, на основе которого он был создан.  
  
> [!NOTE]
>   В большинстве случаев выражение, используемое для фильтрации и сортировки, не должно иметь побочных эффектов и должно быть детерминированным. Также эти выражения не должны содержать логику, зависящую от заданного количества выполнений, так как операции фильтрации и сортировки могут выполняться любое количество раз.  
  
 Не поддерживается создание объектов <xref:System.Data.DataView> на основе запросов, возвращающих анонимные типы, или запросов, содержащих операции соединения.  
  
 В запросах, на основе которых создаются объекты <xref:System.Data.DataView>, поддерживаются только следующие операторы запросов:  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Cast%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.OrderBy%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.OrderByDescending%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.ThenBy%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.ThenByDescending%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Where%2A>  
  
 Обратите внимание, что при <xref:System.Data.DataView> создается на основе LINQ для запроса к набору данных <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A> метод должен быть завершающим методом, вызываемым в запросе. Это показано в следующем примере, который создает <xref:System.Data.DataView> online заказов, отсортированных по сумме заказа:  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquery1)]
 [!code-vb[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquery1)]  
  
 Можно также использовать строковые <xref:System.Data.DataView.RowFilter%2A> и <xref:System.Data.DataView.Sort%2A> свойства для сортировки и фильтрации <xref:System.Data.DataView> после его создания на основе запроса. Обратите внимание, что при этом сведения о сортировке и фильтрации, унаследованные из запроса, будут удалены. В следующем примере создается <xref:System.Data.DataView> с LINQ для запроса набора данных, выполняющего фильтрацию по фамилии, начинающиеся с помощью элемента ". Строковое свойство <xref:System.Data.DataView.Sort%2A> задает сортировку по фамилиям в возрастающем порядке, а затем по именам в убывающем порядке:  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## <a name="creating-a-dataview-from-a-datatable"></a>Создание объекта DataView на основе DataTable  
 В дополнение к, созданные из LINQ для запроса набора данных, <xref:System.Data.DataView> объект может быть создан из <xref:System.Data.DataTable> с помощью <xref:System.Data.DataTableExtensions.AsDataView%2A> метод.  
  
 В следующем примере объект <xref:System.Data.DataView> создается на основе таблицы SalesOrderDetail и становится источником данных для объекта <xref:System.Windows.Forms.BindingSource>. Этот объект выступает в роли посредника для элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromtable)]
 [!code-vb[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromtable)]  
  
 Фильтрацию и сортировку для объекта <xref:System.Data.DataView> можно задать после его создания на основе таблицы <xref:System.Data.DataTable>. В следующем примере объект <xref:System.Data.DataView> создается на основе таблицы Contact, и в свойстве <xref:System.Data.DataView.Sort%2A> задается сортировка по фамилиям в возрастающем порядке, а затем по именам в убывающем порядке:  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
 Однако задание свойств <xref:System.Data.DataView.RowFilter%2A> или <xref:System.Data.DataView.Sort%2A> после создания объекта <xref:System.Data.DataView> на основе запроса приводит к потере производительности, так как объект <xref:System.Data.DataView> строит индекс для поддержки операций фильтрации и сортировки. При установке свойств <xref:System.Data.DataView.RowFilter%2A> или <xref:System.Data.DataView.Sort%2A> перестраивается индекс данных, что добавляет нагрузку на приложение и снижает производительность. Если возможно, лучше указать сведения о фильтрации и сортировке при создании объекта <xref:System.Data.DataView> и избежать необходимости изменять его позднее.  
  
## <a name="see-also"></a>См. также

- [Привязка данных и LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
- [Фильтрация с использованием объекта DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)
- [Сортировка с использованием объекта DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)
