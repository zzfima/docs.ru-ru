---
title: Извлечение данных и операции создания, обновления и удаления в N-уровневых приложениях (LINQ to SQL)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c3133d53-83ed-4a4d-af8b-82edcf3831db
ms.openlocfilehash: ea27d6406ed588f2046dc938f5167a6c0200329e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365843"
---
# <a name="data-retrieval-and-cud-operations-in-n-tier-applications-linq-to-sql"></a>Извлечение данных и операции создания, обновления и удаления в N-уровневых приложениях (LINQ to SQL)
При сериализации объектов сущностей, например объектов "Customers" или "Orders", на клиент по сети эти сущности отсоединяются от своего контекста данных. Контекст данных более не отслеживает их изменения или их связи с другими объектами. Это не вызывает проблемы, если клиент осуществляет только чтение данных. Также довольно просто реализовать добавление клиентами строк в базу данных. Однако если приложению требуется, чтобы клиенты имели возможность обновлять или удалять данные, то перед вызовом метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=nameWithType> необходимо присоединить сущности к новому контексту данных. Кроме того, если используется проверка оптимистического параллелизма на основе исходных значений, также требуется реализовать способ предоставления базе данных исходной сущности и сущности после изменения. С помощью методов `Attach` можно поместить сущности в новый контекст данных после их отсоединения.  
  
 Даже если выполняется сериализация прокси-объектов вместо [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сущностей, все равно необходимо создать сущность в слое доступа к данным (DAL) и присоединить ее к новой <xref:System.Data.Linq.DataContext?displayProperty=nameWithType>, для отправки данных в базу данных.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] — совершенно не зависит от способа сериализации сущностей. Дополнительные сведения об использовании [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] и средства SQLMetal для создания классов, которые могут быть сериализованы с помощью Windows Communication Foundation (WCF) в разделе [как: сделать сущностей сериализуемым](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md).  
  
