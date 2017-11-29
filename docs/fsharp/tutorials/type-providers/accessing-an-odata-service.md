---
title: "Пошаговое руководство. Доступ к службе OData с помощью поставщиков типов (F#)"
description: "Использование поставщика типов ODataService F # в F # 3.0 для создания типов клиентов для службы OData и запроса данных веб-каналы, служба предоставляет."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0adae84c-b0fa-455f-994b-274ecdc6df30
ms.openlocfilehash: 28c2e9a405670f4e5f9512e99e0e6c3e3082856c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-accessing-an-odata-service-by-using-type-providers"></a>Пошаговое руководство. Доступ к службе OData с помощью поставщиков типов

> [!NOTE]
В этом руководстве, была написана для F # 3.0 и будут обновлены.  Актуальные сведения о кроссплатформенных поставщиках типов см. в описании [FSharp.Data](http://fsharp.github.io/FSharp.Data/).

> [!NOTE]
Справочные ссылки API, вы перейдете MSDN.  Работа над справочником по API docs.microsoft.com не завершена.

OData, то есть Open Data Protocol — это протокол передачи данных через Интернет. Многие поставщики данных предоставляют доступ к своим данным путем публикации веб-службу OData. Доступ к данным из любого источника OData в F # 3.0 с помощью типов данных, автоматически создаваемых `ODataService` поставщик типа. Дополнительные сведения об OData см. в разделе https://msdn.microsoft.com/library/da3380cc-f6da-4c6c-bdb2-bb86afa59d62.

В этом пошаговом руководстве демонстрируется использование поставщика типов ODataService F # для создания типов клиентов для службы OData и запроса данных веб-каналы, служба предоставляет.

В этом пошаговом руководстве описываются перечисленные ниже задачи, которые необходимо выполнить в указанном порядке.


- Настройка проекта клиента для службы OData
<br />

- Доступ к типам OData
<br />

- Запросов службы OData
<br />

- Проверка запросов OData
<br />


## <a name="configuring-a-client-project-for-an-odata-service"></a>Настройка проекта клиента для службы OData
На этом этапе можно настроить проект для использования поставщика типов OData.


#### <a name="to-configure-a-client-project-for-an-odata-service"></a>Чтобы настроить проект клиента для службы OData

- Откройте проект консольного приложения F # и добавьте ссылку на `System.Data.Services.Client` Framework сборки.
<br />

- В разделе `Extensions`, добавьте ссылку на `FSharp.Data.TypeProviders` сборки.
<br />

## <a name="accessing-odata-types"></a>Доступ к типам OData
На этом шаге создается тип поставщика, который предоставляет доступ к типам и данных для службы OData.


#### <a name="to-access-odata-types"></a>Для доступа к типам OData

- В редакторе кода откройте исходный файл F # и введите следующий код.
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type Northwind = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">

let db = Northwind.GetDataContext()
let fullContext = Northwind.ServiceTypes.NorthwindEntities()
```

В этом примере вызывается поставщик типа F # и указание его, чтобы создать набор типов, основанных на указанный вами URI OData. Доступны два объекта, содержащие сведения о данных; один является упрощенным контекстом данных, `db` в примере. Этот объект содержит только типы данных, которые связаны с базой данных, включающих типов для таблиц или веб-каналы. Другой объект `fullContext` в этом примере является экземпляром класса `System.Data.Linq.DataContext` и содержит много дополнительных свойств, методов и событий.
<br />


## <a name="querying-an-odata-service"></a>Запросов службы OData
На этом шаге используются выражения запросов F # для запроса к службе OData.


#### <a name="to-query-an-odata-service"></a>Для запросов службы OData

1. Теперь, когда настраивается поставщик типов, можно выполнить запрос службы OData.
<br />  OData поддерживает только подмножество доступных запросов операций. Поддерживаются следующие операции и их соответствующие ключевые слова:
<br />
  - проекция (`select`)
<br />

  - Фильтрация (`where`, по возможности используя строка и Дата операции)
<br />

  - Разбивка на страницы (`skip`, `take`)
<br />

  - упорядочение (`orderBy`, `thenBy`)
<br />

  - `AddQueryOption`и `Expand`, которые являются операций, связанных с OData
<br />

  Дополнительные сведения см. в разделе [рекомендации по LINQ &#40; Службы данных WCF &#41; ](https://msdn.microsoft.com/library/ee622463.aspx).
<br />  Все записи в канал или таблице, используйте самая простая форма выражения запроса, как показано в следующем коде:
<br />

```fsharp
query {
  for customer in db.Customers do
  select customer
} |> Seq.iter (fun customer ->
                  printfn "ID: %s\nCompany: %s" customer.CustomerID customer.CompanyName
                  printfn "Contact: %s\nAddress: %s" customer.ContactName customer.Address
                  printfn "         %s, %s %s" customer.City customer.Region customer.PostalCode
                  printfn "%s\n" customer.Phone)
