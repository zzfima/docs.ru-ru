---
title: Определение первичных ключей
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 159b23eb4ef5ca38ebce6e488080d315ec3be081
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151186"
---
# <a name="defining-primary-keys"></a><span data-ttu-id="36586-102">Определение первичных ключей</span><span class="sxs-lookup"><span data-stu-id="36586-102">Defining Primary Keys</span></span>
<span data-ttu-id="36586-103">База данных обычно содержит столбец или группу столбцов, уникально определяющих каждую строку в таблице.</span><span class="sxs-lookup"><span data-stu-id="36586-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="36586-104">Такие столбцы или группы столбцов называются первичными ключами.</span><span class="sxs-lookup"><span data-stu-id="36586-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="36586-105">При определении <xref:System.Data.DataColumn> сингла <xref:System.Data.DataTable.PrimaryKey%2A> как <xref:System.Data.DataTable>для, таблица <xref:System.Data.DataColumn.AllowDBNull%2A> автоматически устанавливает свойство <xref:System.Data.DataColumn.Unique%2A> столбца к **ложному** и свойство к **истине.**</span><span class="sxs-lookup"><span data-stu-id="36586-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="36586-106">Для основных ключей с несколькими столбцовами только свойство **AllowDBNull** автоматически устанавливается на **ложное.**</span><span class="sxs-lookup"><span data-stu-id="36586-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="36586-107">Свойство **PrimaryKey** <xref:System.Data.DataTable> получает в качестве своей ценности массив одного или нескольких объектов **DataColumn,** как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="36586-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="36586-108">В первом примере в качестве первичного ключа определяется один столбец.</span><span class="sxs-lookup"><span data-stu-id="36586-108">The first example defines a single column as the primary key.</span></span>  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustID")}  
  
' Or  
  
Dim columns(1) As DataColumn  
columns(0) = workTable.Columns("CustID")  
workTable.PrimaryKey = columns  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustID"]};  
  
// Or  
  
DataColumn[] columns = new DataColumn[1];  
columns[0] = workTable.Columns["CustID"];  
workTable.PrimaryKey = columns;  
```  
  
 <span data-ttu-id="36586-109">Следующий пример определяет два столбца в качестве первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="36586-109">The following example defines two columns as a primary key.</span></span>  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustLName"), _  
                                         workTable.Columns("CustFName")}  
  
' Or  
  
Dim keyColumn(2) As DataColumn  
keyColumn(0) = workTable.Columns("CustLName")  
keyColumn(1) = workTable.Columns("CustFName")  
workTable.PrimaryKey = keyColumn  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustLName"],
                                         workTable.Columns["CustFName"]};  
  
// Or  
  
DataColumn[] keyColumn = new DataColumn[2];  
keyColumn[0] = workTable.Columns["CustLName"];  
keyColumn[1] = workTable.Columns["CustFName"];  
workTable.PrimaryKey = keyColumn;  
```  
  
## <a name="see-also"></a><span data-ttu-id="36586-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="36586-110">See also</span></span>

- <xref:System.Data.DataTable>
- [<span data-ttu-id="36586-111">Определение схемы таблицы данных</span><span class="sxs-lookup"><span data-stu-id="36586-111">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="36586-112">DataTables</span><span class="sxs-lookup"><span data-stu-id="36586-112">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="36586-113">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="36586-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