> [!NOTE]
>  Для новых или десериализованных сущностей следует вызывать только методы `Attach`. При сериализации сущности ее обязательно следует отсоединить от исходного контекста данных. Если выполняется попытка присоединить неотсоединенную сущность к новому контексту данных и у этой сущности по-прежнему имеются отложенные загрузчики из предыдущего контекста данных, технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] вызовет исключение. Наличие сущности с отложенными загрузчиками из двух разных контекстов данных может привести к нежелательным результатам при выполнении операций вставки, обновления и удаления для этой сущности. Дополнительные сведения о отложенными загрузчиками см. в разделе [отложенное или немедленное загрузки](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
## <a name="retrieving-data"></a>Получение данных  
  
### <a name="client-method-call"></a>Вызов клиентского метода  
 В следующих примерах показан метод вызова компонента DAL из клиента Windows Forms. В данном примере компонент DAL реализован в качестве библиотеки служб Windows.  
  
```vb  
Private Function GetProdsByCat_Click(ByVal sender As Object, ByVal e _  
    As EventArgs)  
  
    ' Create the WCF client proxy.  
    Dim proxy As New NorthwindServiceReference.Service1Client  
  
    ' Call the method on the service.  
    Dim products As NorthwindServiceReference.Product() = _  
        proxy.GetProductsByCategory(1)  
  
    ' If the database uses original values for concurrency checks,  
    ' the client needs to store them and pass them back to the  
    ' middle tier along with the new values when updating data.  
  
    For Each v As NorthwindClient1.NorthwindServiceReference.Product _  
        In products  
        ' Persist to a List(Of Product) declared at class scope.  
        ' Additional change-tracking logic is the responsibility  
        ' of the presentation tier and/or middle tier.  
        originalProducts.Add(v)  
    Next  
  
    ' (Not shown) Bind the products list to a control  
    ' and/or perform whatever processing is necessary.  
End Function  
```  
  
```csharp  
private void GetProdsByCat_Click(object sender, EventArgs e)  
{  
    // Create the WCF client proxy.  
    NorthwindServiceReference.Service1Client proxy =   
    new NorthwindClient.NorthwindServiceReference.Service1Client();  
  
    // Call the method on the service.  
    NorthwindServiceReference.Product[] products =   
    proxy.GetProductsByCategory(1);  
  
    // If the database uses original values for concurrency checks,   
    // the client needs to store them and pass them back to the   
    // middle tier along with the new values when updating data.  
    foreach (var v in products)  
    {  
        // Persist to a list<Product> declared at class scope.  
        // Additional change-tracking logic is the responsibility  
        // of the presentation tier and/or middle tier.  
        originalProducts.Add(v);  
    }  
  
    // (Not shown) Bind the products list to a control  
    // and/or perform whatever processing is necessary.  
    }  
```  
  
### <a name="middle-tier-implementation"></a>Реализация среднего уровня  
 В следующем примере приведена реализация данного метода интерфейса для среднего уровня. Необходимо отметить два основных момента.  
  
-   Класс <xref:System.Data.Linq.DataContext> объявляется в области действия метода.  
  
-   Метод возвращает коллекцию <xref:System.Collections.IEnumerable>, содержащую фактические результаты. Для отправки результатов обратно на клиентский уровень или уровень представления данных сериализатор выполняет запрос. Для получения доступа к результатам запроса локально на среднем уровне можно принудительно выполнить запрос, вызвав метод `ToList` или `ToArray` для переменной запроса. После этого можно возвратить этот список или массив в качестве коллекции `IEnumerable`.  
  
```vb  
Public Function GetProductsByCategory(ByVal categoryID As Integer) _  
    As IEnumerable(Of Product)  
  
    Dim db As New NorthwindClasses1DataContext(connectionString)  
    Dim productQuery = _  
    From prod In db.Products _  
    Where prod.CategoryID = categoryID _  
    Select prod  
  
    Return productQuery.AsEnumerable()  
  
End Function  
```  
  
```csharp  
public IEnumerable<Product> GetProductsByCategory(int categoryID)  
{  
    NorthwindClasses1DataContext db =   
    new NorthwindClasses1DataContext(connectionString);  
  
    IEnumerable<Product> productQuery =  
    from prod in db.Products  
    where prod.CategoryID == categoryID  
    select prod;  
  
    return productQuery.AsEnumerable();   
}  
```  
  
 Время существования экземпляра контекста данных должно составлять одну "единицу работы". В слабо связанных средах единица работы обычно мала и, как правило, составляет одну оптимистическую транзакцию, включающую вызов метода `SubmitChanges`. Поэтому контекст данных создается и уничтожается в области действия метода. Если единица работы включает вызовы логики бизнес-правил, то, как правило, требуется сохранять экземпляр `DataContext` в течение всей операции. В любом случае экземпляры `DataContext` не предназначены для существования в течение продолжительного периода времени в составе произвольного числа транзакций.  
  
 Данный метод возвращает объекты "Product", а не коллекцию объектов "Order_Detail", связанных с каждым объектом "Product". Для изменения данного поведения, установленного по умолчанию, используйте объект <xref:System.Data.Linq.DataLoadOptions>. Дополнительные сведения см. в разделе [как: элемент управления как гораздо связанные данные извлекаются](../../../../../../docs/framework/data/adonet/sql/linq/how-to-control-how-much-related-data-is-retrieved.md).  
  
## <a name="inserting-data"></a>Вставка данных  
 Для вставки нового объекта уровень представления данных просто вызывает соответствующий метод в интерфейсе среднего уровня и передает новый объект для вставки. В некоторых случаях более эффективным становится способ, когда клиент передает только некоторые значения и указывает среднему уровню создать полный объект.  
  
### <a name="middle-tier-implementation"></a>Реализация среднего уровня  
 На среднем уровне создается новый класс <xref:System.Data.Linq.DataContext>, объект присоединяется к классу <xref:System.Data.Linq.DataContext> с помощью метода <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> и объект вставляется при вызове метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. Исключения, обратные вызовы и состояния ошибки можно обрабатывать точно так же, как в других сценариях веб-служб.  
  
```vb  
' No call to Attach is necessary for inserts.  
Public Sub InsertOrder(ByVal o As Order)  
  
    Dim db As New NorthwindClasses1DataContext(connectionString)  
    db.Orders.InsertOnSubmit(o)  
  
    ' Exception handling not shown.  
    db.SubmitChanges()  
  
End Sub  
```  
  
```csharp  
// No call to Attach is necessary for inserts.  
    public void InsertOrder(Order o)  
    {  
        NorthwindClasses1DataContext db = new NorthwindClasses1DataContext(connectionString);  
        db.Orders.InsertOnSubmit(o);  
  
        // Exception handling not shown.  
        db.SubmitChanges();  
    }  
```  
  
## <a name="deleting-data"></a>Удаление данных  
 Для удаления существующего объекта из базы данных уровень представления данных вызывает соответствующий метод в интерфейсе среднего уровня и передает копию, которая содержит исходные значения удаляемого объекта.  
  
 В состав операций удаления входят проверки оптимистического параллелизма, а удаляемый объект должен сначала быть присоединен к новому контексту данных. В данном примере для параметра `Boolean` устанавливается значение `false`, которое указывает, что объект не имеет отметки времени (столбца "RowVersion"). Если таблица базы данных создает отметки времени для каждой записи, проверки параллелизма выполняются гораздо проще, особенно для клиента. Для этого достаточно передать исходный или измененный объект и установить для параметра `Boolean` значение `true`. В любом случае на среднем уровне, как правило, требуется перехватывать исключение <xref:System.Data.Linq.ChangeConflictException>. Дополнительные сведения о том, как обрабатывать конфликты оптимистического параллелизма см. в разделе [оптимистичного параллелизма: Обзор](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
 При удалении сущностей, которые имеют ограничения внешних ключей для связанных таблиц, необходимо сначала удалить все объекты в коллекции <xref:System.Data.Linq.EntitySet%601> для сущности.  
  
```vb  
' Attach is necessary for deletes.  
Public Sub DeleteOrder(ByVal order As Order)  
    Dim db As New NorthwindClasses1DataContext(connectionString)  
  
    db.Orders.Attach(order, False)  
    ' This will throw an exception if the order has order details.  
    db.Orders.DeleteOnSubmit(order)  
  
    Try  
        ' ConflictMode is an optional parameter.  
        db.SubmitChanges(ConflictMode.ContinueOnConflict)  
  
    Catch ex As ChangeConflictException  
        ' Get conflict information, and take actions  
        ' that are appropriate for your application.  
        ' See MSDN Article "How to: Manage Change  
        ' Conflicts (LINQ to SQL).  
  
    End Try  
End Sub  
```  
  
```csharp  
// Attach is necessary for deletes.  
public void DeleteOrder(Order order)  
{  
    NorthwindClasses1DataContext db = new NorthwindClasses1DataContext(connectionString);  
  
    db.Orders.Attach(order, false);  
    // This will throw an exception if the order has order details.  
    db.Orders.DeleteOnSubmit(order);  
    try  
    {  
        // ConflictMode is an optional parameter.  
        db.SubmitChanges(ConflictMode.ContinueOnConflict);  
    }  
    catch (ChangeConflictException e)  
    {  
       // Get conflict information, and take actions  
       // that are appropriate for your application.  
       // See MSDN Article How to: Manage Change Conflicts (LINQ to SQL).  
    }  
}  
```  
  
## <a name="updating-data"></a>Обновление данных  
 Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает обновления в перечисленных ниже сценариях, в которых используется оптимистический параллелизм.  
  
-   Оптимистический параллелизм, основанный на отметках времени (или значениях столбца "RowVersion").  
  
-   Оптимистический параллелизм, основанный на исходных значениях вложенного набора свойств сущности.  
  
-   Оптимистический параллелизм, основанный на полных исходных и измененных сущностях.  
  
 Можно также выполнять операции обновления или удаления сущности вместе с ее связями, например обновить или удалить объект "Customer" и коллекцию связанных с ним объектов "Order". Если при внесении изменений в граф объектов сущностей и их дочерних коллекций (`EntitySet`) на клиенте для проверок оптимистического параллелизма требуются исходные значения, то клиенту необходимо предоставить эти исходные значения для каждой сущности и объекта <xref:System.Data.Linq.EntitySet%601>. Если необходимо предоставить клиенту возможность выполнить набор связанных операций удаления, обновления и вставки в одном методе, следует предоставить клиенту способ указания типа операции, которую необходимо выполнить для каждой сущности. На среднем уровне требуется вызвать соответствующий метод <xref:System.Data.Linq.ITable.Attach%2A>, а затем перед вызовом метода <xref:System.Data.Linq.ITable.InsertOnSubmit%2A> необходимо вызвать метод <xref:System.Data.Linq.ITable.DeleteAllOnSubmit%2A>, <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> или `Attach` (для операций вставки вызывать метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> вызывать не следует) для каждой сущности. Не используйте извлечение данных из базы данных в качестве способа получения исходных значений перед обновлением.  
  
 Дополнительные сведения о оптимистичного параллелизма в разделе [оптимистичного параллелизма: Обзор](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md). Подробные сведения об устранении оптимистичного параллелизма конфликты изменений см. в разделе [как: управление конфликты изменения](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).  
  
 В следующих примерах демонстрируется каждый из описанных выше сценариев.  
  
### <a name="optimistic-concurrency-with-timestamps"></a>Оптимистический параллелизм на основе отметок времени  
  
```vb  
' Assume that "customer" has been sent by client.  
' Attach with "true" to say this is a modified entity  
' and it can be checked for optimistic concurrency  
' because it has a column that is marked with the  
' "RowVersion" attribute.  
  
db.Customers.Attach(customer, True)  
  
Try  
    ' Optional: Specify a ConflictMode value  
    ' in call to SubmitChanges.  
    db.SubmitChanges()  
Catch ex As ChangeConflictException  
    ' Handle conflict based on options provided.  
    ' See MSDN article "How to: Manage Change  
    ' Conflicts (LINQ to SQL)".  
End Try  
```  
  
```csharp  
// Assume that "customer" has been sent by client.  
// Attach with "true" to say this is a modified entity  
// and it can be checked for optimistic concurrency because  
//  it has a column that is marked with "RowVersion" attribute  
db.Customers.Attach(customer, true)  
try  
{  
    // Optional: Specify a ConflictMode value  
    // in call to SubmitChanges.  
    db.SubmitChanges();  
}  
catch(ChangeConflictException e)  
{  
    // Handle conflict based on options provided  
    // See MSDN article How to: Manage Change Conflicts (LINQ to SQL).  
}  
```  
  
### <a name="with-subset-of-original-values"></a>На основе вложенного набора исходных значений  
 В данном методе клиент возвращает полный сериализованный объект вместе со значениями, которые требуется изменить.  
  
```vb  
Public Sub UpdateProductInventory(ByVal p As Product, ByVal _  
    unitsInStock As Short?, ByVal unitsOnOrder As Short?)  
  
    Using db As New NorthwindClasses1DataContext(connectionString)  
        ' p is the original unmodified product  
        ' that was obtained from the database.  
        ' The client kept a copy and returns it now.  
        db.Products.Attach(p, False)  
  
        ' Now that the original values are in the data context,  
        ' apply the changes.  
        p.UnitsInStock = unitsInStock  
        p.UnitsOnOrder = unitsOnOrder  
  
        Try  
            ' Optional: Specify a ConflictMode value  
            ' in call to SubmitChanges.  
            db.SubmitChanges()  
  
        Catch ex As Exception  
            ' Handle conflict based on options provided.  
            ' See MSDN article "How to: Manage Change Conflicts  
            ' (LINQ to SQL)".  
        End Try  
    End Using  
End Sub  
```  
  
```csharp  
public void UpdateProductInventory(Product p, short? unitsInStock, short? unitsOnOrder)  
{  
    using (NorthwindClasses1DataContext db = new NorthwindClasses1DataContext(connectionString))  
    {  
        // p is the original unmodified product  
        // that was obtained from the database.  
        // The client kept a copy and returns it now.  
        db.Products.Attach(p, false);  
  
        // Now that the original values are in the data context, apply the changes.  
        p.UnitsInStock = unitsInStock;  
        p.UnitsOnOrder = unitsOnOrder;  
        try  
        {  
             // Optional: Specify a ConflictMode value  
             // in call to SubmitChanges.  
             db.SubmitChanges();  
        }  
        catch (ChangeConflictException e)  
        {  
            // Handle conflict based on provided options.  
            // See MSDN article How to: Manage Change Conflicts  
            // (LINQ to SQL).  
        }  
    }  
}  
```  
  
### <a name="with-complete-entities"></a>На основе полных сущностей  
  
```vb  
Public Sub UpdateProductInfo(ByVal newProd As Product, ByVal _  
    originalProd As Product)  
  
    Using db As New NorthwindClasses1DataContext(connectionString)  
        db.Products.Attach(newProd, originalProd)  
  
        Try  
            ' Optional: Specify a ConflictMode value  
            ' in call to SubmitChanges.  
            db.SubmitChanges()  
  
        Catch ex As Exception  
            ' Handle potential change conflicgt in whatever way  
            ' is appropriate for your application.  
            ' For more information, see the MSDN article  
            ' "How to: Manage Change Conflicts (LINQ to  
            ' SQL)".  
        End Try  
  
    End Using  
End Sub  
```  
  
```csharp  
public void UpdateProductInfo(Product newProd, Product originalProd)  
{  
     using (NorthwindClasses1DataContext db = new  
        NorthwindClasses1DataContext(connectionString))  
     {  
         db.Products.Attach(newProd, originalProd);  
         try  
         {  
               // Optional: Specify a ConflictMode value  
               // in call to SubmitChanges.  
               db.SubmitChanges();  
         }  
        catch (ChangeConflictException e)  
        {  
            // Handle potential change conflict in whatever way  
            // is appropriate for your application.  
            // For more information, see the MSDN article  
            // How to: Manage Change Conflicts (LINQ to SQL)/  
        }   
    }  
}  
```  
  
 Для обновления коллекции вместо метода <xref:System.Data.Linq.ITable.AttachAll%2A> вызовите метод `Attach`.  
  
### <a name="expected-entity-members"></a>Ожидаемые члены сущности  
 Как уже указывалось выше, перед вызовом методов `Attach` требуется установить только некоторые члены объекта сущности. Ниже перечислены критерии, которым должны удовлетворять члены сущности, которые требуется установить.  
  
-   Члены должны входить в состав идентификации сущности.  
  
-   Их изменение должно быть ожидаемо.  
  
-   Они должны представлять собой отметку времени или для их атрибута <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> должно быть установлено значение, отличное от `Never`.  
  
 Если для проверки оптимистического параллелизма в таблице используется отметка времени или номер версии, то перед вызовом метода <xref:System.Data.Linq.ITable.Attach%2A> необходимо установить значения этих членов. Член предназначен для проверки оптимистического параллелизма в том случае, если свойства <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> данного атрибута столбца установлено значение "true". Любые запрошенные обновления будут отправлены только в том случае, если значения номера версии или отметки времени совпадают в базе данных.  
  
 Кроме того, член используется для проверки оптимистического параллелизма в том случае, если для свойства <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> данного члена не установлено значение `Never`. Если значение этого атрибута не установлено, по умолчанию используется значение `Always`.  
  
 Если один из этих обязательных членов отсутствует, то при выполнении метода <xref:System.Data.Linq.ChangeConflictException> вызывается исключение <xref:System.Data.Linq.DataContext.SubmitChanges%2A> ("Строка не найдена или изменена").  
  
### <a name="state"></a>Состояние  
 После того как объект сущности присоединен к экземпляру <xref:System.Data.Linq.DataContext>, состоянием объекта считается значение `PossiblyModified`. Для принудительного присвоения объекту состояния `Modified` можно использовать три способа.  
  
1.  Присоединить объект как неизмененный и затем изменить непосредственно поля.  
  
2.  Присоединить объект с помощью перегрузки метода <xref:System.Data.Linq.Table%601.Attach%2A>, которая принимает текущий и исходный экземпляры объекта. При этом средству отслеживания изменений предоставляются старое и новое значения, и он можно автоматически определить, какие поля изменились.  
  
3.  Присоединить объект с помощью перегрузки метода <xref:System.Data.Linq.Table%601.Attach%2A>, которая принимает "Boolean" в качестве второго параметра (с установленным значением "true"). При этом средство отслеживания изменений получает указание рассматривать объект как измененный, и предоставлять исходные значения не требуется. При использовании этого метода объект должен иметь поле версии или метки времени.  
  
 Дополнительные сведения см. в разделе [состояния объектов и отслеживание изменений](../../../../../../docs/framework/data/adonet/sql/linq/object-states-and-change-tracking.md).  
  
 Если в кэше уже имеется объект сущности с идентификацией присоединяемого объекта, вызывается исключение <xref:System.Data.Linq.DuplicateKeyException>.  
  
 Если при присоединении набора объектов `IEnumerable` в кэше оказывается совпадающий ключ, вызывается исключение <xref:System.Data.Linq.DuplicateKeyException>. Остальные объекты не присоединяются.  
  
## <a name="see-also"></a>См. также  
 [N-уровневые и удаленные приложения и LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)  
 [Основные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
