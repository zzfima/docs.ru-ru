---
title: Практическое руководство. Реализация CopyToDataTable<T>, где универсальный тип T не является объектом DataRow
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b27b52cf-6172-485f-a75c-70ff9c5a2bd4
ms.openlocfilehash: 6c14e87c5caede4fea52867d9f184f3f64a5ed3b
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249647"
---
# <a name="how-to-implement-copytodatatablet-where-the-generic-type-t-is-not-a-datarow"></a>Как: Реализация CopyToDataTable\<T>, где общий тип T не DataRow
Объект <xref:System.Data.DataTable> часто используется для связывания данных. Метод <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> принимает результаты запроса и копирует данные в <xref:System.Data.DataTable>, которую в дальнейшем можно использовать для привязки данных. Однако методы <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> работают только с источником, реализующим интерфейс <xref:System.Collections.Generic.IEnumerable%601>, в котором общий параметр `T` принадлежит к типу <xref:System.Data.DataRow>. Хотя это и полезно, это не позволяет создавать таблицы из последовательности скалярных типов, из запросов, проецирующих анонимные типы, или из запросов, содержащих соединение таблиц.  
  
 В этом разделе описано применение пользовательских методов расширений `CopyToDataTable<T>`, принимающих общий параметр `T` типа, отличного от <xref:System.Data.DataRow>. Логика создания объекта <xref:System.Data.DataTable> из источника <xref:System.Collections.Generic.IEnumerable%601> содержится в классе `ObjectShredder<T>`, который затем помещается в два перегруженных метода расширений `CopyToDataTable<T>`. Метод `Shred` класса `ObjectShredder<T>` возвращает заполненный объект <xref:System.Data.DataTable> и принимает три входных параметра: источник <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Data.DataTable> и перечисление <xref:System.Data.LoadOption>. Исходная схема возвращенного объекта <xref:System.Data.DataTable> основана на схеме типа `T`. Если в качестве входных данных используется существующая таблица, ее схема должна быть согласована со схемой типа `T`. Каждое общее свойство и поле типа `T` в возвращенной таблице преобразуется в тип <xref:System.Data.DataColumn>. Если исходная последовательность содержит тип, производный от `T`, то схема возвращенной таблицы расширяется дополнительными общими свойствами и полями.  
  
 Примеры использования пользовательских методов `CopyToDataTable<T>` см. в разделе [Создание таблицы данных из запроса](creating-a-datatable-from-a-query-linq-to-dataset.md).  
  
### <a name="to-implement-the-custom-copytodatatablet-methods-in-your-application"></a>Реализация в приложении пользовательских методов CopyToDataTable\<T>  
  
1. Реализуйте класс `ObjectShredder<T>` для создания объекта <xref:System.Data.DataTable> из источника <xref:System.Collections.Generic.IEnumerable%601>:  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#objectshredderclass)]
     [!code-vb[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#objectshredderclass)]  

    Предыдущий пример предполагает, что `DataColumn` свойства не являются недействительными типами значений. Для обработки свойств с необыданными типами значений используйте следующий код:

    ```csharp
    DataColumn dc = table.Columns.Contains(p.Name) ? table.Columns[p.Name] : table.Columns.Add(p.Name, Nullable.GetUnderlyingType(p.PropertyType) ?? p.PropertyType);
    ```

2. Реализуйте пользовательские методы расширений `CopyToDataTable<T>` в классе:  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#customcopytodatatablemethods)]
     [!code-vb[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#customcopytodatatablemethods)]  
  
3. Добавьте в приложение класс `ObjectShredder<T>` и методы расширений `CopyToDataTable<T>`.  
  
```vb  
Module Module1  
    Sub Main()  
        ' Your application code using CopyToDataTable<T>.  
    End Sub  
End Module  
  
Public Module CustomLINQtoDataSetMethods  
…  
End Module  
  
Public Class ObjectShredder(Of T)  
…  
End Class
```
  
```csharp
class Program  
{  
    static void Main(string[] args)  
    {  
        // Your application code using CopyToDataTable<T>.  
    }  
}  
public static class CustomLINQtoDataSetMethods  
{  
…  
}  
public class ObjectShredder<T>  
{  
…  
}  
```
  
## <a name="see-also"></a>См. также

- [Создание DataTable из запроса](creating-a-datatable-from-a-query-linq-to-dataset.md)
- [Руководство по программированию](programming-guide-linq-to-dataset.md)
