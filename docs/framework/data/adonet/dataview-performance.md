---
title: Производительность объекта DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 90820e49-9d46-41f6-9a3d-6c0741bbd8eb
ms.openlocfilehash: 7c81619bf4ac6ed084ea63349345dbf3b7f139b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150692"
---
# <a name="dataview-performance"></a>Производительность объекта DataView
В этом разделе обсуждается повышение производительности при использования методов <xref:System.Data.DataView.Find%2A> и <xref:System.Data.DataView.FindRows%2A> класса <xref:System.Data.DataView>, а также при кэшировании объекта <xref:System.Data.DataView> в веб-приложении.  
  
## <a name="find-and-findrows"></a>Find и FindRows  
 Объект <xref:System.Data.DataView> создает индекс. Индекс содержит ключи, построенные из одного или нескольких столбцов в таблице или представлении. Эти ключи хранятся в виде структуры сбалансированного дерева, которая поддерживает быстрый поиск строк по их ключевым значениям в объекте <xref:System.Data.DataView>. Операции, в которые используется индекс, такие как фильтрация и сортировка, значительно повышают производительность. Индекс для <xref:System.Data.DataView> формируется как при создании <xref:System.Data.DataView>, так и при изменении каких-либо сведений о сортировке или фильтрации. Создание <xref:System.Data.DataView> и последующее задание сведений о сортировке или фильтрации приводит как минимум к двукратному построению индекса - при создании <xref:System.Data.DataView> и при изменении каких-либо свойств сортировки или фильтрации. Для получения дополнительной информации о <xref:System.Data.DataView>фильтрации и сортировке с помощью, см. [Фильтрация с DataView](filtering-with-dataview-linq-to-dataset.md) и [сортировка с DataView](sorting-with-dataview-linq-to-dataset.md).  
  
 Чтобы вернуть результаты определенного запроса к данным в противоположность динамическому представлению подмножества данным, можно воспользоваться методами <xref:System.Data.DataView.Find%2A> или <xref:System.Data.DataView.FindRows%2A> класса <xref:System.Data.DataView> вместо установки свойства <xref:System.Data.DataView.RowFilter%2A>. Свойство <xref:System.Data.DataView.RowFilter%2A> используется наилучшим образом в приложении, связываемом с данными, где элемент связывания отображает отфильтрованные результаты. При установке свойства <xref:System.Data.DataView.RowFilter%2A> перестраивается индекс данных, что добавляет нагрузку на приложение и снижает производительность. Методы <xref:System.Data.DataView.Find%2A> и <xref:System.Data.DataView.FindRows%2A> используют текущий индекс, не требуя его перестроения. Если <xref:System.Data.DataView.Find%2A> или <xref:System.Data.DataView.FindRows%2A> планируется вызвать только один раз, следует использовать существующий объект <xref:System.Data.DataView>. Если методы <xref:System.Data.DataView.Find%2A> или <xref:System.Data.DataView.FindRows%2A> планируется вызывать несколько раз, следует создать новый объект <xref:System.Data.DataView> для перестроения индекса столбца, в котором необходимо выполнить поиск, а затем вызвать методы <xref:System.Data.DataView.Find%2A> или <xref:System.Data.DataView.FindRows%2A>. Для получения дополнительной <xref:System.Data.DataView.Find%2A> <xref:System.Data.DataView.FindRows%2A> информации о методах и методах, [см.](./dataset-datatable-dataview/finding-rows.md)  
  
 В следующем примере метод <xref:System.Data.DataView.Find%2A> используется для поиска контактного лица с фамилией «Zhu».  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryorderbyfind)]
 [!code-vb[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryorderbyfind)]  
  
 В следующем примере метод <xref:System.Data.DataView.FindRows%2A> используется для поиска всех продуктов красного цвета.  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryfindrows)]
 [!code-vb[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryfindrows)]  
  
## <a name="aspnet"></a>ASP.NET  
 ASP.NET имеет механизм кэширования, позволяющий сохранять объекты, для создания которых в памяти требуются значительные ресурсы сервера. Кэширование таких типов ресурсов может значительно повысить производительность приложения. Кэширование реализовано с помощью класса <xref:System.Web.Caching.Cache> с собственными экземплярами кэша для каждого приложения. Поскольку создание нового объекта <xref:System.Data.DataView> требует больших ресурсов, в веб-приложениях может быть полезным использование кэширования, чтобы объект <xref:System.Data.DataView> не приходилось перестраивать при каждом обновлении веб-страницы.  
  
 В следующем примере объект <xref:System.Data.DataView> кэшируется, поэтому данные не приходится сортировать заново при обновлении страницы.  
  
```vb  
If (Cache("ordersView") = Nothing) Then  
  
Dim dataSet As New DataSet()  
  
   FillDataSet(dataSet)  
  
   Dim orders As DataTable = dataSet.Tables("SalesOrderHeader")  
  
   Dim query = _  
                    From order In orders.AsEnumerable() _  
                    Where order.Field(Of Boolean)("OnlineOrderFlag") = True _  
                    Order By order.Field(Of Decimal)("TotalDue") _  
                    Select order  
  
   Dim view As DataView = query.AsDataView()  
  
   Cache.Insert("ordersView", view)  
  
End If  
  
Dim ordersView = CType(Cache("ordersView"), DataView)  
  
GridView1.DataSource = ordersView  
GridView1.DataBind()  
```  
  
```csharp  
if (Cache["ordersView"] == null)  
{  
   // Fill the DataSet.
   DataSet dataSet = FillDataSet();  
  
   DataTable orders = dataSet.Tables["SalesOrderHeader"];  
  
   EnumerableRowCollection<DataRow> query =  
                        from order in orders.AsEnumerable()  
                        where order.Field<bool>("OnlineOrderFlag") == true  
                        orderby order.Field<decimal>("TotalDue")  
                        select order;  
  
   DataView view = query.AsDataView();  
   Cache.Insert("ordersView", view);  
}  
  
DataView ordersView = (DataView)Cache["ordersView"];  
  
GridView1.DataSource = ordersView;  
GridView1.DataBind();  
```  
  
## <a name="see-also"></a>См. также раздел

- [Привязка данных и LINQ to DataSet](data-binding-and-linq-to-dataset.md)
