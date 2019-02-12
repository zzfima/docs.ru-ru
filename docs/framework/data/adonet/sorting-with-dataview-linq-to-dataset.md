---
title: Сортировка с использованием объекта DataView (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 885b3b7b-51c1-42b3-bb29-b925f4f69a6f
ms.openlocfilehash: 63dcfd80cca0db67dfad87c491d607506057a532
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092271"
---
# <a name="sorting-with-dataview-linq-to-dataset"></a>Сортировка с использованием объекта DataView (LINQ to DataSet)
Возможность сортировки данных на основе заданных критериев и их предоставление клиенту с помощью элемента управления в пользовательском интерфейсе - это важный аспект привязки данных. Объект <xref:System.Data.DataView> предоставляет несколько способов сортировки и возврата строк данных, упорядоченных по определенным критериям. В дополнение к его строковых возможностей, упорядочения <xref:System.Data.DataView> также позволяет использовать [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] выражения для условия сортировки. [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] выражения позволяют выполнять гораздо более сложные и мощные операции сортировки, чем сортировка на основе строк. В этом разделе описываются оба подхода к сортировке с помощью объекта <xref:System.Data.DataView>.  
  
## <a name="creating-dataview-from-a-query-with-sorting-information"></a>Создание объекта DataView на основе запроса с данными сортировки  
 Объект <xref:System.Data.DataView> можно создать с помощью запроса [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Если запрос содержит <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.ThenBy%2A>, или <xref:System.Linq.Enumerable.ThenByDescending%2A> выражения в этих предложениях используются в качестве основы для сортировки данных в предложении <xref:System.Data.DataView>. Например, если запрос содержит `Order By…`и `Then By…` предложений, полученный в результате <xref:System.Data.DataView> данные будут упорядочены по обоим указанным столбцам.  
  
 Сортировка на основе выражений является более сложной и мощной операцией сортировки, чем более простая сортировка на основе строк. Следует иметь в виду, что сортировки на основе строк и выражений являются взаимоисключающими. Если сортировка на основе строк <xref:System.Data.DataView.Sort%2A> задается после создания объекта <xref:System.Data.DataView> на основе запроса, то выводимый из запроса фильтр на основе выражений удаляется и не восстанавливается.  
  
 Индекс для <xref:System.Data.DataView> формируется как при создании <xref:System.Data.DataView>, так и при изменении каких-либо сведений о сортировке или фильтрации. Наилучшей производительности можно достичь, если указать критерии сортировки в запросе [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], на основе которого создается объект <xref:System.Data.DataView>, и не менять данные сортировки позднее. Дополнительные сведения см. в разделе [производительность объекта DataView](../../../../docs/framework/data/adonet/dataview-performance.md).  
  
> [!NOTE]
>  В большинстве случаев выражение, используемое для сортировки, не должно иметь побочных эффектов и должно быть детерминированным. Также эти выражения не должны содержать логику, зависящую от заданного количества выполнений, так как операции сортировки могут выполняться любое количество раз.  
  
### <a name="example"></a>Пример  
 В следующем примере выполняется запрос к таблице SalesOrderHeader, а полученные строки упорядочиваются по дате заказа; на основе этого запроса создается объект <xref:System.Data.DataView> и привязывается к <xref:System.Data.DataView><xref:System.Windows.Forms.BindingSource>.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby)]  
  
### <a name="example"></a>Пример  
 В следующем примере запрашивает таблицу SalesOrderHeader и упорядочивает возвращенную строку по Итого к оплате; Создает <xref:System.Data.DataView> из запроса; и привязывает <xref:System.Data.DataView> для <xref:System.Windows.Forms.BindingSource>.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby2)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby2)]  
  
### <a name="example"></a>Пример  
 В следующем примере выполняется запрос к таблице SalesOrderDetail, а полученные строки упорядочиваются по объему заказа, а затем по идентификатору заказа на продажу; на основе этого запроса создается объект <xref:System.Data.DataView> и привязывается к <xref:System.Data.DataView><xref:System.Windows.Forms.BindingSource>.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderbythenby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderbythenby)]  
  
## <a name="using-the-string-based-sort-property"></a>Использование свойства сортировки на основе строк  
 Сортировка объекта <xref:System.Data.DataView> на основе строк также работает и с запросом [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. После создания объекта <xref:System.Data.DataView> на основе запроса [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] можно использовать свойство <xref:System.Data.DataView.Sort%2A> для задания сортировки в объекте <xref:System.Data.DataView>.  
  
 Возможности сортировки на основе строк и выражений являются взаимоисключающими. При задании свойства <xref:System.Data.DataView.Sort%2A> сортировка на основе выражений, унаследованная из запроса, на основе которого был создан объект <xref:System.Data.DataView>, удаляется.  
  
 Дополнительные сведения о строковых <xref:System.Data.DataView.Sort%2A> фильтрации, см. в разделе [Сортировка и фильтрация данных](../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
### <a name="example"></a>Пример  
 В следующем примере объект <xref:System.Data.DataView> создается на основе таблицы Contact, затем выполняется сортировка по фамилиям в возрастающем порядке, а затем по именам в убывающем порядке:  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
### <a name="example"></a>Пример  
 В следующем примере выполняется запрос к таблице Contact, который должен вернуть фамилии, начинающиеся на букву «S».  На основе этого запроса создается объект <xref:System.Data.DataView> и привязывается к объекту <xref:System.Windows.Forms.BindingSource>.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## <a name="clearing-the-sort"></a>Очистка сортировки  
 Данные сортировки для объекта <xref:System.Data.DataView> можно очистить после их задания с помощью свойства <xref:System.Data.DataView.Sort%2A>. Существует два способа очистки данных сортировки <xref:System.Data.DataView>.  
  
-   Задайте для свойства <xref:System.Data.DataView.Sort%2A> значение `null`.  
  
-   Установите свойство <xref:System.Data.DataView.Sort%2A> равным пустой строке.  
  
### <a name="example"></a>Пример  
 В следующем примере объект <xref:System.Data.DataView> создается на основе запроса и данные сортировки очищаются путем установки для свойства <xref:System.Data.DataView.Sort%2A> значения, равного пустой строке:  
  
 [!code-csharp[DP DataView Samples#LDVClearSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort)]
 [!code-vb[DP DataView Samples#LDVClearSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort)]  
  
### <a name="example"></a>Пример  
 В следующем примере объект <xref:System.Data.DataView> создается на основе таблицы Contact и в свойстве <xref:System.Data.DataView.Sort%2A> задается сортировка по фамилиям в убывающем порядке. Затем данные сортировки очищаются путем установки для свойства <xref:System.Data.DataView.Sort%2A> значения `null`:  
  
 [!code-csharp[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort2)]
 [!code-vb[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort2)]  
  
## <a name="see-also"></a>См. также
- [Привязка данных и LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
- [Фильтрация с использованием объекта DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)
- [Сортировка данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546145(v=vs.120))
