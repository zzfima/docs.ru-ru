---
title: Запросы к одной таблице (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b74bcf8-3f87-449f-bff7-6bcb0d69d212
ms.openlocfilehash: 8807125bd61c71217ca96f3b5a38148ed100073b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794373"
---
# <a name="single-table-queries-linq-to-dataset"></a>Запросы к одной таблице (LINQ to DataSet)
[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]запросы работают с источниками данных, которые <xref:System.Collections.Generic.IEnumerable%601> реализуют интерфейс <xref:System.Linq.IQueryable%601> или интерфейс. <xref:System.Data.DataTable> <xref:System.Data.DataTableExtensions.AsEnumerable%2A> [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] `From` Класс не реализует ни один из интерфейсов, поэтому необходимо вызвать метод, если вы хотите использовать в качестве источника в предложении запроса. <xref:System.Data.DataTable>  
  
 В следующем примере получаются все активные заказы из таблицы SalesOrderHeader и выводится на консоль идентификатор, дата и номер заказа.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]  
 [!code-vb[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)] 
  
 Запрос локальной переменной инициализируется выражением запроса, которое работает с одним или несколькими источниками данных, применяя один или несколько операторов запроса либо к стандартным операторам запроса, либо, в случае LINQ to DataSet, операторам, относящимся к элементу <xref:System.Data.DataSet>класс. Выражение запроса в предыдущем примере использует два стандартных оператора запроса: `Where` и `Select`.  
  
 Предложение `Where` фильтрует последовательность на основе состояния. В данном случае переменная `OnlineOrderFlag` установлена в `true`. Оператор `Select` назначает и возвращает перечислимый объект, который перехватывает параметры, передаваемые оператору. В предыдущем примере анонимный тип создан с тремя свойствами: `SalesOrderID`, `OrderDate`, `SalesOrderNumber`. Этим трем свойствам присвоены значения из столбцов `SalesOrderID`, `OrderDate` и `SalesOrderNumber` таблицы `SalesOrderHeader`.  
  
 Затем цикл `foreach` проходит по перечислимому объекту, возвращенному оператором `Select`, и выдает результаты запроса. Так как этот запрос имеет тип <xref:System.Linq.Enumerable>, который реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601>, результат запроса откладывается до тех пор, пока переменная запроса проходит по циклу `foreach`. Отложенный результат запроса позволяет запросам храниться в виде значений, которые могут вычисляться несколько раз, каждый раз давая потенциально различные результаты.  
  
 Метод <xref:System.Data.DataRowExtensions.Field%2A> обеспечивает доступ к значениям столбцов <xref:System.Data.DataRow> и <xref:System.Data.DataRowExtensions.SetField%2A> (что не показано в предыдущем примере) и устанавливает значения столбцов в <xref:System.Data.DataRow>. Оба метода, <xref:System.Data.DataRowExtensions.Field%2A> и <xref:System.Data.DataRowExtensions.SetField%2A>, обрабатывают типы, допускающие значения NULL, поэтому нет необходимости явно проводить проверку на значения NULL. Оба метода являются универсальными методами, что означает, что нет необходимости приводить тип возвращаемого значения. В <xref:System.Data.DataRow> нужно использовать предопределенный метод доступа к столбцам (например, `o["OrderDate"]`), однако в этом случае приведение возвращаемого объекта к соответствующему типу обязательно.  Если столбец допускает значение NULL, необходимо проверить его на значение NULL, используя метод <xref:System.Data.DataRow.IsNull%2A>. Дополнительные сведения см. в разделе [универсальные методы полей и SetField](generic-field-and-setfield-methods-linq-to-dataset.md).  
  
 Обратите внимание, что тип данных, определяемый в универсальном параметре `T` методов <xref:System.Data.DataRowExtensions.Field%2A> и <xref:System.Data.DataRowExtensions.SetField%2A>, должен соответствовать типу базового значения, иначе сформируется исключение <xref:System.InvalidCastException>. Указанное имя столбца должно совпадать с именем столбца в <xref:System.Data.DataSet>, иначе это вызовет исключение <xref:System.ArgumentException>. В обоих случаях исключении возникает при перечислении данных во время выполнения в момент выполнения запроса.  
  
## <a name="see-also"></a>См. также

- [Запросы между таблицами](cross-table-queries-linq-to-dataset.md)
- [Запрос к типизированным объектам DataSet](querying-typed-datasets.md)
- [Универсальные методы Field и SetField](generic-field-and-setfield-methods-linq-to-dataset.md)
