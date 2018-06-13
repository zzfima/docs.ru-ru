---
title: Разбивка на страницы результатов запроса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: 73475f8521b4112929339cc7f1116e36ffebedb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358972"
---
# <a name="paging-through-a-query-result"></a>Разбивка на страницы результатов запроса
Постраничный просмотр результатов запроса - это процесс возврата результатов запроса небольшими подмножествами данных (страницами). Этот метод часто используется для вывода результатов пользователю в виде небольших фрагментов, с которыми легко работать.  
  
 **DataAdapter** предоставляет возможность возвращать только одну страницу данных путем перегрузки **заполнения** метод. Однако это не может быть наилучшим решением для постраничного просмотра результатов запроса имеет большой размер, поскольку несмотря на то что **DataAdapter** заполняет целевые <xref:System.Data.DataTable> или <xref:System.Data.DataSet> с только запрошенными записями, а ресурсы, возвращая весь запрос все еще используются. Для возврата страницы данных из источника данных без использования лишних ресурсов задайте для запроса дополнительные критерии, которые ограничат число возвращаемых строки только необходимыми.  
  
 Для использования **заполнения** указать метод для возврата страницы данных, **startRecord** параметр первую запись на странице данных и **maxRecords** параметр количества записей на странице данных.  
  
 В следующем примере кода показано, как использовать **заполнения** метод для возврата первой страницы результатов запроса, где размер страницы-пять записей.  
  
```vb  
Dim currentIndex As Integer = 0  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT * FROM dbo.Orders ORDER BY OrderID"  
' Assumes that connection is a valid SqlConnection object.  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
int currentIndex = 0;  
int pageSize = 5;  
  
string orderSQL = "SELECT * FROM Orders ORDER BY OrderID";  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 В предыдущем примере **набора данных** заполняется только пятью записями, и вся **заказов** возвращается вся таблица. Для заполнения **набора данных** с теми же пятью записями, но возвратить только пять записей, используйте TOP и WHERE в инструкции SQL, как показано в следующем примере кода.  
  
```vb  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT TOP " & pageSize & _  
  " * FROM Orders ORDER BY OrderID"  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Orders")   
```  
  
```csharp  
int pageSize = 5;  
  
string orderSQL = "SELECT TOP " + pageSize +   
  " * FROM Orders ORDER BY OrderID";  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Orders");  
```  
  
 Обратите внимание, что при таком способе постраничного просмотра результатов запроса необходимо сохранять уникальный идентификатор, с помощью которого выполняется упорядочение строк. Этот уникальный идентификатор нужно будет передать команде, служащей для возврата следующей страницы записей, как показано в следующем примере кода.  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =   
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 Чтобы возвратить следующую страницу записей, используя перегруженный **заполнения** метода, принимающего **startRecord** и **maxRecords** параметров, увеличения значения текущему индексу записи по размер страницы и заполнения таблицы. Помните, что сервер базы данных возвращает все результаты запроса, несмотря на то, что только одна страница записей добавляется **набора данных**. В следующем примере кода строки таблицы очищаются, а затем заполняются следующей страницей данных. Может быть необходимым сохранить определенное число возвращенных строк в локальном кэше, чтобы уменьшить число обращений к серверу базы данных.  
  
```vb  
currentIndex = currentIndex + pageSize  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
currentIndex += pageSize;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 Чтобы возвратить следующую страницу записей, не заставляя сервер баз данных возвращать сразу все результаты запроса, укажите ограничивающие критерии для инструкции SELECT. Так как код предыдущего примера сохранил последнюю возвращенную запись, ее можно использовать в предложении WHERE, чтобы указать для запроса начальную точку, как показано в следующем примере кода.  
  
```vb  
orderSQL = "SELECT TOP " & pageSize & _  
  " * FROM Orders WHERE OrderID > " & lastRecord & " ORDER BY OrderID"  
adapter.SelectCommand.CommandText = orderSQL  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, "Orders")  
```  
  
```csharp  
orderSQL = "SELECT TOP " + pageSize +   
  " * FROM Orders WHERE OrderID > " + lastRecord + " ORDER BY OrderID";  
adapter.SelectCommand.CommandText = orderSQL;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, "Orders");  
```  
  
## <a name="see-also"></a>См. также  
 [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