```

2. Укажите поля или столбцы, которые должны с помощью кортеж после ключевого слова select.
<br />

```fsharp
  query { 
    for cat in db.Categories do
    select (cat.CategoryID, cat.CategoryName, cat.Description)
  } |> Seq.iter (fun (id, name, description) ->
                    printfn "ID: %d\nCategory: %s\nDescription: %s\n" id name description)
```

3. Укажите условия, используя `where` предложения.
<br />

```fsharp
query {
  for employee in db.Employees do
  where (employee.EmployeeID = 9)
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID))
```

4. Укажите условие подстроки в запрос с помощью `System.String.Contains(System.String)` метод. Следующий запрос возвращает все продукты, имеющих в имени «Chef». Также Обратите внимание на использование `System.Nullable<'T>.GetValueOrDefault()`. `UnitPrice` Является допускающим значения NULL, поэтому вы должны получить значение с помощью `Value` свойства, или необходимо вызвать метод `System.Nullable<'T>.GetValueOrDefault()`.
<br />

```fsharp
query { 
  for product in db.Products do
  where (product.ProductName.Contains("Chef"))
  select product
} |> Seq.iter (fun product ->
                  printfn "ID: %d Product: %s" product.ProductID product.ProductName
                  printfn "Price: %M\n" (product.UnitPrice.GetValueOrDefault()))
```

5. Используйте `System.String.EndsWith(System.String)` метод, чтобы указать, что строка заканчивается определенной подстрокой.
<br />

```fsharp
query {
  for product in db.Products do
  where (product.ProductName.EndsWith("u"))
  select product
} |> Seq.iter (fun product ->
                  printfn "ID: %d Product: %s" product.ProductID product.ProductName
                  printfn "Price: %M\n" (product.UnitPrice.GetValueOrDefault()))
```

6. Объединение условий в предложение where можно с помощью `&&` оператор.
<br />

```fsharp
// Open this module to use the nullable operators ?> and ?<.
open Microsoft.FSharp.Linq.NullableOperators

let salesIn1997 = query { 
  for sales in db.Category_Sales_for_1997 do
  where (sales.CategorySales ?> 50000.00M && sales.CategorySales ?< 60000.0M)
  select sales }

salesIn1997
|> Seq.iter (fun sales ->
                printfn "Category: %s Sales: %M" sales.CategoryName (sales.CategorySales.GetValueOrDefault()))
```

Операторы `?>` и `?<` приведены операторы, допускающие значение NULL. Можно использовать полный набор nullable операторы равенства и сравнения. Дополнительные сведения см. в разделе [модуль Linq.NullableOperators](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d).
<br />

7. Используйте `sortBy` запроса оператор, чтобы задать сортировку и используйте `thenBy` чтобы указать другой уровень упорядочения. Обратите внимание, использование кортежа в части select запроса. Таким образом запрос содержит кортеж как тип элемента.
<br />

```fsharp
printfn "Freight for some orders: "

query { 
  for order in db.Orders do
  sortBy (order.OrderDate.Value)
  thenBy (order.OrderID)
  select (order.OrderDate, order.OrderID, order.Customer.CompanyName)
} |> Seq.iter (fun (orderDate, orderID, company) ->
                  printfn "OrderDate: %s" (orderDate.GetValueOrDefault().ToString())
                  printfn "OrderID: %d Company: %s\n" orderID company)
```

8. Игнорировать заданное число записей, используя оператор skip и использовать оператор take, чтобы указать количество возвращаемых записей. Таким образом можно реализовать разбиение на страницы на веб-каналов данных.
<br />

```fsharp
printfn "Get the first page of 2 employees."

query { 
  for employee in db.Employees do
  take 2
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID)) 

printfn "Get the next 2 employees."

query { 
  for employee in db.Employees do
  skip 2
  take 2
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID))
```

## <a name="verifying-the-odata-request"></a>Проверка запроса OData
Каждый запрос OData преобразуется в конкретных URI запроса OData. Убедитесь, что URI, возможно для отладки целей, добавив обработчик событий к `SendingRequest` событий для объекта context полного набора данных.


#### <a name="to-verify-the-odata-request"></a>Чтобы проверить запрос OData

- Чтобы убедиться в URI запроса OData, используйте следующий код:
<br />

```fsharp
// The DataContext property returns the full data context.
db.DataContext.SendingRequest.Add (fun eventArgs -> printfn "Requesting %A" eventArgs.Request.RequestUri)
```

Выводится следующий результат выполнения приведенного кода:
<br />`requesting http://services.odata.org/Northwind/Northwind.svc/Orders()?$orderby=ShippedDate&amp;$select=OrderID,ShippedDate`


## <a name="see-also"></a>См. также
[Выражения запросов](../../language-reference/query-expressions.md)

[Рекомендации по LINQ (службы данных WCF)](https://msdn.microsoft.com/library/ee622463.aspx)

[Поставщик типов ODataService (F #)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/odataservice-type-provider-%5bfsharp%5d)
