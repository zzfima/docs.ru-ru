---
title: Определение первичных ключей
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 0f87b1b730eecf0edad75bd87ca8b491b96e1d2b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784704"
---
# <a name="defining-primary-keys"></a><span data-ttu-id="27924-102">Определение первичных ключей</span><span class="sxs-lookup"><span data-stu-id="27924-102">Defining Primary Keys</span></span>
<span data-ttu-id="27924-103">База данных обычно содержит столбец или группу столбцов, уникально определяющих каждую строку в таблице.</span><span class="sxs-lookup"><span data-stu-id="27924-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="27924-104">Такие столбцы или группы столбцов называются первичными ключами.</span><span class="sxs-lookup"><span data-stu-id="27924-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="27924-105">При определении <xref:System.Data.DataColumn> одного объекта в <xref:System.Data.DataTable.PrimaryKey%2A> качестве для <xref:System.Data.DataTable>таблицы автоматически присваивает <xref:System.Data.DataColumn.AllowDBNull%2A> свойству столбца **значение false** , а <xref:System.Data.DataColumn.Unique%2A> свойству — **значение true**.</span><span class="sxs-lookup"><span data-stu-id="27924-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="27924-106">Для первичных ключей с несколькими столбцами автоматически присваивается **значение false**только для свойства **AllowDbNull** .</span><span class="sxs-lookup"><span data-stu-id="27924-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="27924-107">Свойство <xref:System.Data.DataTable> PrimaryKey принимает в качестве значения массив из одного или нескольких объектов **DataColumn** , как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="27924-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="27924-108">В первом примере в качестве первичного ключа определяется один столбец.</span><span class="sxs-lookup"><span data-stu-id="27924-108">The first example defines a single column as the primary key.</span></span>  
  
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
  
 <span data-ttu-id="27924-109">Следующий пример определяет два столбца в качестве первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="27924-109">The following example defines two columns as a primary key.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="27924-110">См. также</span><span class="sxs-lookup"><span data-stu-id="27924-110">See also</span></span>

- <xref:System.Data.DataTable>
- [<span data-ttu-id="27924-111">Определение схемы DataTable</span><span class="sxs-lookup"><span data-stu-id="27924-111">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="27924-112">DataTables</span><span class="sxs-lookup"><span data-stu-id="27924-112">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="27924-113">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="27924-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
