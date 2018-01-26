---
title: "Перечисление экземпляров SQL Server (ADO.NET)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ddf1c83c-9d40-45e6-b04d-9828c6cbbfdc
caps.latest.revision: "8"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 7b0a81fd9b92e626b52c5a74c65798ddedbd94a9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="enumerating-instances-of-sql-server-adonet"></a>Перечисление экземпляров SQL Server (ADO.NET)
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] позволяет приложениям находить экземпляры [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] в существующей сети. Класс <xref:System.Data.Sql.SqlDataSourceEnumerator> обеспечивает доступ к этим сведениям разработчику приложения, предоставляя объект <xref:System.Data.DataTable> с данными обо всех видимых серверах. Эта возвращенная таблица содержит список экземпляров сервера, доступен в сети, который совпадает со списком, предоставляемым при попытке пользователя создать новое соединение и дополняет раскрывающегося списка, содержащий все доступные серверы в **подключения Свойства** диалоговое окно. Отображаемые результаты не всегда являются полными.  
  
> [!NOTE]
>  Как и применительно к большинству служб Windows, лучше всего использовать службу браузера SQL с наименьшими возможными правами. Дополнительные сведения о службе браузера SQL и о том, как управлять ее работой, см. в электронной документации по [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
## <a name="retrieving-an-enumerator-instance"></a>Получение экземпляра перечислителя  
 Чтобы получить таблицу с данными о доступных экземплярах [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], вначале необходимо получить перечислитель с помощью общего и (или) статического свойства <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A>:  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =   
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 После получения статического экземпляра можно вызвать метод <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A>, который возвращает таблицу <xref:System.Data.DataTable> со сведениями о доступных серверах:  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 Таблица, возвращенная в результате вызова этого метода, содержит следующие столбцы, причем все эти столбцы содержат значения `string`:  
  
|Столбец|Описание:|  
|------------|-----------------|  
|**ServerName**|Имя сервера.|  
|**InstanceName**|Имя экземпляра сервера. Является пустым, если сервер работает в качестве экземпляра по умолчанию.|  
|**IsClustered**|Показывает, является ли сервер частью кластера.|  
|**Version**|Версия сервера. Пример:<br /><br /> -9, 00.x ([!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)])<br />-10.0.xx ([!INCLUDE[ssKatmai](../../../../../includes/sskatmai-md.md)])<br />-10.50.x ([!INCLUDE[ssKilimanjaro](../../../../../includes/sskilimanjaro-md.md)])<br />-11.0.xx ([!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 г.)|  
  
## <a name="enumeration-limitations"></a>Ограничения перечисления  
 Могут перечисляться все или не все доступные серверы. Содержимое списка может изменяться в зависимости от таких факторов, как время ожидания и сетевой трафик. Это может привести к тому, что при двух последовательных вызовах будут получены разные списки. В список входят только серверы, находящиеся в одной сети. Широковещательные пакеты обычно не проходят через маршрутизаторы, поэтому некоторый сервер может отсутствовать в списке, но будет стабильно работать.  
  
 Сведения о серверах из списка могут включать или не включать такие дополнительные данные, как `IsClustered` и версия. Это зависит от того, каким образом был получен список. В списках серверов, полученных с помощью службы браузера [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], присутствует больше сведений, чем в списках серверов, найденных с помощью инфраструктуры Windows и содержащих только имена.  
  
> [!NOTE]
>  Перечисление серверов становится доступным только при выполнении процедуры с полным уровнем доверия. Сборки, работающие в среде с неполным доверием, не могут использовать это перечисление, даже если для них задано разрешение CAS <xref:System.Data.SqlClient.SqlClientPermission>.  
  
 В версии [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] сведения для <xref:System.Data.Sql.SqlDataSourceEnumerator> предоставляются с использованием внешней службы Windows, называемой браузером SQL. Применение этой службы разрешено по умолчанию, но администраторы могут ее выключать или запрещать, в результате чего соответствующий экземпляр сервера становится невидимым для указанного класса.  
  
## <a name="example"></a>Пример  
 Следующее консольное приложение получает сведения обо всех видимых экземплярах [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] и отображает эти сведения в окне консоли.  
  
```vb  
Imports System.Data.Sql  
  
Module Module1  
  Sub Main()  
    ' Retrieve the enumerator instance and then the data.  
    Dim instance As SqlDataSourceEnumerator = _  
     SqlDataSourceEnumerator.Instance  
    Dim table As System.Data.DataTable = instance.GetDataSources()  
  
    ' Display the contents of the table.  
    DisplayData(table)  
  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Sub  
  
  Private Sub DisplayData(ByVal table As DataTable)  
    For Each row As DataRow In table.Rows  
      For Each col As DataColumn In table.Columns  
        Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
      Next  
      Console.WriteLine("============================")  
    Next  
  End Sub  
End Module  
```  
  
```csharp  
using System.Data.Sql;  
  
class Program  
{  
  static void Main()  
  {  
    // Retrieve the enumerator instance and then the data.  
    SqlDataSourceEnumerator instance =  
      SqlDataSourceEnumerator.Instance;  
    System.Data.DataTable table = instance.GetDataSources();  
  
    // Display the contents of the table.  
    DisplayData(table);  
  
    Console.WriteLine("Press any key to continue.");  
    Console.ReadKey();  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
    foreach (System.Data.DataRow row in table.Rows)  
    {  
      foreach (System.Data.DataColumn col in table.Columns)  
      {  
        Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
      }  
      Console.WriteLine("============================");  
    }  
  }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [SQL Server и ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
