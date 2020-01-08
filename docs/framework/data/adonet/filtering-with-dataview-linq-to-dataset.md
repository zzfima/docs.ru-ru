---
title: Фильтрация с использованием объекта DataView (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5632d74a-ff53-4ea7-9fe7-4a148eeb1c68
ms.openlocfilehash: 426e8c43f0ff8af94ab56230cf002637f351cd75
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634863"
---
# <a name="filtering-with-dataview-linq-to-dataset"></a>Фильтрация с использованием объекта DataView (LINQ to DataSet)
Возможность фильтрации данных на основе заданных критериев и их предоставление клиенту с помощью элемента управления в пользовательском интерфейсе - это важный аспект привязки данных. Объект <xref:System.Data.DataView> реализует несколько способов фильтрации и возвращения подмножеств строк данных, отвечающих определенным критериям фильтрации. В дополнение к возможностям фильтрации на основе строк <xref:System.Data.DataView> также предоставляет возможность использования выражений LINQ для критериев фильтрации. Выражения LINQ позволяют выполнять гораздо более сложные и эффективные операции фильтрации, чем фильтрация на основе строк.  
  
 Существует два способа фильтрации данных с помощью объекта <xref:System.Data.DataView>.  
  
- Создание <xref:System.Data.DataView> из LINQ to DataSet запроса с предложением WHERE.  
  
- Используйте существующие возможности фильтрации на основе строк, предоставляемые объектом <xref:System.Data.DataView>.  
  
## <a name="creating-dataview-from-a-query-with-filtering-information"></a>Создание объекта DataView на основе запроса с данными фильтрации  
 Объект <xref:System.Data.DataView> можно создать из LINQ to DataSet запроса. Если запрос содержит предложение `Where`, объект <xref:System.Data.DataView> будет создан с учетом данных фильтрации из этого запроса. Выражение в предложении `Where` используется для определения того, какие строки данных будут включены в объект <xref:System.Data.DataView>, и является основой для фильтра.  
  
 Фильтрация на основе выражений является более сложной и мощной, чем более простая фильтрация на основе строк. Фильтры на основе строк и выражений взаимно исключают друг друга. Если фильтрация на основе строк <xref:System.Data.DataView.RowFilter%2A> задается после создания объекта <xref:System.Data.DataView> на основе запроса, выводимый из запроса фильтр на основе выражений очищается.  
  
> [!NOTE]
> В большинстве случаев выражение, используемое для фильтрации, не должно иметь побочных эффектов и должно быть детерминированным. Также эти выражения не должны содержать логику, зависящую от заданного количества выполнений, так как операции фильтрации могут выполняться любое количество раз.  
  
### <a name="example"></a>Пример  
 В следующем примере выполняется запрос к таблице SalesOrderDetail и возвращаются строки с количеством больше 2, но меньше 6, на основе этого запроса создается объект <xref:System.Data.DataView>, который привязывается к <xref:System.Data.DataView>.  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhere](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywhere)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhere](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywhere)]  
  
### <a name="example"></a>Пример  
 В следующем примере объект <xref:System.Data.DataView> создается на основе заказов, размещенных позже 6 июня 2001 г.:  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhere3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywhere3)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhere3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywhere3)]  
  
### <a name="example"></a>Пример  
 Фильтрация может быть совмещена с сортировкой. В следующем примере объект <xref:System.Data.DataView> создается на основе запроса на получение контактов с фамилией, начинающейся на букву «S», отсортированных сначала по фамилии, а затем по имени:  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhereOrderByThenBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywhereorderbythenby)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhereOrderByThenBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywhereorderbythenby)]  
  
