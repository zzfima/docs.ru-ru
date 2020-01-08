---
title: Сортировка с использованием объекта DataView (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 885b3b7b-51c1-42b3-bb29-b925f4f69a6f
ms.openlocfilehash: 2998de7dee34f9b5410bfe53988e0b7cfa797784
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634759"
---
# <a name="sorting-with-dataview-linq-to-dataset"></a>Сортировка с использованием объекта DataView (LINQ to DataSet)
Возможность сортировки данных на основе заданных критериев и их предоставление клиенту с помощью элемента управления в пользовательском интерфейсе - это важный аспект привязки данных. Объект <xref:System.Data.DataView> предоставляет несколько способов сортировки и возврата строк данных, упорядоченных по определенным критериям. В дополнение к возможностям сортировки на основе строк, <xref:System.Data.DataView> также позволяет использовать LINQ-выражения для критериев сортировки. Выражения LINQ позволяют выполнять гораздо более сложные и эффективные операции сортировки, чем сортировка на основе строк. В этом разделе описываются оба подхода к сортировке с помощью объекта <xref:System.Data.DataView>.  
  
## <a name="creating-dataview-from-a-query-with-sorting-information"></a>Создание объекта DataView на основе запроса с данными сортировки  
 Объект <xref:System.Data.DataView> можно создать из LINQ to DataSet запроса. Если этот запрос содержит предложение <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.ThenBy%2A>или <xref:System.Linq.Enumerable.ThenByDescending%2A>, то выражения в этих предложениях используются в качестве базиса для сортировки данных в <xref:System.Data.DataView>. Например, если запрос содержит предложения `Order By…`и `Then By…`, то результирующая <xref:System.Data.DataView> будет упорядочивать данные по обоим указанным столбцам.  
  
 Сортировка на основе выражений является более сложной и мощной операцией сортировки, чем более простая сортировка на основе строк. Следует иметь в виду, что сортировки на основе строк и выражений являются взаимоисключающими. Если сортировка на основе строк <xref:System.Data.DataView.Sort%2A> задается после создания объекта <xref:System.Data.DataView> на основе запроса, то выводимый из запроса фильтр на основе выражений удаляется и не восстанавливается.  
  
 Индекс для <xref:System.Data.DataView> формируется как при создании <xref:System.Data.DataView>, так и при изменении каких-либо сведений о сортировке или фильтрации. Вы получаете максимальную производительность, предоставляя критерии сортировки в LINQ to DataSet запросе, из которого создается <xref:System.Data.DataView>, и не изменяет сведения о сортировке позже. Дополнительные сведения см. в разделе [производительность DataView](dataview-performance.md).  
  
> [!NOTE]
> В большинстве случаев выражение, используемое для сортировки, не должно иметь побочных эффектов и должно быть детерминированным. Также эти выражения не должны содержать логику, зависящую от заданного количества выполнений, так как операции сортировки могут выполняться любое количество раз.  
  
### <a name="example"></a>Пример  
 В следующем примере выполняется запрос к таблице SalesOrderHeader, а полученные строки упорядочиваются по дате заказа; на основе этого запроса создается объект <xref:System.Data.DataView> и привязывается к <xref:System.Data.DataView>.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby)]  
  
### <a name="example"></a>Пример  
 В следующем примере выполняется запрос к таблице SalesOrderHeader, а полученные строки упорядочиваются по общей стоимости; на основе этого запроса создается объект <xref:System.Data.DataView> и привязывается к <xref:System.Data.DataView>.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby2)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby2)]  
  
### <a name="example"></a>Пример  
 В следующем примере выполняется запрос к таблице SalesOrderDetail, а полученные строки упорядочиваются по объему заказа, а затем по идентификатору заказа на продажу; на основе этого запроса создается объект <xref:System.Data.DataView> и привязывается к <xref:System.Data.DataView>.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderbythenby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderbythenby)]  
  
## <a name="using-the-string-based-sort-property"></a>Использование свойства сортировки на основе строк  
 Функции сортировки на основе строк <xref:System.Data.DataView> по-прежнему работают с LINQ to DataSet. После создания <xref:System.Data.DataView> из LINQ to DataSet запроса можно использовать свойство <xref:System.Data.DataView.Sort%2A>, чтобы задать сортировку в <xref:System.Data.DataView>.  
  
 Возможности сортировки на основе строк и выражений являются взаимоисключающими. При задании свойства <xref:System.Data.DataView.Sort%2A> сортировка на основе выражений, унаследованная из запроса, на основе которого был создан объект <xref:System.Data.DataView>, удаляется.  
  
 Дополнительные сведения о фильтрации <xref:System.Data.DataView.Sort%2A> на основе строк см. в разделе [Сортировка и фильтрация данных](./dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
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
  
- Задайте для свойства <xref:System.Data.DataView.Sort%2A> значение `null`.  
  
- Установите свойство <xref:System.Data.DataView.Sort%2A> равным пустой строке.  
  
### <a name="example"></a>Пример  
 В следующем примере объект <xref:System.Data.DataView> создается на основе запроса и данные сортировки очищаются путем установки для свойства <xref:System.Data.DataView.Sort%2A> значения, равного пустой строке:  
  
 [!code-csharp[DP DataView Samples#LDVClearSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort)]
 [!code-vb[DP DataView Samples#LDVClearSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort)]  
  
### <a name="example"></a>Пример  
 В следующем примере объект <xref:System.Data.DataView> создается на основе таблицы Contact и в свойстве <xref:System.Data.DataView.Sort%2A> задается сортировка по фамилиям в убывающем порядке. Затем данные сортировки очищаются путем установки для свойства <xref:System.Data.DataView.Sort%2A> значения `null`:  
  
 [!code-csharp[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort2)]
 [!code-vb[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort2)]  
  
## <a name="see-also"></a>См. также:

- [Привязка данных и LINQ to DataSet](data-binding-and-linq-to-dataset.md)
- [Фильтрация с использованием объекта DataView](filtering-with-dataview-linq-to-dataset.md)
- [Сортировка данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546145(v=vs.120))
