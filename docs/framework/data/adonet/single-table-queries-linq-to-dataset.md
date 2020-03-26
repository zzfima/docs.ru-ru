---
title: Запросы к одной таблице (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b74bcf8-3f87-449f-bff7-6bcb0d69d212
ms.openlocfilehash: 89c90fd217285fac449aba40682aa947fcfb3a07
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249094"
---
# <a name="single-table-queries-linq-to-dataset"></a>Запросы к одной таблице (LINQ to DataSet)
Языковые интегрированные запросы (LINЗ) работают <xref:System.Collections.Generic.IEnumerable%601> на источниках данных, которые реализуют интерфейс или <xref:System.Linq.IQueryable%601> интерфейс. Класс <xref:System.Data.DataTable> не реализует ни один из интерфейсов, поэтому необходимо вызвать <xref:System.Data.DataTableExtensions.AsEnumerable%2A> метод, если вы хотите использовать его в <xref:System.Data.DataTable> качестве источника в `From` пункте запроса LIN's.  
  
 В следующем примере получаются все активные заказы из таблицы SalesOrderHeader и выводится на консоль идентификатор, дата и номер заказа.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]  
 [!code-vb[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)]
  
 Локальный переменный запрос инициализирован с выражением запроса, который работает на одном или нескольких источниках информации, применяя одного или нескольких операторов <xref:System.Data.DataSet> запросов либо от стандартных операторов запросов, либо, в случае LIN' к DataSet, операторам, специфичным для класса. Выражение запроса в предыдущем примере использует два стандартных оператора запроса: `Where` и `Select`.  
  
 Предложение `Where` фильтрует последовательность на основе состояния. В данном случае переменная `OnlineOrderFlag` установлена в `true`. Оператор `Select` назначает и возвращает перечислимый объект, который перехватывает параметры, передаваемые оператору. В предыдущем примере анонимный тип создан с тремя свойствами: `SalesOrderID`, `OrderDate`, `SalesOrderNumber`. Этим трем свойствам присвоены значения из столбцов `SalesOrderID`, `OrderDate` и `SalesOrderNumber` таблицы `SalesOrderHeader`.  
  
 Затем цикл `foreach` проходит по перечислимому объекту, возвращенному оператором `Select`, и выдает результаты запроса. Так как этот запрос имеет тип <xref:System.Linq.Enumerable>, который реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601>, результат запроса откладывается до тех пор, пока переменная запроса проходит по циклу `foreach`. Отложенный результат запроса позволяет запросам храниться в виде значений, которые могут вычисляться несколько раз, каждый раз давая потенциально различные результаты.  
  
 Метод <xref:System.Data.DataRowExtensions.Field%2A> обеспечивает доступ к значениям столбцов <xref:System.Data.DataRow> и <xref:System.Data.DataRowExtensions.SetField%2A> (что не показано в предыдущем примере) и устанавливает значения столбцов в <xref:System.Data.DataRow>. Как <xref:System.Data.DataRowExtensions.Field%2A> метод, <xref:System.Data.DataRowExtensions.SetField%2A> так и метод обрабатывают недействительные типы значений, поэтому вам не придется явно проверять значения null. Оба метода являются универсальными методами, что означает, что нет необходимости приводить тип возвращаемого значения. В <xref:System.Data.DataRow> нужно использовать предопределенный метод доступа к столбцам (например, `o["OrderDate"]`), однако в этом случае приведение возвращаемого объекта к соответствующему типу обязательно.  Если столбец является необоснованной типом значения, вы должны <xref:System.Data.DataRow.IsNull%2A> проверить, является ли значение нулевым с помощью метода. Для получения дополнительной [информации см.](generic-field-and-setfield-methods-linq-to-dataset.md)  
  
 Обратите внимание, что тип данных, определяемый в универсальном параметре `T` методов <xref:System.Data.DataRowExtensions.Field%2A> и <xref:System.Data.DataRowExtensions.SetField%2A>, должен соответствовать типу базового значения, иначе сформируется исключение <xref:System.InvalidCastException>. Указанное имя столбца должно совпадать с именем столбца в <xref:System.Data.DataSet>, иначе это вызовет исключение <xref:System.ArgumentException>. В обоих случаях исключении возникает при перечислении данных во время выполнения в момент выполнения запроса.  
  
## <a name="see-also"></a>См. также

- [Запросы между таблицами](cross-table-queries-linq-to-dataset.md)
- [Запросы к типизированным наборам данных](querying-typed-datasets.md)
- [Универсальные методы Field и SetField](generic-field-and-setfield-methods-linq-to-dataset.md)