### <a name="example"></a>Пример  
 В следующем примере алгоритм SoundEx используется для поиска контактов с фамилией, сходной с «Zhu». Алгоритм SoundEx реализуется в методе SoundEx.  
  
 [!code-csharp[DP DataView Samples#LDVSoundExFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvsoundexfilter)]
 [!code-vb[DP DataView Samples#LDVSoundExFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvsoundexfilter)]  
  
 SoundEx — это фонетический алгоритм, используемый для индексирования имен по их звучанию на английском языке. Он был разработан в бюро переписи населения США. Метод SoundEx возвращает четырехзначный код имени, состоящий из английской буквы и трех цифр. Буква - это первая буква имени, а цифры обозначают остальные согласные в имени. Сходно звучащие имена имеют одинаковый код SoundEx. Реализация алгоритма SoundEx, используемого в методе SoundEx в предыдущем примере, показана здесь:  
  
 [!code-csharp[DP DataView Samples#SoundEx](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#soundex)]
 [!code-vb[DP DataView Samples#SoundEx](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#soundex)]  
  
## <a name="using-the-rowfilter-property"></a>Использование свойства RowFilter  
 Существующие функции фильтрации на основе строк <xref:System.Data.DataView> по-прежнему работают в контексте LINQ to DataSet. Дополнительные сведения о фильтрации <xref:System.Data.DataView.RowFilter%2A> на основе строк см. в разделе [Сортировка и фильтрация данных](./dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
 В следующем примере объект <xref:System.Data.DataView> создается на основе таблицы Contact, а затем устанавливается свойство <xref:System.Data.DataView.RowFilter%2A> для возврата строк, содержащих контакты с фамилией «Zhu».  
  
 [!code-csharp[DP DataView Samples#LDVRowFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvrowfilter)]
 [!code-vb[DP DataView Samples#LDVRowFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvrowfilter)]  
  
 После создания <xref:System.Data.DataView> из запроса <xref:System.Data.DataTable> или LINQ to DataSet можно использовать свойство <xref:System.Data.DataView.RowFilter%2A>, чтобы указать подмножества строк на основе их значений столбцов. Фильтры на основе строк и выражений взаимно исключают друг друга. Установка свойства <xref:System.Data.DataView.RowFilter%2A> очистит выражение фильтра, выводимое из LINQ to DataSet запроса, и невозможно сбросить выражение фильтра.  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhereSetRowFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywheresetrowfilter)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhereSetRowFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywheresetrowfilter)]  
  
 Чтобы вернуть результаты определенного запроса к данным в противоположность динамическому представлению подмножества данным, можно воспользоваться методами <xref:System.Data.DataView.Find%2A> или <xref:System.Data.DataView.FindRows%2A> класса <xref:System.Data.DataView> вместо установки свойства <xref:System.Data.DataView.RowFilter%2A>. Свойство <xref:System.Data.DataView.RowFilter%2A> используется наилучшим образом в приложении, связываемом с данными, где элемент связывания отображает отфильтрованные результаты. При установке свойства <xref:System.Data.DataView.RowFilter%2A> перестраивается индекс данных, что добавляет нагрузку на приложение и снижает производительность. Методы <xref:System.Data.DataView.Find%2A> и <xref:System.Data.DataView.FindRows%2A> используют текущий индекс, не требуя его перестроения. Если <xref:System.Data.DataView.Find%2A> или <xref:System.Data.DataView.FindRows%2A> планируется вызвать только один раз, следует использовать существующий объект <xref:System.Data.DataView>. Если методы <xref:System.Data.DataView.Find%2A> или <xref:System.Data.DataView.FindRows%2A> планируется вызывать несколько раз, следует создать новый объект <xref:System.Data.DataView> для перестроения индекса столбца, в котором необходимо выполнить поиск, а затем вызвать методы <xref:System.Data.DataView.Find%2A> или <xref:System.Data.DataView.FindRows%2A>. Дополнительные сведения о методах <xref:System.Data.DataView.Find%2A> и <xref:System.Data.DataView.FindRows%2A> см. в разделе [Поиск строк](./dataset-datatable-dataview/finding-rows.md) и [производительности DataView](dataview-performance.md).  
  
## <a name="clearing-the-filter"></a>Очистка фильтра  
 Фильтр для объекта <xref:System.Data.DataView> можно очистить после его задания с помощью свойства <xref:System.Data.DataView.RowFilter%2A>. Фильтр для объекта <xref:System.Data.DataView> можно очистить двумя различными способами.  
  
- Задайте для свойства <xref:System.Data.DataView.RowFilter%2A> значение `null`.  
  
- Установите свойство <xref:System.Data.DataView.RowFilter%2A> равным пустой строке.  
  
### <a name="example"></a>Пример  
 В следующем примере объект <xref:System.Data.DataView> создается на основе запроса, а затем фильтр очищается путем установки для свойства <xref:System.Data.DataView.RowFilter%2A> значения `null`.  
  
 [!code-csharp[DP DataView Samples#LDVClearRowFilter2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearrowfilter2)]
 [!code-vb[DP DataView Samples#LDVClearRowFilter2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearrowfilter2)]  
  
### <a name="example"></a>Пример  
 В следующем примере объект <xref:System.Data.DataView> создается на основе таблицы, задается свойство <xref:System.Data.DataView.RowFilter%2A>, а затем фильтр очищается путем установки для свойства <xref:System.Data.DataView.RowFilter%2A> значения, равного пустой строке.  
  
 [!code-csharp[DP DataView Samples#LDVClearRowFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearrowfilter)]
 [!code-vb[DP DataView Samples#LDVClearRowFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearrowfilter)]  
  
## <a name="see-also"></a>См. также:

- [Привязка данных и LINQ to DataSet](data-binding-and-linq-to-dataset.md)
- [Сортировка с использованием объекта DataView](sorting-with-dataview-linq-to-dataset.md)
