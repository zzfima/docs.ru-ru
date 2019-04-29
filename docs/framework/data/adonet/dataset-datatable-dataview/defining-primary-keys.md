---
title: Определение первичных ключей
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 84c84cb8fc0ee484b09c69c72571a19c335b58f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607315"
---
# <a name="defining-primary-keys"></a><span data-ttu-id="d33dc-102">Определение первичных ключей</span><span class="sxs-lookup"><span data-stu-id="d33dc-102">Defining Primary Keys</span></span>
<span data-ttu-id="d33dc-103">База данных обычно содержит столбец или группу столбцов, уникально определяющих каждую строку в таблице.</span><span class="sxs-lookup"><span data-stu-id="d33dc-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="d33dc-104">Такие столбцы или группы столбцов называются первичными ключами.</span><span class="sxs-lookup"><span data-stu-id="d33dc-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="d33dc-105">При определении одного <xref:System.Data.DataColumn> как <xref:System.Data.DataTable.PrimaryKey%2A> для <xref:System.Data.DataTable>, в таблице автоматически присваивается <xref:System.Data.DataColumn.AllowDBNull%2A> свойство столбца **false** и <xref:System.Data.DataColumn.Unique%2A> свойства  **значение true,**.</span><span class="sxs-lookup"><span data-stu-id="d33dc-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="d33dc-106">Для нескольких столбцов первичных ключей, только **AllowDBNull** свойству автоматически присваивается **false**.</span><span class="sxs-lookup"><span data-stu-id="d33dc-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="d33dc-107">**PrimaryKey** свойство <xref:System.Data.DataTable> получает в качестве значения массив из одного или нескольких **DataColumn** объектов, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="d33dc-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="d33dc-108">В первом примере в качестве первичного ключа определяется один столбец.</span><span class="sxs-lookup"><span data-stu-id="d33dc-108">The first example defines a single column as the primary key.</span></span>  
  
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
  
 <span data-ttu-id="d33dc-109">Следующий пример определяет два столбца в качестве первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="d33dc-109">The following example defines two columns as a primary key.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d33dc-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d33dc-110">See also</span></span>

- <xref:System.Data.DataTable>
- [<span data-ttu-id="d33dc-111">Определение схемы DataTable</span><span class="sxs-lookup"><span data-stu-id="d33dc-111">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [<span data-ttu-id="d33dc-112">DataTables</span><span class="sxs-lookup"><span data-stu-id="d33dc-112">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="d33dc-113">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d33dc-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
